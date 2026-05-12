---
title: Prise en main des API de Campaign
description: Prise en main des API de Campaign
feature: API
role: Developer
level: Intermediate, Experienced
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
TQID: https://experienceleague.adobe.com/pC27h6Z-J345l4XjFEOgwVTHtQSSRxJmtnWQ973SiPk
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b12f6872-9271-4369-85e5-86969a0b99a2
subfeature_v2: id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 320
ht-degree: 82%

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
* API génériques d’accès aux données pour interroger les données du modèle de données à l’aide de `queryDef` et de l’objet `NLWS`. Pour en savoir plus, consultez la section [Interroger la base de données avec queryDef](query-api.md).

Veuillez notez que dans son [déploiement Entreprise (FFDA)](../architecture/enterprise-deployment.md), Campaign fonctionne avec deux bases de données : une base de données locale pour la messagerie en temps réel de l’interface utilisateur et les requêtes et écritures unitaires à travers les API, et une base de données cloud pour l’exécution de campagnes, les rapports, l&#39;ingestion de données, les requêtes par lots et l’exécution de workflows.

>[!CAUTION]
>
>* Campaign v8.5.1 et les versions ultérieures ont apporté des modifications au processus d’authentification de Campaign v8. Les opérateurs ou opératrices techniques doivent utiliser Adobe Identity Management System (IMS) pour se connecter à Campaign. Découvrez comment migrer votre ou vos comptes techniques existants dans [cette note technique](../../technotes/upgrades/ims-migration.md).
>
>* [!DNL Adobe Campaign] v8 est fourni avec une limite au niveau du débit (TPS) de notre calque API. Le fait de rompre la limite entraîne une erreur HTTP standard (429). En tant qu&#39;utilisateur Managed Cloud Services, vous pouvez contacter Adobe pour adapter le contrôle de flux de chaque API.
> 

## Conditions préalables requises {#ac-api-prerequisites}

Avant d&#39;utiliser les API [!DNL Adobe Campaign], il est conseillé de posséder des notions sur les sujets suivants :

* JavaScript
* protocole SOAP
* Modèle de données [!DNL Adobe Campaign]

Pour utiliser les API et interagir avec [!DNL Adobe Campaign], vous devez également connaître votre modèle de données.

>[!NOTE]
>Vous pouvez générer une description complète de votre modèle de données. En savoir plus à ce propos sur [cette page](datamodel.md).


**Rubriques connexes :**

<!-- * [Query the database with queryDef](query-api.md)-->
* [Bonnes pratiques relatives au modèle de données](datamodel-best-practices.md)
* [Documentation JSAPI Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html?lang=fr){target="_blank"}
