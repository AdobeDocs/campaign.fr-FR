---
product: campaign
title: SpamAssassin
description: Découvrez comment configurer la détection des messages indésirables avec SpamAssassin
feature: Email, Deliverability
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 8be6836d-f7dc-4199-b2b2-b6a9cac9d162
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: 50d1fd2e-0fc9-5627-bbc9-02dbc9d15e08
    internal-label: Email
  - id: 63876777-85c3-57e1-a2da-81f02956c63c
    internal-label: Deliverability
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 92%
---
# SpamAssassin{#spamassassin}

Adobe Campaign peut être configuré pour fonctionner avec [SpamAssassin](https://spamassassin.apache.org){target="_blank"}, service tiers destiné à filtrer les e-mails indésirables. Cela permet d’attribuer un score aux e-mails afin de déterminer si un message risque d’être considéré comme indésirable par les outils anti-spams utilisés à sa réception.

SpamAssassin utilise diverses techniques de détection des emails indésirables, notamment :

* la détection des emails indésirables basée sur une somme de contrôle approximative et DNS,
* le filtrage bayésien,
* les programmes externes,
* Listes bloquées
* les bases de données en ligne.

>[!NOTE]
>
>SpamAssassin doit être installé et configuré sur le serveur d&#39;application d&#39;Adobe Campaign. Pour plus d&#39;informations, contactez votre représentant Adobe.
>
>Les règles qui déterminent si un élément est indésirable ou non sont gérées par SpamAssassin et peuvent être éditées par un administrateur disposant de privilèges.

## Utilisation de SpamAssassin dans Campaign {#using-spamassassin}

Une fois que vous avez créé votre email et défini son contenu, suivez les étapes ci-après pour évaluer les risques.

La création et la conception d&#39;une diffusion sont présentées dans cette [page](defining-the-email-content.md).


1. Accédez à l&#39;onglet **[!UICONTROL Aperçu]**.
1. Sélectionnez un destinataire pour prévisualiser votre diffusion.

   ![](assets/s_tn_del_preview_spamassassin_recipient.png)

   >[!NOTE]
   >
   >Si vous ne sélectionnez pas de destinataire, la vérification anti-spam ne peut pas être effectuée.

1. Un message d’avertissement fournit le résultat du test. Si un risque élevé est détecté, le message d’avertissement suivant est affiché :

   ![](assets/s_tn_del_preview_spamassassin_ko.png)

1. Cliquez sur le lien **[!UICONTROL Détail...]** situé en regard de l&#39;avertissement.
1. Sélectionnez l&#39;onglet **[!UICONTROL Vérification anti-spam]**.
1. Accédez à la section **[!UICONTROL Points / Règle / Description]** pour découvrir les raisons de ce risque.

   ![](assets/s_tn_del_msg_spamassassin_ko.png)

>[!NOTE]
>
>Chaque fois que vous cliquez sur **[!UICONTROL Vérification anti-spam]**, le service SpamAssassin est appelé et le message est réanalysé pour la détection des e-mails indésirables. Veillez à modifier votre contenu avant de réexécuter l’analyse anti-spam.
