---
product: campaign
title: Diffusions cross-canal
description: En savoir plus sur les diffusions cross-canal
feature: Workflows, Channels Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: fedcffcd-cf9b-4c3d-bd25-cb87dda30192
TQID: 'https://experienceleague.adobe.com/hD15kwTxO1uHeIQjrozZmONmVWI5ZrMn40ORMwrGbf8'
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
  - id: bce277d1-7efa-48d8-9a1b-b588bb45ba1c
    internal-label: Channels Activity
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 100%
---
# Diffusions cross-canal{#cross-channel-deliveries}

Les diffusions cross-canal sont disponibles dans l&#39;onglet **[!UICONTROL Diffusions]** des activités d&#39;un [workflow de campagne](campaign-workflows.md).

Sélectionnez le modèle sur lequel vous souhaitez baser votre diffusion et définissez son contenu.

Vous pouvez définir la cible de votre diffusion en amont du workflow via les différentes activités de ciblages.

Dans l&#39;exemple ci-dessous, nous allons créer un workflow permettant d&#39;envoyer un e-mail ou un SMS aux abonnés aux notifications push, suivi d&#39;une notification push une semaine plus tard. Pour cela :

1. Créez une campagne.
1. Dans l&#39;onglet **[!UICONTROL Ciblage et workflows]** de votre campagne, ajoutez une activité **[!UICONTROL Requête]**.
1. Configurez votre requête : sélectionnez les destinataires abonnés aux notifications push comme dimension cible.

   >[!NOTE]
   >
   >Pour les notifications push, utilisez la dimension cible **applications abonnées**.

   ![](assets/cross_channel_delivery_1.png)

1. Ajoutez les conditions de filtre à votre requête. Ici, nous allons sélectionner les destinataires ayant un numéro de mobile ou une adresse e-mail.

   ![](assets/cross_channel_delivery_2.png)

1. Ajoutez une activité de **[!UICONTROL Partage]** à votre workflow pour diviser les destinataires ayant un numéro de mobile et ceux ayant une adresse email.
1. Dans l&#39;onglet **[!UICONTROL Diffusion]**, sélectionnez une diffusion pour chacune de vos cibles.

   Pour créer votre diffusion, procédez de la même manière qu’avec un assistant de diffusion classique en double-cliquant sur l’activité diffusion de votre workflow.

   ![](assets/cross_channel_delivery_3.png)

1. Pour éviter que les destinataires ne reçoivent trop de diffusion à la fois, ajoutez et configurez une activité **[!UICONTROL Attente]**.
1. Ajoutez une activité **[!UICONTROL Partage]** pour diviser les abonnés aux applications mobiles iOS ou Android.

   Sélectionnez un service pour chacun des systèmes d’exploitation.

   ![](assets/cross_channel_delivery_4.png)

1. Sélectionnez et configurez une diffusion pour application mobile pour chacun des systèmes d’exploitation.

   ![](assets/cross_channel_delivery_5.png)
