---
title: Gestion et automatisation des processus avec les workflows Adobe Campaign
description: Prise en main des workflows
feature: Workflows
role: User, Admin
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '1625'
ht-degree: 100%

---

# Prise en main des workflows{#gs-with-workflows}

Configurez Campaign afin de tirer parti de ses puissantes fonctionnalités d&#39;automatisation des campagnes marketing.

Ce que vous pouvez configurer :

* Workflows
* Opérations récurrentes
* Cycle de validation de bout en bout
* Alertes
* Envoi automatique de rapports
* Événements déclenchés

## Conception et utilisation de workflows {#gs-ac-wf}

Utilisez les workflows d&#39;Adobe Campaign pour améliorer la vitesse et l&#39;échelle relatives à chaque aspect de vos campagnes marketing, de la création de segments à la préparation des messages, en passant par leur diffusion.

Découvrez comment concevoir des workflows dans ces [cas d&#39;utilisation complets](#end-to-end-uc).

Pour en savoir plus sur l’interface utilisateur et l’exécution des workflows, consultez ces pages :

* [Prise en main des workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=fr)

* [Bonnes pratiques relatives aux workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=fr)

* [Workflows techniques natifs](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html?lang=fr)

* [Surveillance d’exécution des workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=fr)

* [Créer une audience dans un workflow de campagne marketing](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=fr)

## Activités de workflows {#wf-activities}

Pour en savoir plus sur les activités de workflow disponibles, consultez [cette section](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/activities.html?lang=fr)

Les activités de workflow sont regroupées par catégorie. Les quatre catégories d&#39;activités disponibles sont les suivantes :

* [Activités de ciblage](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html?lang=fr) : requête, lecture de liste, enrichissement, union, etc.
* [Activités d&#39;ordonnancement](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html?lang=fr) : planificateur, branchement, alerte, signal externe, etc.
* [Activités d&#39;action](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html?lang=fr) : diffusions cross-canal, code JavaScript, activités CRM, mise à jour d&#39;agrégat, etc.
* [Activités d&#39;événement](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html?lang=fr) : transfert de fichiers, téléchargement web, etc.

### Activité Modifier la source de données {#change-data-source-activity}

L&#39;activité **[!UICONTROL Modifier la source de données]** permet de modifier la source de données d&#39;un workflow **[!UICONTROL Table de travail]**. Vous bénéficiez ainsi d&#39;une plus grande flexibilité pour gérer les données entre différentes sources de données, telles que FDA, FFDA et base de données locale.

La **[!UICONTROL table de travail]** permet au workflow Adobe Campaign de gérer les données et de partager les données avec les activités de workflow.
Par défaut, la **[!UICONTROL table de travail]** est créée dans la même base de données que la source des données sur lesquelles nous effectuons une requête.

Par exemple, lors de l&#39;interrogation de la table **[!UICONTROL Profils]** stockée dans la base de données cloud, vous allez créer une **[!UICONTROL table de travail]** sur la même base de données cloud.
Pour modifier ce paramètre, vous pouvez ajouter l&#39;activité **[!UICONTROL Modifier la source de données]** afin de choisir une autre source de données pour votre **[!UICONTROL table de travail]**.

Notez que lorsque vous utilisez l&#39;activité **[!UICONTROL Modifier la source de données]**, vous devez revenir à la base de données cloud pour continuer l&#39;exécution des workflows.

Pour utiliser l&#39;activité **[!UICONTROL Modifier la source de données]** :

1. Créez un workflow.

1. Interrogez vos destinataires ciblés avec une activité **[!UICONTROL Requête]**.

   Pour plus d’informations sur l’activité **[!UICONTROL Requête]**, consultez [cette page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=fr).

1. Dans l&#39;onglet **[!UICONTROL Ciblage]**, ajoutez une activité **[!UICONTROL Modifier la source de données]** et double-cliquez dessus pour sélectionner **[!UICONTROL Source de données par défaut]**.

   La table de travail, qui contient le résultat de votre requête, est ensuite déplacée vers la base de données PostgreSQL par défaut.

1. Dans l&#39;onglet **[!UICONTROL Actions]**, effectuez un glisser-déposer d&#39;une activité **[!UICONTROL Code JavaScript]** pour réaliser des opérations unitaires sur la table de travail.

   Pour plus d’informations sur l’activité **[!UICONTROL Code Javascript]**, consultez [cette page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/sql-code-and-javascript-code.html?lang=fr).

1. Ajoutez une autre activité **[!UICONTROL Modifier la source de données]** pour revenir à la base de données cloud.

   Double-cliquez sur votre activité et sélectionnez **[!UICONTROL Compte externe FDA actif]** puis le compte externe correspondant.

1. Vous pouvez maintenant démarrer votre workflow.

## Gestion des entrepôts virtuels {#warehouse}

Une fois votre workflow créé, vous pouvez accéder à des options supplémentaires à l&#39;aide du bouton **[!UICONTROL Propriétés]** pour une configuration plus poussée.

Pour en savoir plus sur les **propriétés du workflow**, consultez [cette page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/workflow-properties.html?lang=fr).

Dans l&#39;onglet **[!UICONTROL Exécution]** de la fenêtre des **[!UICONTROL Propriétés]** de votre workflow, vous pouvez choisir de lier votre workflow à différents entrepôts et optimiser la gestion de votre charge de travail. Pour plus d&#39;informations sur les **Entrepôts**, consultez la [documentation de Snowflake](https://docs.snowflake.com/fr/user-guide/warehouses-overview.html).

![](assets/warehouse.png)

En fonction de l&#39;objectif de votre workflow, vous pouvez choisir parmi les trois entrepôts suivants dans le menu déroulant **[!UICONTROL Entrepôt]** :

* **[!UICONTROL Par défaut]**/**[!UICONTROL Campagne]** : proposé par défaut lors de la création d&#39;un workflow.

* **[!UICONTROL Importation/Exportation]** : doit être utilisé avec les workflows d&#39;importation ou d&#39;exportation afin d&#39;optimiser les performances de vos activités.

* **[!UICONTROL Campagne en rafale]** : doit être utilisé avec les workflows de campagne ou de diffusion afin d&#39;optimiser le temps de traitement de vos diffusions.

>[!NOTE]
>
>L&#39;entrepôt **[!UICONTROL Système]** est uniquement destiné aux workflows intégrés.

## Configuration de campagnes récurrentes

Concevez un workflow récurrent et créez une instance de diffusion à chaque exécution du workflow. Par exemple, si votre workflow est conçu pour s&#39;exécuter une fois par semaine, 52 diffusions seront créées en une année. Cela signifie également que les logs seront séparés par chaque instance de diffusion.

Découvrez comment créer une campagne récurrente sur [cette page](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/recurring-periodic-campaigns.html?lang=fr)


## Utilisation d&#39;événements trigger

Utilisez la messagerie transactionnelle de Campaign pour automatiser les messages générés à partir d&#39;événements déclenchés depuis des systèmes d&#39;information. Ces messages transactionnels peuvent notamment être une facture, une confirmation de commande, une confirmation d&#39;expédition, une modification de mot de passe, une notification d&#39;indisponibilité du produit, un relevé de compte ou la création d&#39;un compte sur un site web. Ces messages peuvent être envoyés individuellement ou par lots via e-mail, SMS ou notifications push.

![](../assets/do-not-localize/glass.png) Pour en savoir plus sur les fonctionnalités des messages transactionnels,consultez [cette section](../send/transactional.md).

Connectez Adobe Campaign et Adobe Analytics pour récupérer les actions utilisateur et envoyer des messages personnalisés en temps quasi réel.

![](../assets/do-not-localize/glass.png) Découvrez comment intégrer Campaign à d&#39;autres solutions dans [cette section](../start/connect.md).


## Cas d&#39;utilisation complets de workflow{#end-to-end-uc}

Cette section présente différents cas d’utilisation utilisant des fonctionnalités de workflows dans Campaign.

### Diffusions {#deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">


* [Envoyer un e-mail d’anniversaire](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=fr)

  Ce cas pratique présente comment planifier l’envoi d’un e-mail récurrent à une liste de destinataires le jour de leur anniversaire.

* [Charger le contenu de la diffusion](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html?lang=fr)
Lorsque le contenu de votre diffusion est disponible dans un fichier HTML situé sur un serveur distant, vous pouvez facilement charger ce contenu dans les diffusions Adobe Campaign.

* [Workflow de diffusion cross-canal](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/cross-channel-delivery-workflow.html?lang=fr)
Découvrez comment créer un workflow de diffusion cross-canal. L&#39;objectif est de segmenter une audience des destinataires de votre base de données en différents groupes et d&#39;envoyer un e-mail au premier groupe et un SMS à l&#39;autre.

* [Enrichissement des e-mails avec des champs de date personnalisés](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/email-enrichment-with-custom-date-fields.html?lang=fr)
Découvrez comment envoyer un e-mail avec des champs de données personnalisés aux profils qui célèbrent leur anniversaire ce mois-ci. L’e-mail contiendra un coupon valide une semaine avant et après leur anniversaire.

Ainsi que ces pages dans la documentation de Campaign v7 :

* [Automatiser la création, l’édition et la publication de contenu](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/content-management/automating-via-workflows.html?lang=fr){target="_blank"}
Découvrez comment automatiser la création et la diffusion d’un bloc de contenu avec le module complémentaire de gestion de contenu de Campaign.

* [Tests AB](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/a-b-testing/use-case/a-b-testing-use-case.html?lang=fr){target="_blank"}
Découvrez comment comparer deux contenus de diffusion par e-mail via un workflow de ciblage. Le message et le texte sont identiques dans les deux diffusions : seule la disposition change. La population ciblée est divisée en trois : deux groupes de test et la population restante. Une version différente de la diffusion est envoyée à chaque groupe de test.

### Surveillance {#monitoring}

<img src="assets/do-not-localize/icon_monitoring.svg" width="60px">

* [Envoi d&#39;un rapport à une liste](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/send-a-report-to-a-list.html?lang=fr)
Découvrez comment générer un rapport mensuel intégré des indicateurs de tracking au format PDF et l’envoyer à une liste d’opérateurs Campaign.

* [Superviser vos workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/workflow-supervision.html?lang=fr)
Découvrez comment créer un workflow qui vous permet de surveiller l’état d’un ensemble de workflows « en pause », « arrêtés » ou « contenant des erreurs ».

* [Envoyer des alertes personnalisées aux opérateurs](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/monitoring/send-alerts-to-operators.html?lang=fr)
Découvrez comment envoyer à un opérateur une alerte contenant le nom des profils qui ont ouvert une newsletter, sans toutefois cliquer sur le lien qu’elle contient.

### Gestion des données {#management}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

* [Coordonner les mises à jour de données](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/coordinate-data-updates.html?lang=fr)
Découvrez comment vérifier que le processus de mise à jour est terminé avant d’exécuter une autre opération de mise à jour. Pour ce faire, nous allons configurer une variable d&#39;instance et laisser le workflow tester si l’instance est en cours d’exécution afin de décider de continuer ou non l’exécution du workflow et d’effectuer la mise à jour.

* [Créer une liste récapitulative](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/create-a-summary-list.html?lang=fr)
Découvrez comment créer un workflow qui, après la collecte de fichiers et plusieurs enrichissements, permet de créer une liste récapitulative. L&#39;exemple est basé sur une liste de contacts qui ont effectué des achats dans un magasin.

* [Enrichissement des données](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/enrich-data.html?lang=fr)
Découvrez comment envoyer des diffusions personnalisées aux profils ayant participé au dernier jeu-concours en fonction de leur score.

* [Utiliser des agrégats](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html?lang=fr)
Découvrez comment identifier les derniers destinataires ajoutés à la base de données.

* [Mise à jour trimestrielle de la liste à l’aide d’une requête incrémentale](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/quarterly-list-update.html?lang=fr)
Découvrez comment utiliser une requête incrémentale pour mettre automatiquement à jour une liste de destinataires.

* [Configurer un workflow d’importation récurrent](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html?lang=fr)
Découvrez comment concevoir un workflow qui peut être réutilisé pour importer des profils en provenance d’un CRM dans la base de données Adobe Campaign.

### Ciblage {#designing-queries}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

* [Effectuer une requête sur la table des destinataires](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/querying-recipient-table.html?lang=fr)
Découvrez comment récupérer les noms et les e-mails des destinataires dont le domaine d’e-mail est « orange.co.uk » et qui ne vivent pas à Londres.

* [Informations sur la diffusion de requêtes](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-delivery-info.html?lang=fr)
Découvrez comment définir des requêtes sur les informations de diffusion pour récupérer le comportement du profil.

* [Calculer les agrégats](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/compute-aggregates.html?lang=fr)
Découvrez comment compter le nombre de profils vivant à Londres, en fonction du genre.

* [Requête avec une relation plusieurs-à-plusieurs](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-many-to-many-relationship.html?lang=fr)
Découvrez comment trouver des profils qui n’ont pas été contactés au cours des 7 derniers jours.

* [Appeler une variable d’instance dans une requête](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/javascript-scripts-and-templates.html?lang=fr)
Découvrez comment utiliser une variable d’instance pour calculer dynamiquement le pourcentage de partage à appliquer à une population.

<!--
### Change data source activity {#data-source-uc}

The **[!UICONTROL Change data source]** activity allows you to change the data source of a workflow **[!UICONTROL Working table]**. 

In this use case, learn how to use the **[!UICONTROL Change data source]** activity to perform unitary operations to insert or update information to the recipient table.

![](assets/wf_data_source_uc.png)

1. Create a workflow and add a **[!UICONTROL Start]** activity.

1. Query your targeted recipients from the NmsRecipient table with a **[!UICONTROL Query]** activity. 

    For more information on the **[!UICONTROL Query]** activity, refer to the [Query](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/query.html#creating-a-query) page in Campaign Classic V7 documentation.

1. 

1. From the **[!UICONTROL Targeting]** tab, add a **[!UICONTROL Change data source]** activity and double-click it to select **[!UICONTROL Default data source]**.
    
    The working table, which contains the result of your query, is then moved to the default PostgreSQL database.

1. From the **[!UICONTROL Actions]** tab, drag and drop a **[!UICONTROL JavaScript code]** activity to perform unitary operations on the working table.

1. Add another **[!UICONTROL Change data source]** activity to revert back to the Cloud database. 
    
    Double-click your activity and select **[!UICONTROL Active FDA external account]** then the corresponding external account.

1. Add an **[!UICONTROL End]** activity and start your workflow.
-->

