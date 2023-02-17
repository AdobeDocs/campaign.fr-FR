---
title: Matrice de compatibilité de Campaign v8
description: Découvrez les systèmes et versions compatibles avec Campaign v8
feature: Overview
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
source-git-commit: 90dde8bb3bde4893971a2f364aa636ade6fff10f
workflow-type: ht
source-wordcount: '367'
ht-degree: 100%

---

# Matrice de compatibilité de Campaign v8

Ce document répertorie tous les systèmes et composants pris en charge pour la dernière version d&#39;**Adobe Campaign v8**. Sauf mention contraire, toutes les versions mineures sont prises en charge. Les produits et versions ne faisant pas partie de cette liste ne sont pas compatibles avec Adobe Campaign.

Lorsque des versions spécifiques de ces systèmes et outils tiers arrivent en fin de vie (EOL), Adobe Campaign n&#39;est plus compatible avec celles-ci. Elles sont alors supprimées de cette matrice de compatibilité. Pour éviter tout problème, vérifiez que vous disposez des versions prises en charge des systèmes répertoriés dans la matrice de compatibilité.

>[!NOTE]
>
>Adobe Campaign Server et la console cliente doivent se trouver sur la même version. [Découvrez comment vérifier votre version](#version).

## Console cliente{#ClientConsoleoperatingsystems}

Les systèmes d’exploitation et le navigateur ci-après sont nécessaires pour utiliser la console cliente Campaign. [En savoir plus](connect.md).

### Systèmes d’exploitation{#op-systems}

* **Microsoft Windows Server** 2019, 2016, 2012
* **Microsoft Windows** 11, 10, 8

>[!NOTE]
>
>Microsoft Windows 10 est recommandé pour les instances japonaises.

### Navigateur web{#web-browsers}

* **Microsoft Edge**

* Dernière version de **Microsoft Edge WebView2**. Téléchargez-le depuis le [site de Microsoft Developer](http://www.adobe.com/go/acc-ms-webview2-runtime-download_fr){target="_blank"}.

## Connecteurs CRM{#CRMconnectors}

Les systèmes de gestion de la relation client (CRM) compatibles avec Adobe Campaign sont répertoriés ci-dessous. [En savoir plus](../connect/crm.md).

* API du connecteur **Salesforce** version 49
* API web du connecteur **Microsoft Dynamics** : Dynamics 365 On-Premise et en ligne

## Federated Data Access (FDA){#FederatedDataAccessFDA}

Les bases de données externes compatibles avec le module Adobe Campaign Federated Data Access (FDA) sont répertoriées ci-dessous. [En savoir plus](../connect/fda.md).

* **Amazon Redshift**
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**

## SDK mobile{#MobileSDK}

Vous pouvez utiliser Campaign pour envoyer des [notifications push](../send/push.md) sur les systèmes d’exploitation répertoriés ci-dessous, à l’aide du SDK mobile associé.

* **Android** 12., 9.0, 8.x, 7 avec le SDK Android de Campaign version 1.1.1.
* **Apple iOS** 9 - 16 avec le SDK iOS de Campaign version 1.0.26, compatible avec les versions 32 et 64 bits. Apple iOS 16 est pris en charge à partir de Campaign v8.4.


## Accès web{#web-access}

Les navigateurs ci-après sont compatibles avec Campaign pour l’[accès à Internet](connect.md#web-access).

* **Microsoft Edge**, **Mozilla Firefox**, **Google Chrome**, **Safari** (dernières versions)

## Comment vérifier la version    et le build de Campaign{#version}

Accédez au menu **Aide > À propos...** pour vérifier votre version.

![](assets/ac-version.png)

Vous accédez aux informations suivantes :

* Le numéro de **version** de la console cliente Campaign et du serveur d&#39;applications. Dans l&#39;exemple ci-dessus, la version est 8.1.5 pour la console cliente et le serveur d&#39;applications.
* Le numéro SHA, entre parenthèses.
* Un lien pour contacter l&#39;assistance clientèle d&#39;Adobe.
* Des liens vers la Politique de confidentialité, les Conditions d&#39;utilisation et la Politique relative aux cookies d&#39;Adobe.
