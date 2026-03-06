---
title: Connecteurs SMS
description: Découvrez les connecteurs SMS dans Adobe Campaign
feature: SMS
role: User, Admin
level: Intermediate
source-git-commit: e349e9f236c3eeb28ffe96bcc5ec72ab64c4c127
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 1%

---

# À propos des types de connecteurs SMS {#sms-connectors}

Adobe Campaign prend en charge deux connecteurs SMS utilisés pour envoyer des SMS à vos clients :

* **Connecteur SMS hérité** : première version du connecteur utilisé dans Campaign v7 et les versions antérieures de Campaign v8. [En savoir plus](#legacy-sms-connector)
* **Connecteur SMS v2** : disponible en disponibilité générale à partir de la version 8.9.1 de Campaign, ce connecteur SMS dédié v2 a été modernisé pour offrir des performances et une fiabilité améliorées. [En savoir plus](#sms-connector-v2)

## Connecteur SMS hérité {#legacy-sms-connector}

L’ancien connecteur SMS est le connecteur SMS basé sur le MTA utilisé dans les versions précédentes d’Adobe Campaign. Ce connecteur est toujours pris en charge pour les implémentations existantes, mais Adobe recommande vivement d’effectuer la mise à niveau vers la version 8.9.1 ou une version ultérieure pour bénéficier des performances améliorées et de la fiabilité du connecteur v2.

Pour savoir comment bénéficier du connecteur v2, reportez-vous à la section [Activation](#activation).

Pour plus d’informations sur la configuration et l’utilisation de l’ancien connecteur SMS, consultez la documentation de Campaign Classic [&#128279;](https://experienceleague.adobe.com/fr/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up){target="_blank"}.

## Connecteur SMS v2 {#sms-connector-v2}

Disponible dans GA à partir de la version 8.9.1, le connecteur v2 active les connexions SMPP en mode émetteur-récepteur, les connexions SMPP persistantes et assure une meilleure compatibilité. Un compte externe SMS dédié est disponible pour toutes les implémentations SMS utilisant le connecteur v2.

Le connecteur v2 est activé par défaut pour les nouvelles installations. Si vous avez effectué une mise à niveau à partir d’une version précédente à l’aide de l’ancien connecteur, vous devez contacter votre représentant Adobe pour passer au connecteur v2. Pour plus d&#39;informations, consultez la section [&#x200B; Activation &#x200B;](#activation) .

Pour savoir comment utiliser le connecteur SMS v2 dans Campaign v8, reportez-vous à la [documentation SMS](sms.md).

>[!NOTE]
>
>Le connecteur v2 est également disponible dans les builds suivants avec certaines restrictions :
>* 8.8.1 : version pour tous les environnements FDA Campaign. Non disponible pour les déploiements Campaign FFDA.
>* 8.8.2 : version pour tous les types de déploiement, y compris FFDA. Disponible en disponibilité limitée (LA).

## Activation {#activation}

### Pourquoi passer au connecteur v2 ? {#why-switch-v2}

Le processus SMS dédié introduit la prise en charge du mode émetteur-récepteur SMPP, réduisant le nombre de connexions et améliorant l’efficacité des ressources, tout en prenant toujours en charge les configurations émetteur/récepteur si nécessaire. Il offre une stabilité nettement supérieure, avec une récupération plus rapide en cas d’erreur, des connexions persistantes et aucune dépendance aux fichiers locaux ou à la communication entre processus. Les performances sont également améliorées, avec une latence plus faible, un débit plus élevé et un microtraitement intelligent pour équilibrer la vitesse et la fiabilité. En outre, l’isolation du processus SMS simplifie la résolution des problèmes et réduit l’impact cross-canal. Ces améliorations font du connecteur dédié une solution plus robuste et évolutive pour la diffusion de SMS.

### Configuration  {#configuration}

Avec Adobe Campaign Managed Cloud Services, la configuration du serveur et la migration du connecteur SMS sont gérées par Adobe. Cette procédure technique nécessite un accès direct aux fichiers de configuration du serveur et aux opérations de base de données.

Pour activer et commencer à utiliser le connecteur SMS v2, vous devez d’abord effectuer la mise à niveau vers la version 8.9.1 ou une version ultérieure. Contactez votre représentant Adobe ou l’assistance clientèle Adobe. Ils planifient et exécutent les mises à jour nécessaires pour votre instance.