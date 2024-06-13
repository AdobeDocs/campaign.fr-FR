---
title: Prise en main des API de Campaign
description: Prise en main des API de Campaign
feature: API
role: Developer
level: Intermediate, Experienced
exl-id: 50e21acd-d23d-4fdd-a8aa-23c3f209bda3
source-git-commit: 07e85c2933194a24b4275519dd7da9c3226f6a3c
workflow-type: ht
source-wordcount: '282'
ht-degree: 100%

---

# Prise en main des [!DNL Campaign] API {#gs-ac-api}

[!DNL Adobe Campaign] comprend un ensemble de fonctions JavaScript que vous pouvez utiliser :

* dans les scripts, dans des workflows [!DNL Adobe Campaign]
* via les API, à partir de systèmes externes

Vous pouvez utiliser des API JavaScript pour écrire dans la base de données cloud de Campaign ou lire à partir de la base de données :

* API spécifiques à l&#39;entreprise qui vous permettent d&#39;agir sur chaque objet : diffusions, workflows, abonnements, etc. Apprenez-en davantage en consultant la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html?lang=fr){target="_blank"}.
* API génériques d’accès aux données pour interroger les données du modèle de données. Apprenez-en davantage en consultant la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html?lang=fr){target="_blank"}.

Veuillez notez que dans son [déploiement Entreprise (FFDA)](../architecture/enterprise-deployment.md), Campaign fonctionne avec deux bases de données : une base de données locale pour la messagerie en temps réel de l’interface utilisateur et les requêtes et écritures unitaires à travers les API, et une base de données cloud pour l’exécution de campagnes, les rapports, l&#39;ingestion de données, les requêtes par lots et l’exécution de workflows.

>[!CAUTION]
>
>* En tant qu’utilisateur ou utilisatrice Campaign ayant effectué la transition depuis Campaign Standard, vous pouvez utiliser les API REST avec Campaign v8. [En savoir plus](https://experienceleague.adobe.com/fr/docs/experience-cloud/campaign/apis/get-started-apis){target="_blank"}.
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

* [Bonnes pratiques relatives au modèle de données](datamodel-best-practices.md)
