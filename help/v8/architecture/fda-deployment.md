---
title: Prise en main du déploiement FDA de Campaign
description: Prise en main du déploiement FDA de Campaign
feature: Architecture, Federated Data Access, Deployment
role: Admin, Developer
level: Beginner
exl-id: b3df0336-f40e-4ac1-b6a4-068b8827dca2
source-git-commit: 561e4b6d2c99e98e068132c80c2bebb756b60a44
workflow-type: ht
source-wordcount: '326'
ht-degree: 100%

---

# Déploiement FDA de [!DNL Campaign]{#gs-fda}

Dans un déploiement FDA (par défaut), [!DNL Adobe Campaign] v8 peut être connecté à [!DNL Snowflake] pour accéder aux données via la fonctionnalité [Federated Data Access](../connect/fda.md) : vous pouvez ainsi accéder aux données et aux informations externes stockées dans votre base de données [!DNL Snowflake] sans modifier la structure des données Adobe Campaign.

>[!NOTE]
>
>Dans ce modèle de déploiement, la base de données [!DNL Snowflake] secondaire n’est disponible que sur demande. Pour mettre à jour votre déploiement avec [!DNL Snowflake], contactez la personne chargée de votre transition Adobe.
>

## Avantages{#fda-benefits}

Ce modèle de déploiement présente les avantages suivants :

* **Stockage et performances**
Vous pouvez déplacer vos données historiques vers [!DNL Snowflake] puis réduire les dépendances à la limite des identifiants Adobe Campaign. Cette architecture réduit également votre dépendance aux limites de stockage et de performances PostgreSQL. Comme moins de données sont stockées dans la base de données Campaign, les performances sont meilleures et les tâches de maintenance sont exécutées plus rapidement.

* **Extension du modèle de données et gestion des données**
Vous pouvez créer des tables dans [!DNL Snowflake] et les lier à Adobe Campaign, par exemple pour utiliser les données archivées sur les périodes de rétention, ou exécuter des processus de segmentation avec des performances exceptionnelles.

  Cette architecture vous permet également d’utiliser les fonctionnalités de workflow de gestion de données dans [!DNL Snowflake]. Seuls les agrégats et les tables temporaires sont déplacés vers Campaign à des fins de personnalisation et de diffusion.


## Architecture{#fda-archi}

Avec ce modèle de déploiement, les utilisateurs d’Adobe Campaign peuvent étendre leurs données dans [!DNL Snowflake] et tirer parti des avantages d’une seule plateforme de données intégrée pour obtenir des informations précieuses sur les données de campagne marketing en temps réel. Il permet aux utilisateurs de dévoiler la valeur de leurs données en leur offrant une seule plateforme unifiée et facile à utiliser pour l’analyse des données. La plateforme de données cloud ne nécessite aucune gestion, car elle prend infiniment en charge n’importe quel volume de données marketing d’Adobe Campaign.

La communication générale entre les serveurs et les processus est réalisée conformément au schéma suivant :

![](assets/fda-architecture.png)

PostgreSQL est la base de données principale et Snowflake peut être utilisé comme base de données secondaire. Vous pouvez étendre votre modèle de données et stocker vos données sur Snowflake. Par la suite, vous pourrez exécuter ETL, la segmentation et les rapports sur un jeu de données volumineux avec des performances optimales.
