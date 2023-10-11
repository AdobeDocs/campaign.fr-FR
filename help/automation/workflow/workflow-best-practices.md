---
product: campaign
title: Bonnes pratiques relatives aux workflows
description: Découvrez les bonnes pratiques relatives aux workflows de Campaign
feature: Workflows
role: User, Admin
exl-id: 8bcaf367-5b1f-4d31-80c9-c77df43c6ed1
source-git-commit: d4e28ddf6081881f02042416aa8214761ea42be9
workflow-type: tm+mt
source-wordcount: '1379'
ht-degree: 96%

---

# Bonnes pratiques relatives aux workflows{#workflow-best-practices}

Vous trouverez ci-dessous des instructions générales pour optimiser les performances des workflows de Campaign, améliorer la conception de vos workflows et sélectionner les paramètres appropriés.

## Dossiers des workflows {#workflow-folders}

Adobe conseille de créer les workflows dans un dossier dédié.

Si le workflow a un impact sur l’ensemble de la plateforme (processus de nettoyage, par exemple), vous pouvez ajouter un sous-dossier au dossier intégré **[!UICONTROL Workflows techniques]**.

## Attribution d’un nom au workflow {#workflow-naming}

Pour trouver plus facilement les workflows qui ne fonctionnent pas de la manière attendue et résoudre les problèmes, Adobe recommande d&#39;attribuer aux workflows des libellés et des noms adéquats. Renseignez également le champ de description du workflow pour que l&#39;opérateur puisse facilement comprendre son objectif.

Si le workflow fait partie d&#39;un processus impliquant d&#39;autres workflows, vous pouvez saisir un libellé explicite, en utilisant par exemple des chiffres pour classer les workflows (par libellé).

Par exemple :

* 001 - Import - Import des destinataires
* 002 - Import - Import des ventes
* 003 - Import - Import des détails sur les ventes
* 010 - Export - Export des logs de diffusion
* 011 - Export - Export des logs de tracking

## Niveau de criticité d’un workflow {#workflow-severity}

Vous pouvez configurer le niveau de criticité d&#39;un workflow dans l&#39;onglet **[!UICONTROL Exécution]** des propriétés du workflow :

* Normal
* Production
* Critique

Si vous indiquez cette information lors de la création d&#39;un workflow, vous déterminerez le niveau de priorité du processus configuré.

Cette option n&#39;a aucun impact fonctionnel sur les workflows autres que les workflows d&#39;opération.

Les workflows d&#39;opération (créés dans le cadre d&#39;une opération/campagne) avec un niveau de priorité plus élevé sont exécutés en premier si l&#39;opération comprend plusieurs processus qui sont supposés s&#39;exécuter simultanément. Par défaut, seuls 10 processus peuvent s&#39;exécuter simultanément dans une opération, selon l&#39;option NmsOperation_LimitConcurrency. Par exemple, si une opération contient 25 workflows, ceux avec une priorité plus élevée seront exécutés dans le premier pool de 10 processus.

## Surveillance des workflows {#workflow-monitoring}

Vous devez surveiller tous les workflows planifiés s&#39;exécutant dans des environnement de production afin d&#39;être averti en cas d&#39;erreur.

Dans les propriétés d&#39;un workflow, sélectionnez un groupe de responsables : le groupe **[!UICONTROL Superviseurs de workflow]** par défaut ou un groupe personnalisé. Vérifiez qu&#39;un opérateur au moins appartient à ce groupe et qu&#39;il dispose d&#39;une adresse email.

Avant de commencer la construction d’un workflow, pensez à définir les superviseurs. Ceux-ci seront avertis par email lorsqu’un workflow sera en erreur. Pour plus d&#39;informations, consultez la section [Gérer les erreurs](monitor-workflow-execution.md#managing-errors).

Vérifiez régulièrement l’onglet **[!UICONTROL Supervision]** pour connaître le statut des workflows actifs. Pour plus d&#39;informations, consultez la section [Supervision de l’instance](monitor-workflow-execution.md#instance-supervision).

La carte thermique des workflows permet aux administrateurs de la plateforme Adobe Campaign de surveiller la charge sur l’instance et de planifier les workflows en conséquence. Voir à ce sujet [Surveillance des workflows](heatmap.md).

