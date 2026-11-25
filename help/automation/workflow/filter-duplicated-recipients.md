---
product: campaign
title: Filtrer les destinataires en double
description: Découvrez comment filtrer les destinataires en double.
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: cfa1f45c-e1ac-4055-996c-6e8d041889bb
TQID: 'https://experienceleague.adobe.com/jwnm0saAGOFD4FjCniKHBm6xDd8H2QggSy3UvrMAb-E'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 72%
---
# Filtrer les destinataires en double {#filtering-duplicated-recipients}



Dans cet exemple, nous allons filtrer les destinataires qui apparaissent deux fois ou davantage dans une diffusion afin de récupérer les profils dupliqués.

Pour réaliser cet exemple, les étapes sont les suivantes :

1. Placez une activité **[!UICONTROL Requête]** dans un workflow, puis ouvrez-la.
1. Cliquez sur **[!UICONTROL Edition de la requête]** et définissez les dimensions de ciblage et de filtrage sur **[!UICONTROL Destinataires]**.

   ![Étape Dimension de ciblage et de filtrage de l&#39;activité Requête avec Destinataires sélectionnés, Conditions de filtrage mises en surbrillance.](assets/query_recipients_1.png)

1. Définissez la condition de filtrage suivante pour cibler les destinataires qui se trouvent dans le log de diffusion. Sélectionnez **Log de diffusion d&#39;un destinataire (broadlog)** dans la colonne **Expression**. Sélectionnez ensuite **existent tel que** dans la colonne **Opérateur**.

   ![Étape de filtrage avec la condition Logs de diffusion du destinataire (broadLog) et l&#39;opérateur existent, par exemple.](assets/query_recipients_2.png)

1. Définissez la condition de filtrage suivante pour cibler votre diffusion. Sélectionnez **[!UICONTROL Nom interne]** dans la colonne Expression et **[!UICONTROL égal à]** dans la colonne Opérateur.
1. Dans la colonne de la valeur, ajoutez le nom interne de la diffusion ciblée.

   ![Condition de filtrage sur le nom interne de la diffusion, égal à la valeur Summer_delivery_sales, sous existe tel que.](assets/query_recipients_3.png)

1. Répétez les mêmes opérations pour cibler d&#39;autres diffusions à l&#39;aide d&#39;un opérateur **[!UICONTROL ET]**.

   ![Il en existe deux, telles que les conditions jointes par Et, ciblant Summer_delivery_sales et Summer_delivery_new_collection.](assets/query_recipients_4.png)

Votre transition sortante contient les destinataires dupliqués ciblés dans les diffusions.
