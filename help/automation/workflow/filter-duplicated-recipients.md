---
product: campaign
title: Filtrer les destinataires en double
description: Découvrez comment filtrer les destinataires en double.
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: cfa1f45c-e1ac-4055-996c-6e8d041889bb
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 100%

---

# Filtrer les destinataires en double {#filtering-duplicated-recipients}



Dans cet exemple, nous allons filtrer les destinataires qui apparaissent deux fois ou davantage dans une diffusion afin de récupérer les profils dupliqués.

Pour réaliser cet exemple, les étapes sont les suivantes :

1. Placez une activité **[!UICONTROL Requête]** dans un workflow, puis ouvrez-la.
1. Cliquez sur **[!UICONTROL Edition de la requête]** et définissez les dimensions de ciblage et de filtrage sur **[!UICONTROL Destinataires]**.

   ![](assets/query_recipients_1.png)

1. Définissez la condition de filtrage suivante pour cibler les destinataires qui se trouvent dans le log de diffusion. Sélectionnez **Log de diffusion d&#39;un destinataire (broadlog)** dans la colonne **Expression**. Sélectionnez ensuite **existent tel que** dans la colonne **Opérateur**.

   ![](assets/query_recipients_2.png)

1. Définissez la condition de filtrage suivante pour cibler votre diffusion. Sélectionnez **[!UICONTROL Nom interne]** dans la colonne Expression et **[!UICONTROL égal à]** dans la colonne Opérateur.
1. Dans la colonne de la valeur, ajoutez le nom interne de la diffusion ciblée.

   ![](assets/query_recipients_3.png)

1. Répétez les mêmes opérations pour cibler d&#39;autres diffusions à l&#39;aide d&#39;un opérateur **[!UICONTROL ET]**.

   ![](assets/query_recipients_4.png)

Votre transition sortante contient les destinataires dupliqués ciblés dans les diffusions.
