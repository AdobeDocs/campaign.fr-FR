---
solution: Campaign v8
product: Adobe Campaign
title: Envoyer une notification push avec Adobe Campaign
description: Prise en main de la notification push dans Campaign
feature: Vue d'ensemble
role: Data Engineer
level: Beginner
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 22%

---

# Créer et envoyer des notifications push

Les diffusions d’applications mobiles vous permettent d’envoyer des notifications sur les systèmes iOS et Android.

Pour envoyer des notifications push dans Adobe Campaign, vous devez effectuer les opérations suivantes :

1. Configuration de votre environnement Campaign
1. Créez un service d’informations de type Application mobile pour votre application mobile.
1. Ajoutez, à ce service, les versions iOS et Android de l&#39;application.
1. Créez une diffusion pour iOS et Android.

:[!DNL :arrow_upper_right:] : Découvrez comment commencer à utiliser l’application mobile dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=fr)

## Intégration avec le SDK Adobe

### Intégration du SDK Campaign

Le SDK Campaign facilite l&#39;intégration de votre application mobile dans la plateforme Adobe Campaign.

:[!DNL :arrow_upper_right:] : Découvrez comment intégrer le SDK Campaign à votre application dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/integrating-campaign-sdk-into-the-mobile-application.html?lang=en#loading-campaign-sdk)

### Configuration de l’extension Campaign dans Launch

Vous pouvez intégrer le SDK Adobe Experience Platform Launch à Campaign en exploitant l’extension Campaign Classic.

:[!DNL :arrow_upper_right:] : En savoir plus dans la [documentation du SDK Mobile Adobe](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic)

## Configuration des paramètres de votre application dans Campaign

Vous devez définir les paramètres de vos applications iOS et Android dans Adobe Campaign.

:[!DNL :arrow_upper_right:] : Les instructions de configuration pour iOS sont présentées dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#sending-messages)

:[!DNL :arrow_upper_right:] : Les instructions de configuration pour Android sont détaillées dans [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=en#sending-messages)

## Créer votre première notification push

:[!DNL :arrow_upper_right:] : Découvrez comment créer vos premières notifications push dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/creating-notifications.html?lang=en#sending-notifications-on-ios)


>[!CAUTION]
>
>Avec l’enregistrement mobile de Campaign v8, il est désormais **asynchrone**. [En savoir plus](../dev/staging.md).
