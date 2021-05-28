---
solution: Campaign v8
product: Adobe Campaign
title: Nouveautés de Campaign v8
description: En savoir plus sur les principales fonctionnalités
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
source-git-commit: a48e69a3f34c48ed4828bf29b8a02a3dc07bfa7e
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 61%

---

# Nouveautés d’Adobe Campaign v8 {#ac-gs-what-is-new}

Adobe Campaign v8 apporte d’importantes améliorations en termes d’infrastructure, de sécurité, de délivrabilité et de surveillance. En exploitant la technologie de base de données cloud [[!DNL Snowflake]](https://www.snowflake.com/), Adobe Campaign améliore considérablement son échelle et sa vitesse, avec la possibilité de gérer un nombre plus important de profils client, ainsi que des taux de remise et des transactions beaucoup plus élevés par heure.

Les fonctionnalités principales sont les suivantes :

* **Vitesse et échelle**. Adobe Campaign v8 utilise le gestionnaire de base de données cloud. Cela permet aux requêtes d’atteindre des performances jusqu’à 200 fois plus rapides, une mise à l’échelle à plusieurs pétaoctets et l’augmentation du nombre de messages par heure, jusqu’à 20 millions/heure ou 1 million/heure pour les messages transactionnels. Cela permet également de gérer jusqu’à 200 millions de profils actifs, avec la capacité d’atteindre 1 milliard.

* **Connexions à Adobe Experience Platform**. Adobe Campaign v8 prend en charge les connecteurs de données avec Adobe Experience Platform/RT-CDP, le profil client unifié et l’intégration native à Journey Orchestration. Ces investissements vont permettre d’optimiser l’expérience client dans Adobe Campaign. Ils débloqueront notamment de nouveaux cas d’utilisation, tels que la possibilité d’ajouter des parcours clients en temps réel personnalisés aux campagnes.

* **Managed Cloud Services**. Adobe Campaign v8 est disponible en tant que service Managed Cloud Services de premier plan. L’application offre une supervision proactive, des alertes rapides et une gouvernance des services. La valeur du marketeur est une gestion de campagne cross-canal plus agile et plus évolutive.

>[!CAUTION]
>
>Pour l’instant, Campaign v8 est **uniquement** disponible en tant que Cloud Service géré et ne peut pas être déployé dans des environnements on-premise ou hybrides.
>
>La migration depuis un environnement Campaign Classic v7 existant n&#39;est pas encore disponible.
>
>Si vous n’êtes pas sûr de votre modèle de déploiement ou si vous avez des questions, contactez votre équipe de compte.


## Échelle

Campaign v8 apporte une échelle de bout en bout à n’importe quelle étape du processus, du ciblage au reporting final :

* Mise à l’échelle du volume de données que vous pouvez gérer (jusqu’à 8 To)
* Mise à l’échelle des performances de requêtes pour la segmentation et le ciblage ainsi que pour l’ingestion et la sortie des données
* Mise à l’échelle de la préparation de la diffusion (des heures aux minutes)

## Simplification et amélioration des performances

Campaign v8 présente le concept de **Full Federated Data Access** (FDA) : toutes les données sont désormais distantes sur la base de données cloud.

Avec cette nouvelle architecture, Campaign v8 simplifie la gestion des données : aucun index n’est requis sur la base de données cloud. Il vous suffit de créer les tables et de copier les données pour démarrer.

[!DNL Snowflake] est la base de données Campaign Cloud, elle vous apportera vitesse et autonomie : aucune surcharge de l’activité du système ne pèse.

La technologie de base de données cloud ne nécessite pas de maintenance spécifique pour garantir le niveau attendu de performances.

## Écosystème intégré

Vous pouvez intégrer Campaign à un ensemble de solutions Adobe puissantes, telles que : Adobe Analytics, Workfront, Journey Orchestration, Real-Time CDP, etc.

Vous pouvez également configurer l’optimisation de l’heure d’envoi prédictive ainsi que le score d’engagement prédictif grâce à l’IA dédiée au parcours. Cela permet d’augmenter les taux d’ouverture, les clics et les revenus.

[!DNL :bulb:] [En savoir plus sur les intégrations de Campaign](../connect/integration.md)

