---
title: Modifier la source de données
description: En savoir plus sur l’activité Modifier la source de données
feature: Workflows, Data Management, Federated Data Access
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 19%

---

# Modifier la source de données {#change-data-source}

Utilisez la variable **[!UICONTROL Modification de la source de données]** pour modifier la source de données d’une [table de travail des workflows](use-workflow-data.md#workflow-temporary-work-table). Cette activité offre davantage de flexibilité pour gérer les données entre différentes sources de données, telles que Federated Data Access (FDA), Campaign Cloud Database (FFDA) et Campaign Local database.

Le workflow **[!UICONTROL Table de travail]** est utilisé pour gérer et partager des données avec les activités de workflow.

Par défaut, la variable **[!UICONTROL Table de travail]** est créé dans la même base de données que la source des données sur lesquelles vous devez effectuer des requêtes.
Par exemple, lors de l’interrogation de la variable **[!UICONTROL Destinataires]** stockée dans la base de données Cloud, le workflow crée une **[!UICONTROL Table de travail]** sur la même base de données Cloud.

Utilisez une **[!UICONTROL Modifier la source de données]** pour utiliser une autre source de données pour votre **[!UICONTROL Table de travail]**.

Notez que lors de l’utilisation de la variable **[!UICONTROL Modifier la source de données]** , vous devez revenir à la base de données Cloud pour continuer l’exécution du workflow.

Pour utiliser la variable **[!UICONTROL Modifier la source de données]** activité, vous devez :

1. Créez un workflow.

1. Interrogez vos destinataires ciblés avec une activité **[!UICONTROL Requête]**.

   Pour plus d&#39;informations sur l&#39;activité **[!UICONTROL Requête]**, consultez cette [page](query.md#create-a-query).

1. Ajouter un **[!UICONTROL Modification de la source de données]** activité.

   ![](assets/change-data-source.png)

1. Modifiez votre **[!UICONTROL Modification de la source de données]** activité à sélectionner **[!UICONTROL Source de données par défaut]**.

   La table de travail, qui contient le résultat de votre requête, est ensuite déplacée vers la base de données locale Campaign par défaut.

   ![](assets/change-data-source_2.png)

1. Ajouter un **[!UICONTROL Code JavaScript]** pour effectuer des opérations unitaires sur la table de travail.

   Pour plus d’informations sur la variable **[!UICONTROL Code JavaScript]** , voir [cette page](sql-code-and-javascript-code.md#javascript-code).

1. Ajoutez une autre activité **[!UICONTROL Modifier la source de données]** pour revenir à la base de données cloud.

1. Modifiez cette activité et sélectionnez **[!UICONTROL Compte externe principal FDA]**, et le **[!UICONTROL Base de données externe]** compte externe .

   ![](assets/change-data-source_3.png)

1. Vous pouvez maintenant démarrer votre workflow.
