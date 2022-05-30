---
title: Prise en main des API de Campaign
description: Prise en main des API de Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 100%

---

# Prise en main des [!DNL Campaign] API{#gs-ac-api}

[!DNL Adobe Campaign] comprend un ensemble de fonctions JavaScript que vous pouvez utiliser :

* dans les scripts, dans des workflows [!DNL Adobe Campaign]
* via les API, à partir de systèmes externes

Vous pouvez utiliser des API JavaScript pour écrire dans la base de données cloud de Campaign ou lire à partir de la base de données :

* API spécifiques à l&#39;entreprise qui vous permettent d&#39;agir sur chaque objet : diffusions, workflows, abonnements, etc. Apprenez-en davantage en consultant la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html?lang=fr).
* API génériques d&#39;accès aux données pour interroger les données du modèle de données. Apprenez-en davantage en consultant la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html?lang=fr).

Campaign v8 fonctionne avec deux bases de données : une base de données locale pour la messagerie en temps réel et les requêtes unitaires de l&#39;interface utilisateur à travers les API, et une base de données Cloud pour l&#39;exécution de campagnes, le reporting, l&#39;ingestion de données, les requêtes par lots et l&#39;exécution de workflows.

>[!CAUTION]
>
>[!DNL Adobe Campaign] v8 est fourni avec une limite au niveau du débit (TPS) de notre calque API. Le fait de rompre la limite entraîne une erreur HTTP standard (429). En tant qu&#39;utilisateur Managed Cloud Services, vous pouvez contacter Adobe pour adapter le contrôle de flux de chaque API.

## Conditions préalables requises

Avant d&#39;utiliser les API [!DNL Adobe Campaign], il est conseillé de posséder des notions sur les sujets suivants :

* JavaScript
* Protocole SOAP
* Modèle de données [!DNL Adobe Campaign]

Pour utiliser les API et interagir avec [!DNL Adobe Campaign], vous devez également connaître votre modèle de données.

>[!NOTE]
>Vous pouvez générer une description complète de votre modèle de données. Apprenez-en davantage en consultant [cette page](datamodel.md).


**Rubriques connexes**

* [Bonnes pratiques relatives au modèle de données](datamodel-best-practices.md)