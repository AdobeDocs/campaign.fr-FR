---
title: Prise en main des API de Campaign
description: Prise en main des API de Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: 94fc2739c538f3aa8b11e0ea69d08f1bfffb5d32
workflow-type: tm+mt
source-wordcount: '330'
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

## Mécanisme d&#39;évaluation des API [!DNL Campaign]

Avec la base de données [!DNL Campaign] cloud, les appels unitaires d&#39;explosion ne sont pas recommandés en raison des performances (latence et simultanéité). L&#39;opération par lots est toujours préférable. Afin de garantir des performances optimales des API, Campaign gère toujours les appels API au niveau de la base de données locale.

![](../assets/do-not-localize/glass.png) [Le mécanisme d&#39;évaluation des API est présenté dans cette page](staging.md).

## Nouvelles API

De nouvelles API sont disponibles pour gérer la synchronisation des données entre la base de données [!DNL Campaign] locale et la base de données cloud. Un nouveau mécanisme a également été introduit pour gérer les appels API au niveau de la base de données locale afin d&#39;éviter la latence et d&#39;améliorer les performances globales.

![](../assets/do-not-localize/glass.png) [Les nouvelles API sont présentées dans cette page](new-apis.md).

**Rubriques connexes**

* [Bonnes pratiques relatives au modèle de données](datamodel-best-practices.md)
