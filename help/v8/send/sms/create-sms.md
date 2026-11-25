---
title: Créer une diffusion SMS
description: Découvrez comment créer une diffusion SMS.
feature: SMS
role: User
level: Beginner, Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: 3b15eb3e-8625-4049-bf0d-327407ae5ea6
TQID: 'https://experienceleague.adobe.com/9hRirStfl9Rb2piTS3xY7C4Gb7zsUGeuoTxFFKgjf-8'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: b1bd1421-1927-4c59-9bc6-ce292360e43b
    internal-label: SMS Messaging
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: c4f3ffbf421621fa15b1b4d56480bd0ff9304254
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 61%
---
# Créer votre première diffusion SMS {#sms-delivery}

Pour créer une diffusion SMS, procédez comme suit :

1. Créez une diffusion et sélectionnez le [modèle de diffusion SMS](sms-mid-sourcing.md#sms-delivery-template) que vous avez créé pour vos envois de SMS.

   ![Liste des modèles de diffusion pour une nouvelle diffusion, avec le modèle SMS Envoyer aux mobiles (SMPP) en surbrillance](assets/sms_create.png){zoomable="yes"}

   Les étapes de création d&#39;une diffusion sont décrites dans la section [Création de votre première diffusion](../../start/create-message.md).

<!--
 * For standalone instance,  [learn more here](sms-standalone-instance.md#sms-delivery-template).
* For mid-sourcing infrastructure,
-->

1. Renommez votre diffusion dans le champ **[!UICONTROL Libellé]** et ajoutez des informations dans le champ **[!UICONTROL Code de diffusion]** et dans la liste **[!UICONTROL Nature]** si nécessaire pour le suivi. Vous pouvez également ajouter une **[!UICONTROL description]** à votre diffusion.

1. Cliquez sur le bouton **[!UICONTROL Continuer]**. Désormais, vous disposez de tous les paramètres de votre modèle dans votre diffusion.

1. Vous pouvez archiver le bouton **[!UICONTROL Propriétés]** qui est configuré selon vos besoins. [En savoir plus sur l’onglet SMS](sms-delivery-settings.md#sms-tab)

   ![Propriétés de la diffusion SMS avec l&#39;onglet Général, le champ Routage et l&#39;onglet SMS en surbrillance](assets/sms_settings.png){zoomable="yes"}

1. [Définissez le contenu](sms-content.md) de votre diffusion.

1. [Sélectionnner l’audience](sms-audience.md).

Les étapes de définition d&#39;une audience sont détaillées sur la page [Créer des audiences de profil dans Campaign](../../audiences/create-audiences.md).

## Valider et envoyer les SMS {#sms-validate}

Après la création de votre diffusion, vous pouvez effectuer les opérations suivantes :

1. [Envoyez des BAT](sms-proofs.md) pour valider le rendu et le contenu.

1. Ensuite, [envoyez à l’audience finale](sms-send.md).

## Surveiller et suivre les SMS {#sms-monitor}

Après l’envoi, [apprenez à surveiller et suivre vos SMS](sms-monitor.md).
