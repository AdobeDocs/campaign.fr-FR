---
title: Modifier la source de données
description: En savoir plus sur l’activité Modifier la source de données
feature: Workflows, Data Management, Federated Data Access
role: User
version: Campaign v8, Campaign Classic v7
exl-id: ca7eca9d-9112-4ea1-9a0c-a24cf6a978e6
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 100%

---

# Modifier la source de données {#change-data-source}

L&#39;activité **[!UICONTROL Modifier la source de données]** permet de modifier la source de données d&#39;une [table de travail d&#39;un workflow](use-workflow-data.md#workflow-temporary-work-table). Cette activité offre davantage de flexibilité permettant de gérer les données entre les différentes sources de données, telles que Federated Data Access (FDA), la base de données cloud de Campaign (FFDA) et la base de données locale de Campaign.

La **[!UICONTROL table de travail]** du workflow est utilisée pour gérer et partager des données avec les activités du workflow.

Par défaut, la **[!UICONTROL table de travail]** est créée dans la même base de données que la source des données sur lesquelles vous devez effectuer une requête.
Par exemple, lors de l&#39;interrogation de la table des **[!UICONTROL Destinataires]** stockée dans la base de données cloud, le workflow crée une **[!UICONTROL table de travail]** dans la même base de données cloud.

Utilisez une activité **[!UICONTROL Modifier la source de données]** pour utiliser une autre source de données pour votre **[!UICONTROL table de travail]**.

Notez que lorsque vous utilisez l&#39;activité **[!UICONTROL Modifier la source de données]**, vous devez revenir à la base de données cloud pour continuer l&#39;exécution des workflows.

>[!IMPORTANT]
>
>Veuillez noter que les activités **[!UICONTROL Changer la dimension]** et **[!UICONTROL Modifier la source de données]** ne doivent pas être ajoutées sur une même ligne. Si vous devez utiliser les deux activités consécutivement, veillez à inclure une activité **[!UICONTROL Enrichissement]** entre les deux. Cela garantit une bonne exécution et évite les erreurs et conflits potentiels.

Pour utiliser l&#39;activité **[!UICONTROL Modifier la source de données]**, vous devez effectuer les opérations suivantes :

1. Créez un workflow.

1. Interrogez vos destinataires ciblés avec une activité **[!UICONTROL Requête]**.

   Pour plus d&#39;informations sur l&#39;activité **[!UICONTROL Requête]**, consultez cette [page](query.md#create-a-query).

1. Ajoutez une activité **[!UICONTROL Modifier la source de données]**.

   ![](assets/change-data-source.png)

1. Modifiez votre activité **[!UICONTROL Modifier la source de données]** pour sélectionner **[!UICONTROL Source de données par défaut]**.

   La table de travail, qui contient le résultat de votre requête, est ensuite déplacée vers la base de données locale par défaut de Campaign.

   ![](assets/change-data-source_2.png)

1. Ajoutez un **[!UICONTROL code JavaScript]** pour effectuer des opérations unitaires sur la table de travail.

   Pour plus d&#39;informations sur l&#39;activité **[!UICONTROL code JavaScript]**, consultez [cette page](sql-code-and-javascript-code.md#javascript-code).

1. Ajoutez une autre activité **[!UICONTROL Modifier la source de données]** pour revenir à la base de données cloud.

1. Modifiez cette activité et sélectionnez **[!UICONTROL Compte externe FDA actif]** puis le compte externe **[!UICONTROL Base de données externe]** correspondant.

   ![](assets/change-data-source_3.png)

1. Vous pouvez maintenant démarrer votre workflow.
