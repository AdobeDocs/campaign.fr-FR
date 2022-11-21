---
product: campaign
title: Diffusions cross-canal
description: En savoir plus sur les diffusions cross-canal
feature: Workflows, Channels Activity
exl-id: fedcffcd-cf9b-4c3d-bd25-cb87dda30192
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '273'
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

1. Ajoutez les conditions de filtrage à votre requête. Ici, nous allons sélectionner les destinataires ayant un numéro de mobile ou une adresse email.

   ![](assets/cross_channel_delivery_2.png)

1. Ajoutez une activité de **[!UICONTROL Partage]** à votre workflow pour diviser les destinataires ayant un numéro de mobile et ceux ayant une adresse email.
1. Dans l&#39;onglet **[!UICONTROL Diffusion]**, sélectionnez une diffusion pour chacune de vos cibles.

   Pour créer votre diffusion, procédez de la même manière qu&#39;avec un assistant de diffusion classique en double-cliquant sur l&#39;activité de diffusion de votre workflow. Pour plus d&#39;informations, reportez-vous à .

   ![](assets/cross_channel_delivery_3.png)

1. Pour éviter que les destinataires ne reçoivent trop de diffusion à la fois, ajoutez et configurez une activité **[!UICONTROL Attente]**.
1. Ajoutez une activité **[!UICONTROL Partage]** pour diviser les abonnés aux applications mobiles iOS ou Android.

   Sélectionnez un service pour chacun des systèmes d&#39;exploitation. Pour en savoir plus sur la création de service, reportez-vous à .

   ![](assets/cross_channel_delivery_4.png)

1. Sélectionnez et configurez une diffusion application mobile pour chacun des systèmes d&#39;exploitation.

   ![](assets/cross_channel_delivery_5.png)
