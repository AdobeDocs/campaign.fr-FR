---
title: Prise en main des messages
description: Prise en main des messages
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
source-git-commit: 7234ca65f785b005b11851a5cd88add8cddeff4f
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 99%

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

   ![](../assets/do-not-localize/book.png) Découvrez comment envoyer des messages dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html?lang=fr){target=&quot;_blank&quot;}

* Envoyer des messages associés à une [campagne marketing](campaigns.md)

   ![](assets/deliveries-in-a-campaign.png)

   ![](../assets/do-not-localize/book.png) Découvrez comment envoyer des messages dans le contexte d&#39;une campagne dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html?lang=fr){target=&quot;_blank&quot;}

* Envoyer des messages via un [workflow](../config/workflows.md)

   ![](assets/send-in-a-wf.png)

   ![](../assets/do-not-localize/book.png) Découvrez comment automatiser les diffusions par e-mail dans la documentation de [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/delivery.html?lang=fr){target=&quot;_blank&quot;}

* [Déclencher des messages](../send/transactional.md) à partir d&#39;un événement
   ![](../assets/do-not-localize/book.png) [Cas pratique : découvrez comment envoyer un e-mail transactionnel avec une pièce jointe](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/transactional-email-with-attachments.html?lang=fr){target=&quot;_blank&quot;}

* Planifier vos messages

   ![](assets/schedule-send.png)

   ![](../assets/do-not-localize/book.png) [Cas pratique : découvrez comment planifier et envoyer un e-mail d&#39;anniversaire](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?lang=fr){target=&quot;_blank&quot;}


## Ajout de personnalisation

Les messages diffusés par Adobe Campaign peuvent être personnalisés de différentes façons.

Vous pouvez ainsi :

* Insérer des champs de personnalisation dynamiques.
   ![](../assets/do-not-localize/book.png) Découvrez comment utiliser les champs de personnalisation dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html?lang=fr).{target=&quot;_blank&quot;}
* insérer des blocs de personnalisation prédéfinis ;
   ![](../assets/do-not-localize/book.png) Découvrez en quoi consiste un bloc de personnalisation ainsi que son fonctionnement dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-blocks.html?lang=fr){target=&quot;_blank&quot;}
* Créer du contenu conditionnel.
   ![](../assets/do-not-localize/book.png) Découvrez comment insérer du contenu conditionnel dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/conditional-content.html?lang=fr).{target=&quot;_blank&quot;}

## Envoi de messages transactionnels

La messagerie transactionnelle (Message Center) est le module de Campaign conçu pour gérer les messages de déclenchement.

![](../assets/do-not-localize/glass.png) En savoir plus sur la fonctionnalité de messages transactionnels dans [cette section](../dev/architecture.md#transac-msg-archi).

![](../assets/do-not-localize/glass.png) Retrouvez les détails des étapes de configuration et d&#39;envoi de messages transactionnels sur [cette page](../send/transactional.md).

![](../assets/do-not-localize/book.png) Découvrez cette fonctionnalité à travers un cas d&#39;utilisation complet dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/transactional-email-with-attachments.html?lang=fr).{target=&quot;_blank&quot;}

## Logs de tracking et de diffusion

La surveillance de vos diffusions après leur envoi est une étape clé pour vous assurer que vos campagnes marketing sont efficaces et atteignent vos clients. Vous pouvez ainsi surveiller une diffusion après son envoi et comprendre la gestion des diffusions en échec et des quarantaines.

![](../assets/do-not-localize/book.png) Découvrez comment surveiller vos diffusions dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=fr#sending-messages){target=&quot;_blank&quot;}


**Rubriques connexes** dans la documentation de Campaign Classic v7 :

* [Bonnes pratiques de diffusion](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=fr){target=&quot;_blank&quot;}

* [Test et envoi d’un e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html){target=&quot;_blank&quot;}

* [Envoi de bons à tirer](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=fr){target=&quot;_blank&quot;}
