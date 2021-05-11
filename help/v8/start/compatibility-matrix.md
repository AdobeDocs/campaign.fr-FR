---
solution: Campaign
product: Adobe Campaign
title: Matrice de compatibilité Campaign v8
description: Apprenez les systèmes et les versions compatibles avec Campaign v8
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
translation-type: tm+mt
source-git-commit: 3419ede105f652f0a33362468a7d119687c078de
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 33%

---

# Matrice de compatibilité Campaign v8

Ce document liste tous les systèmes et composants pris en charge pour la dernière version de **Adobe Campaign v8**. Les produits et versions ne faisant pas partie de cette liste ne sont pas compatibles avec Adobe Campaign.

>[!CAUTION]
>
>* Sauf mention contraire, toutes les versions mineures sont prises en charge.
>* Comme des versions spécifiques de ces systèmes et outils tiers atteignent la fin de vie (EOL), Adobe Campaign ne sera plus compatible avec ces versions et sera supprimé de cette matrice de compatibilité. Pour éviter tout problème, vérifiez que vous disposez des versions prises en charge des systèmes répertoriés dans la matrice de compatibilité.


## Systèmes compatibles

### Connecteurs CRM{#CRMconnectors}

* **API** Salesforceconnector version 49
* **Microsoft** Dynamicsconnector, API Web : Dynamics 365 Sur site et en ligne

### Federated Data Access (FDA){#FederatedDataAccessFDA}

* **Microsoft Azure Synapse Analytics**
* **Amazon Redshift**
* **[!DNL Snowflake]**
* **Oracle** 19c, 18c, 12c, 11G
* **PostgreSQL** 12.x, 11.x, 10.x, 9.6.x, 9.5.x, 9.4.x
* **Microsoft SQL Server** 2019, 2017, 2016, 2014, 2012 SP1 et SP2
* **MySQL** 5.7
* **Teradata** 16.20, 16, 15.10, 15.0
* **Netezza**  7.2
* **sybase IQ** 16, ASE 15.7
* **SAP** HANAversion 1 SPS 12
* **Hadoop via HiveSQL**
   * HortonWorks HDP 2.4.X, 2.5.x, 2.6.x
   * HDInsight 3.4 (HDP 2.4), 3.5 (HDP 2.5), 3.6 (HDP 2.6
   * Cloudera CDH6.x

### Console client{#ClientConsoleoperatingsystems}

:warning: Les systèmes d’exploitation et le navigateur suivants sont nécessaires pour utiliser Campaign Client Console.

**Systèmes d’exploitation**

* **Microsoft Windows Server** 2016, 2012
* **Microsoft Windows** 8, 10 (recommandé pour les instances japonaises)

**Navigateur**

Microsoft Internet Explorer 11

### SDK Mobile{#MobileSDK}

* **Android** 7.x, 8.x, 9.0 avec SDK mobile version 1.0.27.
* **Apple iOS** 9 - 14 avec SDK mobile version 1.0.26, compatible avec les versions 32 et 64 bits.

### Navigateurs pris en charge {#Browsers}

Les navigateurs suivants sont compatibles avec Campaign for Web Access.

* **Microsoft Edge**,  **Mozilla Firefox**,  **Google Chrome**,  **Safari**  (dernières versions)

* **Internet Explorer 11**

## Vérification de la version Campaign

Le menu **Aide > À propos de...** vous permet d’accéder aux informations suivantes :

* numéro de version de la console client Campaign et du serveur d’applications
* numéro de build pour la console client Campaign et le serveur d’applications
* lien pour contacter l&#39;Assistance clientèle d&#39;Adobe
* liens vers la Politique de confidentialité, les Conditions d&#39;utilisation et la Politique relative aux cookies d&#39;Adobe
