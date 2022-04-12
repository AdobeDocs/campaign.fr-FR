---
title: Nouveautés de Campaign v8
description: Découvrez les fonctionnalités principales de Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
source-git-commit: def9714448ef5fdde39cee070088615e8f50e522
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 100%

---

# Nouveautés d&#39;Adobe Campaign v8 {#ac-gs-what-is-new}

Adobe Campaign v8 a fortement amélioré son infrastructure, sa sécurité, sa délivrabilité et sa surveillance. Grâce à l&#39;utilisation de [[!DNL Snowflake]](https://www.snowflake.com/), une technologie de base de données cloud, Adobe Campaign améliore considérablement sa mise à l&#39;échelle et sa vitesse. L&#39;application a ainsi la capacité de gérer un nombre plus important de profils client, ainsi que des taux de diffusion et de transactions beaucoup plus élevés par heure.

## Fonctionnalités principales{#key-capabilities}

Les fonctionnalités principales sont les suivantes :

* **Vitesse et mise à l&#39;échelle**. Adobe Campaign v8 utilise le gestionnaire de base de données cloud. Cela permet aux requêtes d&#39;atteindre des performances jusqu&#39;à 200 fois plus rapides, une mise à l&#39;échelle à plusieurs pétaoctets et l&#39;augmentation du nombre de messages par heure, jusqu&#39;à 20 millions/heure ou 1 million/heure pour les messages transactionnels. Cela permet également de gérer jusqu&#39;à 200 millions de profils actifs, avec la capacité d&#39;atteindre 1 milliard.

* **Connexions à Adobe Experience Platform**. Adobe Campaign v8 prend en charge les connecteurs de données avec Adobe Experience Platform/RT-CDP, le profil client unifié et l&#39;intégration native à Journey Orchestration. Ces investissements vont permettre d’optimiser l’expérience client dans Adobe Campaign. Ils débloqueront notamment de nouveaux cas d’utilisation, tels que la possibilité d’ajouter des parcours clients en temps réel personnalisés aux campagnes.

* **Managed Cloud Services**. Adobe Campaign v8 est disponible en tant que service Managed Cloud Services de premier plan. L&#39;application offre une supervision proactive, des alertes rapides et une gouvernance des services. Pour le spécialiste marketing, la valeur de ces améliorations réside dans une plus grande flexibilité et une plus grande évolutivité en termes de gestion de campagnes cross-canal.

>[!CAUTION]
>
>À l&#39;heure actuelle, Campaign v8 est **uniquement** disponible en tant que Managed Cloud Service et ne peut pas être déployé dans des environnements on-premise ou hybrides.
>
>La migration depuis un environnement Campaign Classic v7 existant n&#39;est pas encore disponible.
>
>Si vous n&#39;êtes pas sûr de votre modèle de déploiement ou si vous avez des questions, contactez votre équipe de compte.

![](assets/home-page.png)

## Échelle{#scale}

Campaign v8 fournit une mise à l&#39;échelle de bout en bout à n&#39;importe quelle étape du processus, du ciblage au reporting final :

* Mise à l&#39;échelle du volume de données que vous pouvez gérer (jusqu&#39;à 8 To)
* Mise à l&#39;échelle des performances de requêtes pour la segmentation et le ciblage ainsi que pour l&#39;ingestion et la sortie des données
* Mise à l&#39;échelle de la préparation des diffusions (des heures aux minutes)

## Interface d&#39;administrateur en libre-service{#self-service-admin}

En tant qu&#39;administrateur de produit, vous pouvez gérer les paramètres et suivre l&#39;utilisation de chacune de vos instances Campaign v8 avec le **Panneau de contrôle Campaign**.

Grâce à une interface utilisateur intuitive, les administrateurs peuvent surveiller l&#39;utilisation des ressources clés, effectuer des tâches avancées telles que les listes autorisées d&#39;adresses IP, la surveillance de l&#39;espace de stockage SFTP, la gestion des clés, etc. Cette interface en libre-service vous apporte davantage de flexibilité et vous permet d&#39;effectuer les opérations suivantes :

* Modifiez rapidement par vous-même les paramètres sans contacter le support Adobe
* Configurez les paramètres en fonction de vos besoins métier à différents instants
* Renforcez la sécurité en contrôlant les paramètres d&#39;accès au cas par cas

![](assets/subdomain1.png)

![](../assets/do-not-localize/glass.png) [Apprenez-en davantage sur le panneau de contrôle Campaign](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/key-features.html?lang=fr){target=&quot;_blank&quot;}



## Simplification et amélioration des performances{#simplification-and-perf-increase}

Campaign v8 présente le concept de **Full Federated Data Access** (FFDA) : toutes les données sont désormais distantes sur la base de données cloud.

Avec cette nouvelle architecture, Campaign v8 simplifie la gestion des données : aucun index n&#39;est requis sur la base de données cloud. Il vous suffit de créer les tables et de copier les données pour démarrer.

[!DNL Snowflake] est la base de données cloud de Campaign. Grâce à sa vitesse et son endurance, vous ne constaterez aucun pic de surcharge d&#39;activité du système.

La technologie de base de données cloud ne nécessite pas de maintenance spécifique pour garantir le niveau attendu de performances.

## Écosystème intégré

Vous pouvez intégrer Campaign à un ensemble de solutions Adobe puissantes, telles que : Adobe Analytics, Adobe Journey Orchestration, CDP en temps réel, etc.

Vous pouvez également configurer l&#39;optimisation de l&#39;heure d&#39;envoi prédictive ainsi que le score d&#39;engagement prédictif grâce à l&#39;IA dédiée au parcours. Cela permet d&#39;augmenter les taux d&#39;ouverture, les clics et les revenus.

[ ![](../assets/do-not-localize/glass.png)En savoir plus sur les intégrations de Campaign](../connect/integration.md).

