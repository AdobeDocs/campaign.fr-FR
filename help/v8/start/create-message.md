---
solution: Campaign
product: Adobe Campaign
title: Prise en main des messages
description: Prise en main des messages
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
exl-id: 6cf8a929-637e-4e51-9160-5980ca727efb
translation-type: tm+mt
source-git-commit: 3fe4156149e9ff8724dd1ff5fc17b538e6055ef8
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 23%

---

# Commencer avec des messages {#gs-ac-audiences}

Avec Adobe Campaign, vous pouvez réaliser des campagnes cross-canal, y compris sous forme d&#39;emails, SMS, messages LINE, notifications push et courrier, et mesurer leur efficacité à l&#39;aide de différents rapports dédiés. Ces messages sont conçus et envoyés à l&#39;aide de diffusions, et peuvent être personnalisés pour chaque destinataire.

Les principales fonctionnalités comprennent le ciblage, la définition et la personnalisation des messages, l&#39;exécution des communications et les rapports opérationnels connexes. Le principal point d&#39;accès fonctionnel est l&#39;assistant de diffusion. Ce point d&#39;accès permet d&#39;accéder à de multiples fonctionnalités proposées par Adobe Campaign.

Découvrez les étapes clés pour créer une diffusion dans [la documentation du Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html).

Adobe Campaign v8 est fourni avec les canaux de diffusion suivants :

* **Canal email** : les diffusions email permettent d&#39;adresser des messages électroniques personnalisés à la population cible. En savoir plus sur [cette page](../send/email.md).

* **Canal courrier** : les diffusions courrier permettent de générer un fichier d&#39;extraction contenant les données relatives à la population cible.  En savoir plus sur [cette page](../send/direct-mail.md)

* **Canal** mobile : Les diffusions sur les canaux mobiles vous permettent d&#39;envoyer des SMS personnalisés à la population cible.  En savoir plus sur [cette page](../send/sms.md)

* **Canal** d&#39;application mobile : les diffusions d’applications mobiles vous permettent d’envoyer des notifications aux systèmes iOS et Android.  En savoir plus sur [cette page](../send/push.md)

* **Canal** DE LIGNE : Les diffusions LINE vous permettent d&#39;envoyer des messages sur LINE, une application de messagerie instantanée disponible sur tous les smartphones. En savoir plus sur [cette page](../send/line.md)

## Choisir comment envoyer vos messages

Une fois votre message créé et son contenu conçu et testé, vous pouvez choisir comment l’envoyer. Campaign offre un ensemble de fonctionnalités pour :

* Envoyer des messages manuellement à la cible principale
:flèche_supérieur_droite : [Découvrez comment envoyer des messages](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)
* Envoyer des messages associés à une [campagne marketing](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html)
:flèche_supérieur_droite : [Découvrez comment envoyer des messages dans le contexte d&#39;une campagne](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html).
* Envoyer des messages via un [workflow](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html)
:flèche_supérieur_droite : [Découvrez comment automatiser les diffusions de courriel](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/delivery.html)
* [Déclenchez ](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html) les messages d&#39;un événement : flèche_supérieur_droite :  [Cas d’utilisation : apprendre à envoyer un courrier électronique transactionnel avec une pièce jointe](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html)
* Planification de vos messages
:flèche_supérieur_droite : [Cas d&#39;utilisation : découvrez comment planifier et envoyer un courriel d&#39;anniversaire ](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html?)


## Personnalisation des Ajoutes

Les messages envoyés par Adobe Campaign peuvent être personnalisés de différentes manières.

Vous pouvez ainsi :

* Insérer des champs de personnalisation dynamiques.
:flèche_supérieur_droite : Découvrez comment utiliser les champs de personnalisation dans [la documentation du Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html)
* Insérer des blocs de personnalisation prédéfinis.
:flèche_supérieur_droite : Découvrez ce qu&#39;est un bloc de personnalisation et comment l&#39;utiliser dans [la documentation du Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-blocks.html)
* Créer du contenu conditionnel.
:flèche_supérieur_droite : Découvrez comment insérer du contenu conditionnel dans la [documentation du Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/conditional-content.html)

## Envoyer des messages transactionnels

La messagerie transactionnelle (Centre de messages) est le module Campaign conçu pour gérer les messages de déclenchement.

: bulb: Pour en savoir plus sur la fonctionnalité de messages transactionnels, consultez [cette section](../dev/architecture.md#transac-msg-archi)

: bulb: Les étapes de configuration et d&#39;envoi de messages transactionnels sont détaillées dans [cette page](../send/transactional.md).

:flèche_supérieur_droite : Découvrez cette fonctionnalité dans un cas d’utilisation de bout en bout dans [la documentation du Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/use-case/transactional-email-with-attachments.html?lang=en#transactional-messaging)

## Diffusion et logs de tracking

La surveillance de vos diffusions après leur envoi est une étape clé pour vous assurer que vos campagnes marketing sont efficaces et atteignent vos clients. Vous pouvez surveiller après avoir envoyé une diffusion et comprendre comment les échecs de diffusion et les quarantaines sont gérés.

:flèche_supérieur_droite : [Découvrez comment surveiller vos diffusions dans cette section](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=en#sending-messages)


**Rubriques connexes :**

:flèche_supérieur_droite :  [Meilleures pratiques de Diffusion](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html)

:flèche_supérieur_droite :  [Testez et envoyez un e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/sending-messages.html)

:flèche_supérieur_droite :  [Envoyer des BAT](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)
