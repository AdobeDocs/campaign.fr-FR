---
title: Matrice de compatibilité de Campaign v8
description: Découvrez les systèmes et versions compatibles avec Campaign v8
feature: Overview
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
source-git-commit: 61222c2b05f1346bd2560ff17b225153edf9e91e
workflow-type: ht
source-wordcount: '385'
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

>[!NOTE]
>
>Veuillez noter que la version 32 bits de la console cliente sera abandonnée dans la version 8.5. À compter de la version 8.6, la console cliente sera uniquement disponible en 64 bits. Pour plus d’informations sur la mise à niveau de votre système d’exploitation, reportez-vous à cette [note technique](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/console.html?lang=fr).

### Systèmes d’exploitation{#op-systems}

* **Microsoft Windows Server** 2019, 2016, 2012
* **Microsoft Windows** 11, 10, 8

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

Pour envoyer des [notifications push](../send/push.md) avec Campaign, vous pouvez utiliser le SDK mobile Adobe Experience Platform en configurant l’extension Adobe Campaign Classic dans l’interface utilisateur de collecte de données.


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
