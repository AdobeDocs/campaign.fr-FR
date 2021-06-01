---
product: Adobe Campaign
title: Prise en main des messages
description: Prise en main des messages
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 69%

---

# Prise en main des messages{#gs-ac-audiences}

Avec Adobe Campaign, vous pouvez envoyer des campagnes cross-canal, notamment des emails, des SMS, des notifications push et des courriers, et mesurer leur efficacité à l’aide de différents rapports dédiés. Ces messages sont conçus et envoyés par le biais de diffusions, et peuvent être personnalisés pour chaque destinataire.

Les principales fonctionnalités comprennent le ciblage, la définition et la personnalisation des messages, l’exécution des communications et les rapports opérationnels associés. Le principal point d’accès fonctionnel est l’assistant de diffusion. Ce point d’accès permet d’accéder à de multiples fonctionnalités proposées par Adobe Campaign.

Découvrez les étapes clés pour créer une diffusion dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=fr).

Adobe Campaign v8 propose les canaux de diffusion suivants :

* **Canal e-mail** : les diffusions e-mail permettent d’envoyer des e-mails personnalisés à la population cible. En savoir plus sur [cette page](../send/email.md).

* **Canal courrier** : les diffusions courrier permettent de générer un fichier d’extraction contenant les données relatives à la population cible.  En savoir plus sur [cette page](../send/direct-mail.md).

* **Canal mobile** : les diffusions sur canaux mobiles permettent d’envoyer des SMS ou des messages LINE personnalisés à la population cible.  En savoir plus sur [cette page](../send/sms.md).

* **Canal applications mobiles** : les diffusions d’applications mobiles vous permettent d’envoyer des notifications aux systèmes iOS et Android.  En savoir plus sur [cette page](../send/push.md).

<!--
* **LINE channel**: LINE deliveries let you send messages on LINE, an instant messaging application available on all smartphones. Learn more in [this page](../send/line.md)
-->

## Choisir comment envoyer vos messages

Une fois votre message créé et son contenu conçu et testé, vous pouvez choisir la façon dont vous souhaitez l’envoyer. Campaign offre un ensemble de fonctionnalités pour :

* Envoyer les messages manuellement à la cible principale
   [!DNL :arrow_upper_right:] [Découvrez comment envoyer des messages](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html?lang=fr)
* Envoyer des messages associés à une [campagne marketing](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=fr)
   [!DNL :arrow_upper_right:] [Découvrez comment envoyer des messages dans le cadre d’une campagne](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html?lang=fr).
* Envoyer des messages via un [workflow](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=fr)
   [!DNL :arrow_upper_right:] [Découvrez comment automatiser les diffusions email](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/delivery.html?lang=fr)
* [Déclencher des ](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html?lang=fr) messages à partir d’un événement
   [!DNL :arrow_upper_right:] [Cas pratique : découvrez comment envoyer un email transactionnel avec une pièce jointe](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html?lang=fr)
* Planification de vos messages
   [!DNL :arrow_upper_right:] [Cas pratique : découvrez comment planifier et envoyer un email d’anniversaire](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?lang=fr)


## Ajout de personnalisation

Les messages diffusés par Adobe Campaign peuvent être personnalisés de différentes façons.

Vous pouvez ainsi :

* Insérer des champs de personnalisation dynamiques.
   [!DNL :arrow_upper_right:] Découvrez comment utiliser les champs de personnalisation dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html?lang=fr)
* Insérer des blocs de personnalisation prédéfinis.
   [!DNL :arrow_upper_right:] Découvrez ce qu&#39;est un bloc de personnalisation et comment l&#39;utiliser dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-blocks.html?lang=fr)
* Créer du contenu conditionnel.
   [!DNL :arrow_upper_right:] Découvrez comment insérer du contenu conditionnel dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/conditional-content.html?lang=fr)

## Envoi de messages transactionnels

La messagerie transactionnelle (Message Center) est le module de Campaign conçu pour gérer les messages de déclenchement.

[!DNL :bulb:] En savoir plus sur la fonctionnalité des messages transactionnels dans  [cette section](../dev/architecture.md#transac-msg-archi)

[!DNL :bulb:] Les étapes de configuration et d&#39;envoi de messages transactionnels sont présentées dans  [cette page](../send/transactional.md)

[!DNL :arrow_upper_right:] Découvrez cette fonctionnalité dans un cas pratique de bout en bout de la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html?lang=fr#transactional-messaging)

## Logs de tracking et de diffusion

La surveillance de vos diffusions après leur envoi est une étape clé pour vous assurer que vos campagnes marketing sont efficaces et atteignent vos clients. Vous pouvez ainsi surveiller une diffusion après son envoi et comprendre la gestion des diffusions en échec et des quarantaines.

[!DNL :arrow_upper_right:] [Découvrez comment surveiller vos diffusions dans cette section](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=fr#sending-messages)


**Rubriques connexes**

[!DNL :arrow_upper_right:]  [Bonnes pratiques de diffusion](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=fr)

[!DNL :arrow_upper_right:]  [Tester et envoyer un email](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)

[!DNL :arrow_upper_right:]  [Envoi de BAT](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=fr)
