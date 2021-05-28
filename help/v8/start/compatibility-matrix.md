---
solution: Campaign v8
product: Adobe Campaign
title: Matrice de compatibilité de Campaign v8
description: Découvrez les systèmes et versions compatibles avec Campaign v8
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
source-git-commit: ffdfc9a2e1bec191b5a3cc7f7b40683b2456bf3e
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 75%

---

# Matrice de compatibilité de Campaign v8

Ce document répertorie tous les systèmes et composants pris en charge pour la dernière version d’**Adobe Campaign v8**. Les produits et versions ne faisant pas partie de cette liste ne sont pas compatibles avec Adobe Campaign.

>[!CAUTION]
>
>* Sauf mention contraire, toutes les versions mineures sont prises en charge.
>* Lorsque des versions spécifiques de ces systèmes et outils tiers arrivent en fin de vie (EOL), Adobe Campaign n’est plus compatible avec celles-ci. Elles sont alors supprimées de cette matrice de compatibilité. Pour éviter tout problème, vérifiez que vous disposez des versions prises en charge des systèmes répertoriés dans la matrice de compatibilité.


## Systèmes compatibles

### Console cliente{#ClientConsoleoperatingsystems}

Avertissement : les systèmes d’exploitation et le navigateur ci-après sont nécessaires pour utiliser la console cliente Campaign.

**Systèmes d’exploitation**

* **Microsoft Windows Server** 2016, 2012
* **Microsoft Windows** 8, 10 (recommandé pour les instances japonaises))

**Navigateur**

**Microsoft Internet Explorer** 11

### Connecteurs CRM{#CRMconnectors}

* API du connecteur **Salesforce** version 49
* API web du connecteur **Microsoft Dynamics** : Dynamics 365 local et en ligne

### Federated Data Access (FDA){#FederatedDataAccessFDA}

* **Amazon Redshift**
* **[!DNL Snowflake]**

### SDK Mobile{#MobileSDK}

* **Android** 7.x, 8.x, 9.0 avec SDK mobile version 1.0.27.
* **Apple iOS** 9 - 14 avec SDK mobile version 1.0.26, compatible avec les versions 32 et 64 bits.

### Navigateurs pris en charge {#Browsers}

Les navigateurs ci-après sont compatibles avec Campaign pour un accès à internet.

* **Microsoft Edge**, **Mozilla Firefox**, **Google Chrome**, **Safari** (dernières versions)

* **Internet Explorer** 11

## Comment vérifier votre version de Campaign

Utilisez le menu **Aide > À propos...** pour vérifier votre version.

![](assets/ac-version.png)

Vous accédez aux informations suivantes :

* Numéro **version** de la console cliente et du serveur applicatif. Dans l’exemple ci-dessus, la version est 8.1.5 pour la console cliente et le serveur d’applications.
* Numéro SHA, entre parenthèses.
* Un lien pour contacter l’assistance clientèle d’Adobe.
* Liens vers la Politique de confidentialité de l’Adobe, les Conditions d’utilisation et la Politique sur les cookies.
