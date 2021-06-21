---
product: Adobe Campaign
title: Prise en main des messages
description: Prise en main des messages
feature: Vue d'ensemble
role: Data Engineer
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: 9cb1b38456601bce21d458fea42a5c112d9fafb4
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 97%

---

# Prise en main des messages{#gs-ac-audiences}

Avec Adobe Campaign, vous pouvez réaliser des campagnes cross-canal, y compris sous forme d&#39;e-mails, SMS, notifications push et courrier, et mesurer leur efficacité à l&#39;aide de différents rapports dédiés. Ces messages sont conçus et envoyés par le biais de diffusions, et peuvent être personnalisés pour chaque destinataire.

Les principales fonctionnalités comprennent le ciblage, la définition et la personnalisation des messages, l&#39;exécution des communications et les rapports opérationnels associés. Le principal point d&#39;accès fonctionnel est l&#39;assistant de diffusion. Ce point d&#39;accès permet d&#39;accéder à de multiples fonctionnalités proposées par Adobe Campaign.

Découvrez les principales étapes de création d&#39;une diffusion dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=fr).

Adobe Campaign v8 propose les canaux de diffusion suivants :

* **Canal e-mail** : les diffusions e-mail permettent d&#39;envoyer des e-mails personnalisés à la population cible. Apprenez-en davantage en consultant [cette page](../send/email.md).

* **Canal courrier** : les diffusions courrier permettent de générer un fichier d&#39;extraction contenant les données relatives à la population cible.  Apprenez-en davantage en consultant [cette page](../send/direct-mail.md).

* **Canal mobile** : les diffusions sur canaux mobiles permettent d&#39;envoyer des SMS ou des messages LINE personnalisés à la population cible.  Apprenez-en davantage en consultant [cette page](../send/sms.md).

* **Canal applications mobiles** : les diffusions d&#39;applications mobiles vous permettent d&#39;envoyer des notifications aux systèmes iOS et Android.  Apprenez-en davantage en consultant [cette page](../send/push.md).

<!--
* **LINE channel**: LINE deliveries let you send messages on LINE, an instant messaging application available on all smartphones. Learn more in [this page](../send/line.md)
-->

## Choisir comment envoyer vos messages

Une fois votre message créé et son contenu conçu et testé, vous pouvez choisir la façon dont vous souhaitez l&#39;envoyer. Campaign offre un ensemble de fonctionnalités pour :

* Envoyer les messages manuellement à la cible principale

   ![](assets/send-email.png)

   [!DNL :arrow_upper_right:] [Découvrez comment envoyer des messages](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html?lang=fr)
* Envoyer des messages associés à une [campagne marketing](campaigns.md)

   ![](assets/deliveries-in-a-campaign.png)

   [!DNL :arrow_upper_right:] [Découvrez comment envoyer des messages dans le cadre d&#39;une campagne](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html?lang=fr).
* Envoyer des messages via un [workflow](../config/workflows.md)

   ![](assets/send-in-a-wf.png)

   [!DNL :arrow_upper_right:] [Découvrez comment automatiser les diffusions par e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/delivery.html?lang=fr)
* [Déclencher des messages](../send/transactional.md) à partir d&#39;un événement
   [!DNL :arrow_upper_right:] [Cas pratique : découvrez comment envoyer un e-mail transactionnel avec une pièce jointe](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/transactional-email-with-attachments.html?lang=en)
* Planifier vos messages

   ![](assets/schedule-send.png)

   [!DNL :arrow_upper_right:] [Cas pratique : découvrez comment planifier et envoyer un e-mail d&#39;anniversaire](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?lang=fr)


## Ajout de personnalisation

Les messages diffusés par Adobe Campaign peuvent être personnalisés de différentes façons.

Vous pouvez ainsi :

* Insérer des champs de personnalisation dynamiques.
   [!DNL :arrow_upper_right:] Découvrez comment utiliser les champs de personnalisation dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html?lang=fr).
* Insérer des blocs de personnalisation prédéfinis.
   [!DNL :arrow_upper_right:] Découvrez en quoi consiste un bloc de personnalisation ainsi que son fonctionnement dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-blocks.html?lang=fr).
* Créer du contenu conditionnel.
   [!DNL :arrow_upper_right:] Découvrez comment insérer du contenu conditionnel dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/conditional-content.html?lang=fr).

## Envoi de messages transactionnels

La messagerie transactionnelle (Message Center) est le module de Campaign conçu pour gérer les messages de déclenchement.

[!DNL :bulb:] En savoir plus sur la fonctionnalité de messages transactionnels dans [cette section](../dev/architecture.md#transac-msg-archi).

[!DNL :bulb:] Retrouvez les détails des étapes de configuration et d&#39;envoi de messages transactionnels sur [cette page](../send/transactional.md).

[!DNL :arrow_upper_right:] Découvrez cette fonctionnalité à travers un cas d&#39;utilisation complet dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/transactional-email-with-attachments.html?lang=en).

## Logs de tracking et de diffusion

La surveillance de vos diffusions après leur envoi est une étape clé pour vous assurer que vos campagnes marketing sont efficaces et atteignent vos clients. Vous pouvez ainsi surveiller une diffusion après son envoi et comprendre la gestion des diffusions en échec et des quarantaines.

[[!DNL :arrow_upper_right:] Découvrez comment surveiller vos diffusions dans cette section](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=fr#sending-messages).


**Rubriques connexes**

[!DNL :arrow_upper_right:]  [Bonnes pratiques de diffusion](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=fr)

[  [!DNL :arrow_upper_right:]Test et envoi d&#39;un e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)

[!DNL :arrow_upper_right:]  [Envoi de BAT](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=fr)
