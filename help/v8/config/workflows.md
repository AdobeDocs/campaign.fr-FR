---
title: Gestion et automatisation des processus avec les workflows Adobe Campaign
description: Prise en main des workflows
feature: Workflows
role: User, Admin
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: 95c944963feee746a2bb83a85f075134c91059d1
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 93%

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

>[!NOTE]
>
>L’interface utilisateur web d’Adobe Campaign s’accompagne d’une zone de travail repensée pour les workflows, ce qui permet de créer des parcours client plus dynamiques et personnalisés. Pour en savoir plus sur les workflows pour l’interface d’utilisation web, reportez-vous à la [documentation de l’interface d’utilisation d’Adobe Campaign Web](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/wf/gs-workflows){target=_blank}.


## Conception et utilisation de workflows {#gs-ac-wf}

Utilisez les workflows d’Adobe Campaign pour améliorer la vitesse et l’échelle relatives à chaque aspect de vos campagnes marketing, de la création de segments à la préparation des messages, en passant par leur diffusion.

Pour en savoir plus sur l’interface utilisateur et l’exécution des workflows, consultez ces pages :

* [Prise en main des workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=fr){target="_blank"}

* [Bonnes pratiques relatives aux workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=fr){target="_blank"}

* [Workflows techniques natifs](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html?lang=fr){target="_blank"}

* [Surveillance d’exécution des workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=fr){target="_blank"}

* [Créer une audience dans un workflow de campagne marketing](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=fr){target="_blank"}

## Activités de workflows {#wf-activities}

Pour en savoir plus sur les activités de workflow disponibles, consultez [cette section](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/activities.html?lang=fr){target="_blank"}

Les activités de workflow sont regroupées par catégorie. Les quatre catégories d&#39;activités disponibles sont les suivantes :

* [Activités de ciblage](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html?lang=fr){target="_blank"} : requête, lecture de liste, enrichissement, union, etc.
* [Activités d&#39;ordonnancement](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html?lang=fr){target="_blank"} : planificateur, branchement, alerte, signal externe, etc.
* [Activités d&#39;action](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html?lang=fr){target="_blank"} : diffusions cross-canal, code JavaScript, activités CRM, mise à jour d&#39;agrégat, etc.
* [Activités d&#39;événement](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html?lang=fr){target="_blank"} : transfert de fichiers, téléchargement web, etc.

<!--
### Change data source activity {#change-data-source-activity}

The **[!UICONTROL Change data source]** activity allows you to change the data source of a workflow **[!UICONTROL Working table]**. This provides more flexibility to manage data across different data sources such as FDA, FFDA and local database.

The **[!UICONTROL Working table]** allows Adobe Campaign workflow to handle data and share data with the workflow activities.
By default, the **[!UICONTROL Working table]** is created in the same database as the source of the data we query on.

For example, when querying the **[!UICONTROL Profiles]** table, stored on the Cloud database, you will create a **[!UICONTROL Working table]** on the same Cloud database.
To change this, you can add the **[!UICONTROL Change Data Source]** activity to choose a different data source for your **[!UICONTROL Working table]**.

Note that when using the **[!UICONTROL Change Data Source]** activity, you will need to switch back to the Cloud database to continue the workflow execution.

To use the **[!UICONTROL Change Data Source]** activity:

1. Create a workflow.

1. Query your targeted recipients with a **[!UICONTROL Query]** activity. 

    For more information on the **[!UICONTROL Query]** activity, refer to [this page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html){target="_blank"}.

1. From the **[!UICONTROL Targeting]** tab, add a **[!UICONTROL Change data source]** activity and double-click it to select **[!UICONTROL Default data source]**.
    
    The working table, which contains the result of your query, is then moved to the default PostgreSQL database.

1. From the **[!UICONTROL Actions]** tab, drag and drop a **[!UICONTROL JavaScript code]** activity to perform unitary operations on the working table.

    For more information on the **[!UICONTROL JavaScript code]** activity, refer to [this page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/sql-code-and-javascript-code.html){target="_blank"}.

1. Add another **[!UICONTROL Change data source]** activity to switch back to the Cloud database. 
    
    Double-click your activity and select **[!UICONTROL Active FDA external account]** then the corresponding external account.

1. You can now start your workflow.
-->

## Gestion des entrepôts virtuels {#warehouse}

Une fois votre workflow créé, vous pouvez accéder à des options supplémentaires à l&#39;aide du bouton **[!UICONTROL Propriétés]** pour une configuration plus poussée.

Pour en savoir plus sur les **propriétés du workflow**, consultez [cette page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/advanced-management/workflow-properties.html?lang=fr){target="_blank"}.

Dans l’onglet **[!UICONTROL Exécution]** de la fenêtre des **[!UICONTROL Propriétés]** de votre workflow, vous pouvez choisir de lier votre workflow à différents entrepôts et optimiser la gestion de votre charge de travail. Pour plus d&#39;informations sur les **Entrepôts**, consultez la [documentation de Snowflake](https://docs.snowflake.com/fr/user-guide/warehouses-overview.html){target="_blank"}.

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

Découvrez comment créer une campagne récurrente sur [cette page](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/recurring-periodic-campaigns.html?lang=fr){target="_blank"}.


## Utilisation d’événements de déclenchement

Utilisez la messagerie transactionnelle de Campaign pour automatiser les messages générés à partir d&#39;événements déclenchés depuis des systèmes d&#39;information. Ces messages transactionnels peuvent notamment être une facture, une confirmation de commande, une confirmation d&#39;expédition, une modification de mot de passe, une notification d&#39;indisponibilité du produit, un relevé de compte ou la création d&#39;un compte sur un site web. Ces messages peuvent être envoyés individuellement ou par lots via e-mail, SMS ou notifications push.

Pour en savoir plus sur les fonctionnalités de la messagerie transactionnelle, consultez [cette section](../send/transactional.md).

Connectez Adobe Campaign et Adobe Analytics pour récupérer les actions utilisateur et envoyer des messages personnalisés en temps quasi réel.

Découvrez comment intégrer Campaign à d’autres solutions dans [cette section](../start/connect.md).


## Cas d’utilisation complets de workflow{#end-to-end-uc}

Découvrez les cas pratiques utilisant les fonctionnalités des workflows Campaign [dans cette section](../../automation/workflow/workflow-use-cases.md).
