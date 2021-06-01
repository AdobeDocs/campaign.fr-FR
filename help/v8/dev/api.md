---
product: Adobe Campaign
title: Prise en main des API de Campaign
description: Prise en main des API de Campaign
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 18%

---

# Prise en main des [!DNL Campaign] API{#gs-ac-api}

[!DNL Adobe Campaign] s’accompagne d’un ensemble de fonctions JavaScript que vous pouvez utiliser :

* dans les scripts - dans les workflows [!DNL Adobe Campaign]
* via les API, à partir de systèmes externes

Vous pouvez utiliser des API JavaScript pour écrire dans la base de données cloud Campaign ou lire depuis la base de données :

* API spécifiques à l’entreprise qui vous permettent d’agir sur chaque objet : diffusions, workflows, abonnements, etc. Pour en savoir plus, consultez la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/business-oriented-apis.html?lang=fr).
* API génériques d’accès aux données pour interroger les données du modèle de données. Pour en savoir plus, consultez la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/api/data-oriented-apis.html?lang=fr).

Campaign v8 fonctionne avec deux bases de données : une base de données locale pour la messagerie en temps réel et les requêtes unitaires de l’interface utilisateur, et une base de données Cloud pour l’exécution de campagnes, le reporting, l’ingestion de données, les requêtes par lots et l’exécution de workflows.

>[!CAUTION]
>
>[!DNL Adobe Campaign] v8 est fourni avec une limite de débit (TPS) de notre couche API. Rompre la limite entraîne une erreur HTTP standard (429). En tant qu’utilisateur Cloud Services géré, vous pouvez contacter Adobe pour adapter le ralentissement de chaque API.


## Conditions préalables requises

Avant d’utiliser les API [!DNL Adobe Campaign], vous devez connaître les sujets suivants :

* JavaScript
* protocole SOAP
* [!DNL Adobe Campaign] datamodel

Pour utiliser les API et interagir avec [!DNL Adobe Campaign], vous devez également connaître votre modèle de données.

>[!NOTE]
>Vous pouvez générer une description complète de votre modèle de données. En savoir plus sur [cette page](datamodel.md).

## [!DNL Campaign] Mécanisme d’évaluation des API

Avec la base de données [!DNL Campaign] cloud, les appels unitaires d’explosion ne sont pas recommandés en raison des performances (latence et simultanéité). L’opération de lot est toujours préférable. Afin de garantir des performances optimales des API, Campaign gère toujours les appels API au niveau de la base de données locale.

[!DNL :bulb:] [Le mécanisme d’évaluation des API est présenté dans cette page](staging.md)

## Nouvelles API

De nouvelles API sont disponibles pour gérer la synchronisation des données entre la [!DNL Campaign] base de données locale et la base de données Cloud. Un nouveau mécanisme a également été introduit pour gérer les appels API au niveau de la base de données locale afin d’éviter la latence et d’améliorer les performances globales.

[!DNL :bulb:] [Les nouvelles API sont présentées dans cette page](new-apis.md)

**Rubriques connexes**

* [Bonnes pratiques relatives au modèle de données](datamodel-best-practices.md)
