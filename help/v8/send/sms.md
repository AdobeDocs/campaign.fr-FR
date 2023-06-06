---
title: Envoi de SMS avec Adobe Campaign
description: Prise en main des SMS dans Campaign
feature: SMS
role: Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 65f4da979f0c5884797af0c3a835d948672b4a7c
workflow-type: ht
source-wordcount: '569'
ht-degree: 100%

---

# Création et envoi de SMS

Utilisez Adobe Campaign pour envoyer des messages SMS personnalisés.

![](../assets/do-not-localize/book.png) Découvrez comment commencer à utiliser le canal SMS dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-channel.html?lang=fr){target="_blank"}

>[!NOTE]
>
>Adobe Campaign permet également d&#39;envoyer des notifications push sur les mobiles, via son option **Canal des applications mobiles Adobe Campaign (NMAC)**. En savoir plus dans [cette section](push.md).

## Configurer le canal SMS

Pour diffuser vers un téléphone mobile, vous devez avoir :

* un compte externe spécifiant un connecteur et un type de message,

* un modèle de diffusion dans lequel est référencé ce compte externe.

![](../assets/do-not-localize/book.png) Découvrez comment configurer un canal SMS dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=fr#sending-messages){target="_blank"}

Avant d&#39;envoyer des SMS :

* Assurez-vous que les profils des destinataires contiennent au moins un téléphone portable.
* Examinez les [bonnes pratiques de diffusion](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=fr#sending-messages) d’Adobe Campaign Classic qui s’appliquent également à Campaign v8.{target="_blank"}

De plus, vous devez connaître le protocole et les paramètres SMS. Découvrez comment établir une connexion entre Adobe Campaign et un fournisseur SMPP dans [ce document](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html?lang=fr#sending-messages){target="_blank"}.

## Créer votre première diffusion par SMS

1. Pour créer une nouvelle diffusion, accédez à l&#39;onglet **[!UICONTROL Campagnes]**, cliquez sur **[!UICONTROL Diffusions]**, puis sur le bouton **[!UICONTROL Créer]** au-dessus de la liste des diffusions existantes.

   ![](assets/delivery_step_1.png)

   ’![](../assets/do-not-localize/book.png) Pour plus d’informations générales sur la création d&#39;une diffusion, consultez la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=fr#sending-messages){target="_blank"}.

1. Sélectionnez un modèle de diffusion référençant le compte externe approprié pour envoyer les diffusions SMS.

   ![](assets/sms-template-list.png)

   ![](../assets/do-not-localize/book.png) Découvrez comment créer un compte externe SMPP dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=fr#creating-an-smpp-external-account){target="_blank"}

   ![](../assets/do-not-localize/book.png) Découvrez comment créer un modèle de diffusion pour diffuser sur les mobiles dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=fr#changing-the-delivery-template){target="_blank"}

1. Identifiez votre diffusion avec un libellé, un code et une description.

1. Cliquez sur **[!UICONTROL Continuer]** pour valider et afficher la fenêtre de configuration du message.

1. Saisissez le contenu du message dans la section **[!UICONTROL Contenu texte]** de l&#39;assistant, y compris les champs de personnalisation si nécessaire.

   ![](assets/sms-content.png)

1. Choisir la population cible.

Les étapes clés de création et de conception d&#39;un SMS sont présentées dans la documentation de Campaign Classic v7 :

* Créer un SMS

   ![](../assets/do-not-localize/book.png) [Découvrez comment créer une diffusion SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=fr#sending-messages){target="_blank"}

* Concevoir le contenu du SMS

   ![](../assets/do-not-localize/book.png) [En savoir plus sur la définition du contenu SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=fr#defining-the-sms-content){target="_blank"}

* Sélectionner l&#39;audience de votre e-mail

   ![](../assets/do-not-localize/book.png) [En savoir plus sur la définition de la population cible](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html?lang=fr){target="_blank"}

![](../assets/do-not-localize/glass.png)Les étapes de définition de l&#39;audience sont décrites sur [cette page](../start/audiences.md).

## Tester votre SMS

Pour visualiser le rendu du message avec sa personnalisation, cliquez sur **[!UICONTROL Aperçu]** et sélectionnez un destinataire.

![](assets/sms-preview.png)

Pour envoyer un bon à tirer, reportez-vous aux sections suivantes de la documentation de Campaign Classic v7 :

* Valider une diffusion et envoyer des BAT
   ![](../assets/do-not-localize/book.png) [En savoir plus sur les étapes clés de validation d’une diffusion](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=fr){target="_blank"}
* Ajouter des adresses de contrôle
   ![](../assets/do-not-localize/book.png) [En savoir plus sur les adresses de contrôle](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html?lang=fr){target="_blank"}

## Envoyer et surveiller les diffusions par SMS

Les étapes clés d&#39;envoi et de surveillance d&#39;un SMS sont présentées dans la documentation de Campaign Classic v7 :

* Envoi, surveillance et suivi de diffusions par SMS

   ![](../assets/do-not-localize/book.png) [En savoir plus sur les outils d’envoi, de surveillance et de suivi des SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-send.html?lang=fr#sending-messages){target="_blank"}

* Dépanner les problèmes de diffusions par SMS

   ![](../assets/do-not-localize/book.png) [En savoir plus sur le dépannage des SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/troubleshooting-sms.html?lang=fr#sending-messages){target="_blank"}
