---
solution: Campaign v8
product: Adobe Campaign
title: Nouveautés de Campaign v8
description: En savoir plus sur les principales fonctionnalités
feature: Vue d'ensemble
role: Data Engineer
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 1%

---

# Nouveautés d’Adobe Campaign v8 {#ac-gs-what-is-new}

Adobe Campaign v8 apporte d’importantes améliorations au niveau de l’infrastructure, de la sécurité, de la délivrabilité et de la surveillance. En exploitant la technologie de base de données cloud [[!DNL Snowflake]](https://www.snowflake.com/), Adobe Campaign améliore considérablement son échelle et sa vitesse, avec la possibilité de gérer un nombre plus important de profils client, ainsi que des taux de remise et des transactions beaucoup plus élevés par heure.

Les fonctionnalités principales sont les suivantes :

* **Vitesse et échelle**. Adobe Campaign v8 s’appuie sur le Cloud Database Manager, ce qui permet aux requêtes d’exécuter jusqu’à 200 fois plus rapidement, à plusieurs pétaoctets, d’augmenter le nombre de messages par heure, avec jusqu’à 20 Mo/heure ou 1,5 million/heure pour les messages transactionnels, et de gérer jusqu’à 200 millions de profils principaux avec la possibilité d’atteindre 1B.

* **Connexions à Adobe Experience Platform**. Adobe Campaign v8 prend en charge les connecteurs de données avec Adobe Experience Platform/RT-CDP, profil client unifié et intégration native avec Journey Orchestration. Ces investissements optimiseront l’expérience client d’Adobe Campaign et déverrouilleront de nouveaux cas d’utilisation, tels que la possibilité d’ajouter des parcours client en temps réel personnalisés aux campagnes.

* **Cloud Services gérés**. Adobe Campaign v8 est disponible en tant que Cloud Services géré haut de gamme, offrant une surveillance proactive, des alertes rapides et une gouvernance des services. La valeur du marketeur est une gestion de campagne cross-canal plus agile et plus évolutive.

>[!CAUTION]
>
>Pour l’instant, Campaign v8 est **uniquement** disponible en tant que Cloud Service géré et ne peut pas être déployé dans des environnements on-premise ou hybrides.
>
>La migration depuis un environnement Campaign Classic v7 existant n&#39;est pas encore disponible.


## Échelle

Campaign v8 apporte une échelle de bout en bout à n’importe quelle étape du processus, du ciblage au reporting final :

* Augmentez le volume de données que vous pouvez gérer (jusqu’à 8 To)
* Augmenter les performances des requêtes de segmentation et de ciblage, mais aussi d’ingestion et de sortie de données
* Mise à l’échelle de la préparation de la diffusion (des heures aux minutes)

## Simplification et amélioration des performances

Campaign v8 apporte le concept de **Full Federated Data Access** (FDA) : toutes les données sont désormais distantes sur la base de données cloud.

Avec cette nouvelle architecture, Campaign v8 simplifie la gestion des données : aucun index n’est requis sur la base de données cloud. Il vous suffit de créer les tableaux, de copier les données et de commencer.

[!DNL Snowflake] est la base de données Campaign Cloud, elle vous apportera vitesse et autonomie : aucune surcharge de l’activité du système ne pèse.

La technologie de base de données Cloud ne nécessite pas de maintenance spécifique pour garantir le niveau de performance.

## Écosystème intégré

Vous pouvez intégrer Campaign à un ensemble de solutions d&#39;Adobe puissantes, telles que : Adobe Analytics, Workfront, Journey Orchestration, plateforme de données clients en temps réel, etc.

Vous pouvez également configurer l’optimisation prédictive de l’heure d’envoi et la notation prédictive de l’engagement avec Parcours AI, ainsi qu’augmenter les taux d’ouverture, les clics et les recettes.

:bulb: [En savoir plus sur les intégrations de Campaign](../connect/integration.md)

