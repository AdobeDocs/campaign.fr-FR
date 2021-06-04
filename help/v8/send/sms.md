---
product: Adobe Campaign
title: Envoi de SMS avec Adobe Campaign
description: Prise en main des SMS dans Campaign
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
source-git-commit: 35814053bff993d0b130bf598c8601c3f5adc407
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 41%

---

# Création et envoi de SMS

Utilisez Adobe Campaign pour envoyer des messages SMS personnalisés.

[!DNL :arrow_upper_right:] Découvrez comment commencer à utiliser le canal SMS dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-channel.html?lang=fr)

>[!NOTE]
>
>Adobe Campaign vous permet également d’envoyer des notifications push sur les mobiles, via son option **Adobe Campaign Mobile App Channel (NMAC)**. En savoir plus dans [cette section](push.md).

## Configurer le canal SMS

Pour diffuser vers un téléphone mobile, vous devez avoir :

* un compte externe spécifiant un connecteur et un type de message,

* un modèle de diffusion dans lequel est référencé ce compte externe.

[!DNL :arrow_upper_right:]  Découvrez comment configurer un canal SMS dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=fr#sending-messages)

Avant d’envoyer des SMS :

* Assurez-vous que les profils des destinataires contiennent au moins un téléphone portable.
* Examinez les [bonnes pratiques de diffusion](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=fr#sending-messages) d’Adobe Campaign Classic qui s’appliquent également à Campaign v8.

De plus, vous devez connaître le protocole et les paramètres SMS. Parcourez la configuration de la connexion entre Adobe Campaign et un fournisseur SMPP dans [ce document](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html?lang=fr#sending-messages).

## Créer votre première diffusion SMS

1. Pour créer une nouvelle diffusion, accédez à l&#39;onglet **[!UICONTROL Campagnes]**, cliquez sur **[!UICONTROL Diffusions]** et cliquez sur le bouton **[!UICONTROL Créer]** au-dessus de la liste des diffusions existantes.

   ![](assets/delivery_step_1.png)

   [!DNL :arrow_upper_right:] Pour plus d&#39;informations sur la création d&#39;une diffusion, reportez-vous à la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=fr#sending-messages).

1. Sélectionnez un modèle de diffusion référençant le compte externe approprié pour envoyer les diffusions SMS.

   ![](assets/sms-template-list.png)

   [!DNL :arrow_upper_right:] Découvrez comment créer un compte externe SMPP dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#creating-an-smpp-external-account)

   [!DNL :arrow_upper_right:] Découvrez comment créer un modèle de diffusion à diffuser vers mobiles dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#changing-the-delivery-template)

1. Identifiez votre diffusion avec un libellé, un code et une description.

1. Cliquez sur **[!UICONTROL Continuer]** pour confirmer et afficher la fenêtre de configuration du message.

1. Saisissez le contenu du message dans la section **[!UICONTROL Contenu texte]** de l&#39;assistant, y compris les champs de personnalisation si nécessaire.

   ![](assets/sms-content.png)

1. Choisir la population cible.

Les étapes clés de création et de conception d&#39;un SMS sont présentées dans la documentation de Campaign Classic v7 :

* créer un SMS ;

   [!DNL :arrow_upper_right:] [Découvrez comment créer une diffusion SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#sending-messages)

* Concevoir le contenu du SMS

   [!DNL :arrow_upper_right:] [Découvrez comment définir le contenu du SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#defining-the-sms-content)

* Sélectionner l&#39;audience de votre email

   [!DNL :arrow_upper_right:] [Découvrez comment définir la population cible](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html?lang=fr)

[!DNL :bulb:] Les étapes de définition d’une audience sont présentées dans  [cette page](../start/audiences.md).

## Tester votre SMS

Pour visualiser le rendu du message avec sa personnalisation, cliquez sur **[!UICONTROL Aperçu]** et sélectionnez un destinataire.

![](assets/sms-preview.png)

Pour envoyer un BAT, reportez-vous aux sections suivantes de la documentation de Campaign Classic v7 :

* Valider une diffusion et envoyer des BAT
   [!DNL :arrow_upper_right:] [Découvrez les étapes clés de validation d&#39;une diffusion](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=fr)
* Ajouter des adresses de contrôle
   [!DNL :arrow_upper_right:] [En savoir plus sur les adresses de contrôle](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html?lang=fr)

## Envoi et surveillance des diffusions SMS

Les étapes clés d&#39;envoi et de surveillance d&#39;un SMS sont présentées dans la documentation de Campaign Classic v7 :

* Envoi, surveillance et suivi  de diffusions par SMS

   [!DNL :arrow_upper_right:] [En savoir plus sur les outils d’envoi, de surveillance et de suivi des SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-send.html?lang=en#sending-messages)
* Résolution des problèmes de diffusions SMS

   [!DNL :arrow_upper_right:] [En savoir plus sur le dépannage des SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/troubleshooting-sms.html?lang=en#sending-messages)
