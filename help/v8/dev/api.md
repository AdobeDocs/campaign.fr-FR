---
title: Prise en main des API de Campaign
description: Prise en main des API de Campaign
feature: API
role: Developer
level: Intermediate, Experienced
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: 26fededf0ee83299477e45e891df30a46c6d40fe
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 79%

---

# Prise en main des [!DNL Campaign] API {#gs-ac-api}

[!DNL Adobe Campaign] comprend un ensemble de fonctions JavaScript que vous pouvez utiliser :

* dans les scripts, dans des workflows [!DNL Adobe Campaign]
* via les API, à partir de systèmes externes

>[!NOTE]
>
>Selon votre modèle de déploiement, vous pouvez également utiliser des API REST avec Campaign v8. [En savoir plus](../dev/api/get-started-apis.md).

Vous pouvez utiliser les [API JavaScript de Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html?lang=fr){target="_blank"} pour écrire dans la base de données cloud de Campaign ou lire à partir de la base de données :

* API spécifiques à l&#39;entreprise qui vous permettent d&#39;agir sur chaque objet : diffusions, workflows, abonnements, etc. Apprenez-en davantage en consultant la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html?lang=fr){target="_blank"}.
* API génériques d&#39;accès aux données pour interroger les données du modèle de données à l&#39;aide des méthodes queryDef et NLWS. Pour en savoir plus, consultez la section [Interroger la base de données avec queryDef](query-api.md).

Veuillez notez que dans son [déploiement Entreprise (FFDA)](../architecture/enterprise-deployment.md), Campaign fonctionne avec deux bases de données : une base de données locale pour la messagerie en temps réel de l’interface utilisateur et les requêtes et écritures unitaires à travers les API, et une base de données cloud pour l’exécution de campagnes, les rapports, l&#39;ingestion de données, les requêtes par lots et l’exécution de workflows.

>[!CAUTION]
>
>* Campaign v8.5.1 et les versions ultérieures ont apporté des modifications au processus d’authentification de Campaign v8. Les opérateurs ou opératrices techniques doivent utiliser Adobe Identity Management System (IMS) pour se connecter à Campaign. Découvrez comment migrer votre ou vos comptes techniques existants dans [cette note technique](../../technotes/upgrades/ims-migration.md).
>
>* [!DNL Adobe Campaign] v8 est fourni avec une limite au niveau du débit (TPS) de notre calque API. Le fait de rompre la limite entraîne une erreur HTTP standard (429). En tant qu&#39;utilisateur Managed Cloud Services, vous pouvez contacter Adobe pour adapter le contrôle de flux de chaque API.
> 

## Conditions préalables {#ac-api-prerequisites}

Avant d&#39;utiliser les API [!DNL Adobe Campaign], il est conseillé de posséder des notions sur les sujets suivants :

* JavaScript
* Protocole SOAP
* Modèle de données [!DNL Adobe Campaign]

Pour utiliser les API et interagir avec [!DNL Adobe Campaign], vous devez également connaître votre modèle de données.

>[!NOTE]
>Vous pouvez générer une description complète de votre modèle de données. Apprenez-en davantage en consultant [cette page](datamodel.md).


**Rubriques connexes**

* [Interroger la base de données avec queryDef](query-api.md)
* [Bonnes pratiques relatives au modèle de données](datamodel-best-practices.md)
* [Documentation JSAPI Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html?lang=fr){target="_blank"}
