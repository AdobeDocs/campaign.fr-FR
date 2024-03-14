---
title: Matrice de compatibilité de Campaign v8
description: Découvrez les systèmes et versions compatibles avec Campaign v8
feature: Release Notes
role: Admin
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9
source-git-commit: a779f243b0ba13dc3fcb7839377ca8766e5f7841
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 78%

---

# Matrice de compatibilité de Campaign v8 {#compat-matrix}

Ce document répertorie tous les systèmes et composants pris en charge pour la dernière version de la console cliente d’**Adobe Campaign v8**. Sauf mention contraire, toutes les versions mineures sont prises en charge. Les produits et versions ne faisant pas partie de cette liste ne sont pas compatibles avec Adobe Campaign.

Lorsque des versions spécifiques de ces systèmes et outils tiers arrivent en fin de vie (EOL), Adobe Campaign n&#39;est plus compatible avec celles-ci. Elles sont alors supprimées de cette matrice de compatibilité. Pour éviter tout problème, vérifiez que vous disposez des versions prises en charge des systèmes répertoriés dans la matrice de compatibilité.

>[!NOTE]
>
>Le serveur Adobe Campaign et la console cliente Campaign doivent se trouver sur la même version. [Découvrez comment vérifier votre version](upgrades.md#version).

## Console cliente {#ClientConsoleoperatingsystems}

Les systèmes d’exploitation et le navigateur ci-après sont nécessaires pour utiliser la console cliente Campaign. [En savoir plus](connect.md).

### Systèmes d’exploitation {#op-systems}

* **Microsoft Windows Server** 2019, 2016
* **Microsoft Windows** 11, 10

>[!NOTE]
>La version 32 bits de la console cliente est obsolète depuis la version 8.5. Depuis la version 8.6, la console cliente est uniquement disponible en 64 bits. Pour plus d’informations sur la mise à niveau de votre système d’exploitation, reportez-vous à cette [note technique](../../technotes/upgrades/console.md).

### Navigateur web {#web-browsers}

* **Microsoft Edge**

* Dernière version de **Microsoft Edge WebView2**. Téléchargez-le depuis le [site de Microsoft Developer](http://www.adobe.com/go/acc-ms-webview2-runtime-download_fr){target="_blank"}.

## Connecteurs CRM {#CRMconnectors}

Les systèmes de gestion de la relation client (CRM) compatibles avec Adobe Campaign sont répertoriés ci-dessous. En savoir plus sur les connecteurs CRM [dans cette page](../connect/crm.md).

* API du connecteur **Salesforce** version 49
* API web du connecteur **Microsoft Dynamics** : Dynamics 365 On-Premise et en ligne

## Federated Data Access (FDA){#FederatedDataAccessFDA}

Les bases de données externes compatibles avec le module Adobe Campaign Federated Data Access (FDA) sont répertoriées ci-dessous. En savoir plus sur FDA [dans cette page](../connect/fda.md).

* **[!DNL Amazon Redshift]**
* **[!DNL Azure Synapse]**, à partir de Campaign v8.5
* **[!DNL Google Big Query]**
* **[!DNL Snowflake]**
* **[!DNL Vertica]**

## SDK mobile {#MobileSDK}

Pour envoyer des [notifications push](../send/push.md) avec Campaign, vous pouvez utiliser le SDK mobile Adobe Experience Platform en configurant l’extension Adobe Campaign Classic dans l’interface utilisateur de collecte de données.

Les versions compatibles avec iOS et Android sont présentées dans la section [Documentation Adobe Developer](https://developer.adobe.com/client-sdks/home/){target="_blank"}.

## Interface utilisateur web {#web-ui}

Les navigateurs suivants sont compatibles avec l&#39;interface utilisateur web de Campaign. En savoir plus sur l’interface utilisateur web de Campaign [dans cette page](campaign-ui.md#ac-web-ui).

* **Microsoft Edge**, **Google Chrome**, **Safari** (versions les plus récentes)

## Accès web {#web-access}

Les navigateurs suivants sont compatibles avec Campaign for Web Access. En savoir plus sur l&#39;accès Web de Campaign [dans cette page](connect.md#web-access).

* **Microsoft Edge**, **Mozilla Firefox**, **Google Chrome**, **Safari** (dernières versions)

## Autres ressources {#support}

* [Mises à jour des versions de Campaign](upgrades.md)
* [Vérifier votre version de Campaign](upgrades.md#version)
* [Installer la console cliente Campaign](connect.md)
* [Versions du panneau de contrôle](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=fr){target="_blank"}.

Pour ne manquer aucune information sur les nouvelles versions de la solution Experience Cloud, abonnez-vous à la [Mise à jour produit prioritaire d’Adobe](https://www.adobe.com/fr/subscription/priority-product-update.html){target="_blank"}.