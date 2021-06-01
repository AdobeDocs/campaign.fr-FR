---
product: Adobe Campaign
title: Envoi de notification push avec Adobe Campaign
description: Prise en main des notifications push dans Campaign
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 72%

---

# Création et envoi de notifications push

Les diffusions d’applications mobiles vous permettent d’envoyer des notifications aux systèmes iOS et Android.

Pour envoyer des notifications push dans Adobe Campaign, vous devez effectuer les opérations suivantes :

1. Configuration de votre environnement Campaign
1. Créez un service d’information de type application mobile pour votre application mobile.
1. Ajoutez, à ce service, les versions iOS et Android de l&#39;application.
1. Créez une diffusion pour iOS et Android.

[!DNL :arrow_upper_right:] Découvrez comment commencer à utiliser les applications mobiles dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=fr)

## Intégration au SDK Adobe

### Intégration du SDK Campaign

Le SDK Campaign facilite l’intégration de votre application mobile à la plateforme Adobe Campaign.

[!DNL :arrow_upper_right:] Découvrez comment intégrer le SDK Campaign à votre application dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/integrating-campaign-sdk-into-the-mobile-application.html?lang=fr#loading-campaign-sdk)

### Configuration de l’extension Campaign dans Launch

Vous pouvez intégrer le SDK Adobe Experience Platorm Launch à Campaign à l’aide de l’extension Campaign Classic.

[!DNL :arrow_upper_right:] En savoir plus dans la documentation du SDK Mobile  [Adobe](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic)

## Configuration des paramètres de votre application dans Campaign

Vous devez définir les paramètres de vos applications iOS et Android dans Adobe Campaign.

[!DNL :arrow_upper_right:] Les instructions de configuration pour iOS sont présentées dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=fr#sending-messages)

[!DNL :arrow_upper_right:] Les instructions de configuration pour Android sont détaillées dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=fr#sending-messages)

## Création de votre première notification push

[!DNL :arrow_upper_right:] Découvrez comment créer vos premières notifications push dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/creating-notifications.html?lang=fr#sending-notifications-on-ios)


>[!CAUTION]
>
>Avec l’enregistrement mobile de Campaign v8, il est désormais **asynchrone**. [En savoir plus](../dev/staging.md).