## Activités {#using-activities}

>[!CAUTION]
>
>Vous pouvez copier et coller des activités dans un même workflow. Toutefois, nous vous déconseillons de copier et coller des activités dans différents workflows. Certains paramètres associés à des activités telles que Diffusions et Planificateur peuvent entraîner des conflits et des erreurs lors de l&#39;exécution du workflow de destination. Nous vous recommandons plutôt de **dupliquer** les workflows. Pour plus d&#39;informations, voir la section [Duplication des workflows](build-a-workflow.md#duplicate-workflows).

### Attribution d&#39;un nom à une activité {#name-of-the-activity}

Lors du développement de votre workflow, toutes les activités seront dotées d&#39;un nom, tout comme les objets Adobe Campaign. Bien que ce nom soit généré par l&#39;outil, il est recommandé d&#39;attribuer à une activité un nom explicite lors de sa configuration. Si vous le faites plus tard, le workflow peut être interrompu si les activités utilisent le nom d&#39;activités précédentes et la mise à jour des noms risque d&#39;être difficile.

Le nom de l’activité se trouve dans la variable **[!UICONTROL Avancé]** . Ne les laissez pas nommées **[!UICONTROL query]**, **[!UICONTROL query1]**, **[!UICONTROL query11]**, mais attribuez-leur des noms explicites tels que **[!UICONTROL querySubscribedRecipients]**. Ce nom apparaît dans le journal et, le cas échéant, dans les journaux SQL. Il permet de déboguer le workflow lors de sa configuration.

### Premières et dernières activités {#first-and-last-activities}

* Commencez toujours votre workflow par une activité **[!UICONTROL Début]** ou une activité **[!UICONTROL Planificateur]**. Lorsque cela est pertinent, vous pouvez également utiliser une activité **[!UICONTROL Signal externe]**.
* Lors de la construction de votre workflow, n&#39;utilisez qu&#39;une seule **** activité Planificateur par branche. Si une même branche d&#39;un workflow comporte plusieurs planificateurs (liés les uns aux autres), le nombre de tâches à exécuter sera multiplié de manière exponentielle, ce qui surchargerait considérablement la base. Cette règle s’applique également à toutes les activités comportant un onglet **[!UICONTROL Planification &amp; historique]**. En savoir plus sur la [planification](scheduler.md).

  ![](assets/wf-scheduler.png)

* Utilisez des activités **[!UICONTROL Fin]** dans tous vos workflows. Cela permet à Adobe Campaign de libérer l’espace temporaire utilisé pour réaliser les calculs dans les workflows. Voir à ce sujet la section [Début et Fin](start-and-end.md).

### Code JavaScript dans une activité {#javascript-within-an-activity}

Vous souhaiterez peut-être ajouter du code JavaScript lors de l&#39;initialisation d&#39;une activité de workflow. Vous pouvez le faire dans l&#39;onglet **[!UICONTROL Avancé]** d&#39;une activité.

Pour repérer plus facilement le workflow, il est conseillé d&#39;utiliser deux tirets avant et après le libellé de l&#39;activité, comme dans l&#39;exemple suivant : -- Mon libellé --.

### Signal {#signal}

La plupart du temps, vous ne saurez pas d&#39;où vient l&#39;appel d&#39;un signal. Pour éviter ce problème, utilisez le champ **[!UICONTROL Commentaire]** de l&#39;onglet **[!UICONTROL Avancé]** de l&#39;activité de signal pour documenter l&#39;origine attendue d&#39;un signal pour l&#39;activité en question.

## Mises à jour des workflows {#workflow-update}

Un workflow de production ne doit pas être directement mis à jour. À moins que le processus consiste à créer une opération avec des modèles de workflow, les processus doivent être d&#39;abord testés dans un environnement de développement. Après validation, le workflow peut être déployé et démarré en production.

Effectuez tous les tests dans les environnements de développement ou d’évaluation, et non dans les environnements de production, où les performances ne peuvent pas être garanties.

