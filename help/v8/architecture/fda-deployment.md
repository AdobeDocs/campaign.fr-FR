---
title: Prise en main du déploiement FDA de Campaign
description: Prise en main du déploiement FDA de Campaign
feature: Architecture, Federated Data Access, Deployment
role: Admin, Developer
level: Beginner
exl-id: b3df0336-f40e-4ac1-b6a4-068b8827dca2
TQID: https://experienceleague.adobe.com/PfXTlEYfwkN9YRDIx44TdtZLjNZJkHqN73sJGxA0c-E
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a658c786-869b-4194-a780-2594d663adda
subfeature_v2: id: ee3dfd63-9a21-4961-9f24-ea3385284a21
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094id: e1e0219c-f879-479f-8427-888ed2a6e9c2id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 329
ht-degree: 84%

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
Vous pouvez déplacer vos données historiques vers [!DNL Snowflake], puis réduire les dépendances à la limite des Adobe Campaign ID. Cette architecture réduit également votre dépendance aux limites de stockage et de performances PostgreSQL. Comme moins de données sont stockées dans la base de données Campaign, les performances sont meilleures et les tâches de maintenance sont exécutées plus rapidement.

* **Extension du modèle de données et gestion des données**
Vous pouvez créer des tables dans [!DNL Snowflake] et les lier à Adobe Campaign, par exemple pour utiliser les données archivées sur les périodes de rétention, ou exécuter des processus de segmentation avec des performances exceptionnelles.

  Cette architecture vous permet également d’utiliser les fonctionnalités de workflow de gestion de données dans [!DNL Snowflake]. Seuls les agrégats et les tables temporaires sont déplacés vers Campaign à des fins de personnalisation et de diffusion.


## Architecture{#fda-archi}

Avec ce modèle de déploiement, les utilisateurs d’Adobe Campaign peuvent étendre leurs données dans [!DNL Snowflake] et tirer parti des avantages d’une seule plateforme de données intégrée pour obtenir des informations précieuses sur les données de campagne marketing en temps réel. Il permet aux utilisateurs de dévoiler la valeur de leurs données en leur offrant une seule plateforme unifiée et facile à utiliser pour l’analyse des données. La plateforme de données cloud ne nécessite aucune gestion, car elle prend infiniment en charge n’importe quel volume de données marketing d’Adobe Campaign.

La communication générale entre les serveurs et les processus est réalisée conformément au schéma suivant :

![](assets/fda-architecture.png)

PostgreSQL est la base de données principale et Snowflake peut être utilisé comme base de données secondaire. Vous pouvez étendre votre modèle de données et stocker vos données sur Snowflake. Par la suite, vous pourrez exécuter ETL, la segmentation et les rapports sur un jeu de données volumineux avec des performances optimales.
