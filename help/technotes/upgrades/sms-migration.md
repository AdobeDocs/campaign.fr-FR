---
title: Passage au nouveau connecteur SMS v2
description: Découvrez comment passer au nouveau connecteur SMS v2
feature: Technote
role: Admin
hide: true
hidefromtoc: true
exl-id: 61a5a3e8-59f8-47ea-afc9-66ec243b8265
source-git-commit: 784c74aaff23dbf1f35c6e8153f90610048e1c07
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 0%

---

# Passage au nouveau connecteur SMS v2

Ce document décrit la procédure et les points essentiels à prendre en compte lors de la migration du connecteur SMS basé sur le MTA vers le nouveau **connecteur de processus SMS dédié** dans Adobe Campaign v8.

## Pourquoi passer au connecteur v2

Le processus SMS dédié introduit la prise en charge du mode émetteur-récepteur SMPP, réduisant le nombre de connexions et améliorant l’efficacité des ressources, tout en prenant toujours en charge les configurations émetteur/récepteur si nécessaire. Il offre une stabilité nettement supérieure, avec une récupération plus rapide en cas d’erreur, des connexions persistantes et aucune dépendance aux fichiers locaux ou à la communication entre processus. Les performances sont également améliorées, avec une latence plus faible, un débit plus élevé et un microtraitement intelligent pour équilibrer la vitesse et la fiabilité. En outre, l’isolation du processus SMS simplifie la résolution des problèmes et réduit l’impact cross-canal. Ces améliorations font du connecteur dédié une solution plus robuste et évolutive pour la diffusion de SMS.

## Différences entre les connecteurs v1 et v2

Le connecteur SMS dédié dans Adobe Campaign v8 introduit plusieurs modifications architecturales par rapport au connecteur basé sur MTA. Une différence clé est l&#39;utilisation par défaut du mode émetteur-récepteur SMPP, qui réduit le nombre de connexions en combinant les fonctions d&#39;envoi et de réception. Si le fournisseur ne prend pas en charge ce mode, il est toujours possible d&#39;utiliser des connexions d&#39;émetteur et de récepteur distinctes. Contrairement au connecteur MTA, l’activation des réponses automatiques n’a aucun effet sur le nombre de connexions et toutes les connexions des destinataires peuvent gérer n’importe quel type de message entrant.

Le nombre de connexions est maintenant calculé à l’aide d’une formule différente :

```
Total connections = SMS sending threads * Number of MTA child connections. 
```

Le paramètre sendingThreads, défini dans serverConf, est défini par défaut sur 1 et doit généralement rester inchangé, sauf en cas d’optimisation spécifique pour des performances élevées. Comme un seul processus gère tout le trafic SMS, la gestion du parallélisme par le biais de ces paramètres est essentielle pour contrôler la charge et le comportement du système.

La fenêtre d’envoi se comporte de la même manière que le connecteur MTA, mais a un impact encore plus important sur les performances dans le mode dédié. Des fenêtres d’envoi plus larges réduisent les IOPS de la base de données et améliorent le débit. Campaign peut gérer efficacement des fenêtres de plus de 1 000 messages, à condition que le fournisseur le prenne en charge et que le cas d’utilisation permette une faible marge de perte ou de duplication des messages en cas de problèmes de connexion. Du côté du fournisseur, la configuration d&#39;une fenêtre d&#39;envoi de SR plus grande peut également améliorer considérablement le débit des rapports de diffusion.

Enfin, bien que la gestion des messages MO (Mobile Originated) reste fonctionnellement inchangée, le code sous-jacent a été mis à jour. Le débit par connexion est toujours limité de la même manière, mais le connecteur dédié permet d’envoyer des rafales beaucoup plus rapidement. Cependant, en l’absence de limites de débit, l’envoi à grande vitesse peut surcharger les ressources du fournisseur ou du système, ce qui recommande de définir des limites de débit MT explicites dans la configuration du compte externe.

## Procédure De Commutation

Pour garantir un passage en douceur au processus SMS dédié, il est préférable d’effectuer l’opération lorsque le trafic SMS est faible ou nul. Certains messages mis en mémoire tampon peuvent être perdus ou laissés dans un état non valide si les mémoires tampons du MTA ne sont pas entièrement vidées. Il est également normal de manquer certains SR pendant une semaine après le changement, en raison de la synchronisation imprévisible des SR. Le non-respect de ces précautions peut entraîner une perte ou une duplication des messages, malgré les garanties intégrées.

Les deux connecteurs SMS utilisent des formats différents pour le traitement SR (Status Report). Bien que tous deux s’appuient sur la table `NmsProviderMsgId`, ils interagissent avec celle-ci différemment. Par conséquent, changer de connecteur nécessite l’effacement de l’ensemble du tableau pour éviter les conflits ou les données orphelines. Il existe plusieurs façons d’effectuer ce nettoyage. Vous trouverez ci-dessous les requêtes SQL que vous pouvez utiliser :

```
TRUNCATE TABLE NmsProviderMsgId;
TRUNCATE TABLE NmsProviderMsgStatus;
```

### Étapes

1. Vérifiez `serverConf` paramètres (`sms > mta2`).
1. Mettre en pause le workflow de préparation des messages en temps réel (le cas échéant).
1. Suspendre toutes les diffusions par SMS.
1. Désactivez le compte externe SMS .
1. Arrêtez et redémarrez les processus MTA et SMS.
1. Assurez-vous qu’aucune connexion SMPP n’est active. Si présent, assurez-vous que toutes les diffusions sont en pause.
1. Effacez le contenu des tables `NmsProviderMsgId` et `NmsProviderMsgStatus` de la base de données.
1. Dans le compte externe :
   * Cochez la case « Processus dédié ».
   * Ajuster les autres paramètres : connexions enfant MTA, débit MT, Fenêtre d&#39;envoi
1. Réactivez le compte externe et enregistrez-le.
1. Reprenez les diffusions par SMS.
1. Vérifiez que les services SMS fonctionnent normalement.

>[!NOTE]
>
>Surveillez les journaux enfants SMS, MTA et MTA pour détecter les erreurs ou les problèmes.
>
>Enregistrez les paramètres du compte externe précédent à des fins de restauration.

### Procédure de restauration

Le retour au connecteur MTA est possible en suivant les mêmes étapes que celles utilisées lors du commutateur initial, dans le même ordre. Cela inclut l’arrêt ou la suspension de toutes les diffusions SMS et la restauration de la configuration d’origine du compte externe.

1. Si l’instance utilise des diffusions en temps réel, mettez en pause le workflow technique responsable de la préparation de ces messages.
1. Suspendre toutes les diffusions par SMS.
1. Désactivez le compte externe SMS .
1. Arrêtez et redémarrez les processus MTA et SMS.
1. Assurez-vous qu’aucune connexion SMPP ne reste active. Si c’est le cas, vérifiez que toutes les diffusions sont correctement suspendues.
1. Effacez les tables `NmsProviderMsgId` et `NmsProviderMsgStatus` de la base de données.
1. Dans le compte externe :
   * Décochez l’option « processus dédié » dans le compte externe.
   * Restaurer tous les paramètres de compte externe précédents : connexions enfant MTA, débit MT, fenêtre d&#39;envoi
1. Réactivez et enregistrez le compte externe.
1. Reprenez toutes les diffusions par SMS.
1. Enfin, vérifiez que les services SMS fonctionnent normalement.