Les workflows archivés peuvent être conservés sur des plateformes de développement ou de test, dans un dossier Archivé. Un environnement de production doit en revanche rester aussi propre que possible. Les anciens workflows doivent être supprimés de l&#39;environnement de production s&#39;ils sont inactifs.

## Exécution et performance {#execution-and-performance}

### Logs {#logs}

La méthode JavaScript **[!UICONTROL logInfo()]** est une solution permettant de déboguer un workflow. Toutefois, vous devez l&#39;utiliser avec précaution, en particulier pour les activités que vous exécutez fréquemment : il peut surcharger les logs et augmenter considérablement la taille de la table des logs.

### Conserver les populations intermédiaires

L&#39;option **Conserver le résultat des populations intermédiaires entre deux exécutions** conserve les tables temporaires entre deux exécutions d&#39;un workflow.

Elle est disponible dans l&#39;onglet **[!UICONTROL Général]** des propriétés du workflow et peut être utilisée à des fins de développement et de test pour surveiller les données et vérifier les résultats. Vous pouvez utiliser cette option dans les environnements de développement, mais ne l&#39;utilisez jamais dans les environnements de production. La conservation des tables temporaires peut entraîner une augmentation significative de la taille de la base de données et, par la suite, l&#39;atteinte de la limite de taille. De plus, cela ralentira la sauvegarde.

Seules les tables de travail de la dernière exécution du workflow sont conservées. Celles des exécutions précédentes sont purgées par le workflow de **[!UICONTROL nettoyage]** qui s&#39;exécute tous les jours.

>[!CAUTION]
>
>Ne cochez **jamais** cette option dans un workflow de **production**. Elle sert à analyser les résultats et est conçue uniquement à des fins de test. Elle ne doit donc être utilisée que dans les environnements de développement ou d&#39;évaluation.


### Enregistrer les requêtes SQL

L&#39;option **Enregistrer les requêtes SQL dans le journal** est disponible dans l&#39;onglet **[!UICONTROL Exécution]** des propriétés de workflow. Cette option enregistre toutes les requêtes SQL des différentes activités et permet de voir ce qui est réellement exécuté par la plateforme. Toutefois, cette option ne doit être utilisée que **temporairement** pendant le développement et **non activée pendant la production**.

Une bonne pratique consiste à purger les logs lorsqu&#39;ils ne sont plus nécessaires. L’historique d’un workflow n’est pas purgé automatiquement : tous les messages sont conservés par défaut. Vous pouvez purger l’historique depuis le menu **[!UICONTROL Fichier > Actions]** ou en cliquant sur le bouton Actions situé dans la barre d’outils au-dessus de la liste. Choisissez Purge de l’historique.
Pour savoir comment purger les logs, consultez cette [documentation](start-a-workflow.md).

### Planification des workflows {#workflow-planning}

D&#39;autres bonnes pratiques doivent être appliquées lors de la planification de l&#39;exécution de vos workflows afin d&#39;éviter tout problème :

* Maintenez un niveau d&#39;activité stable tout au long de la journée et évitez les pics afin d&#39;empêcher la surcharge de l&#39;instance. Pour ce faire, répartissez les heures de début des workflows de manière uniforme tout au long de la journée.
* Planifiez le chargement des données au cours de la nuit de façon à réduire les conflits entre les données.
* Les workflows longs peuvent avoir une incidence sur les ressources du serveur et de la base de données. Fractionnez les workflows les plus longs pour réduire le temps de traitement.
* Pour réduire les temps d’exécution globaux, remplacez les activités exigeant beaucoup de temps par des activités simplifiées et plus rapides.
* Évitez d’exécuter plus de 20 workflows simultanément. Lorsque trop de workflows sont exécutés en même temps, votre plateforme peut être surchargée et devenir instable.


### Option Exécuter dans le moteur {#execute-in-the-engine-option}

Dans un environnement de production, évitez d&#39;exécuter des workflows dans le moteur. Lorsque l&#39;option **[!UICONTROL Exécuter dans le moteur]** est cochée dans les **[!UICONTROL Propriétés d&#39;un workflow]**, le workflow en question devient prioritaire et tous les autres workflows sont arrêtés par le moteur de workflow tant que celui-ci n&#39;est pas terminé.

![](assets/wf-execute-in-engine.png)
