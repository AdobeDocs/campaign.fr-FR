---
title: Transition de Campaign Classic v7 vers Campaign v8
description: Découvrez les différences entre Campaign Classic v7 et Campaign v8.
feature: Overview
role: User
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 98%

---

# Transition de [!DNL Campaign Classic] v7 vers [!DNL Campaign] v8{#gs-matrix}

En tant qu’ancien utilisateur de [!DNL Campaign Classic] v7, votre manière habituelle d&#39;interagir avec [!DNL Adobe Campaign] ne devrait pas subir de perturbations importantes. La plupart des modifications apportées à v8 ne sont pas visibles, à l&#39;exception des petites modifications qui apparaissent dans l&#39;interface utilisateur et dans les étapes de configuration.

>[!AVAILABILITY]
>
>* À l&#39;heure actuelle, Campaign v8 est **uniquement** disponible en tant que Managed Cloud Service et ne peut pas être déployé dans des environnements on-premise ou hybrides. [En savoir plus](#cloud-services)
>
>* La migration automatisée depuis un environnement Campaign Classic v7 existant n’est pas encore disponible.


## Managed Cloud Services{#cloud-services}

Adobe Campaign v8 est disponible en tant que **Managed Cloud Service**.

Adobe Campaign Managed Cloud Services offre une plateforme Managed Cloud Services qui permet de concevoir des expériences client cross-canal et propose un environnement pour l’orchestration visuelle de campagnes, la gestion d’interactions en temps réel et l’exécution cross-canal. Pour en savoir plus sur Campaign Managed Cloud Services, consultez la [page de description du produit](https://helpx.adobe.com/fr/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

La nouvelle offre combine les services les plus performants avec une surveillance proactive et des alertes rapides, en se concentrant sur trois domaines :

* **Agilité du cloud** : automatisation par Adobe, avec des déploiements cloud optimisés et normalisés pour des performances plus prévisibles, une plus grande agilité et une productivité en libre-service améliorée.
* **Expérience de service** : supervision proactive de la disponibilité, de la capacité et des performances et intervention pour prévenir les perturbations, résoudre les incidents plus rapidement et passer régulièrement en revue les services pour une amélioration continue.
* **Expertise approfondie dans Adobe Campaign** : service à haute affinité d’équipes d’ingénieurs client expertes pour répondre aux besoins fonctionnels, techniques ou de délivrabilité, réduire les risques de déploiement et améliorer la gestion du changement.

En tant qu’ancien utilisateur [!DNL Campaign Classic], veuillez noter que la plupart des fonctionnalités de [!DNL Campaign Classic] v7 sont disponibles dans [!DNL Campaign] v8, à l’exception d’un petit ensemble de fonctionnalités répertoriées dans [cette section](#gs-removed).

>La nouvelle architecture cloud permet à Campaign de rationaliser les processus, de réduire les coûts, de gérer les risques et d’améliorer la sécurité des données. Votre environnement Campaign v8 est fourni avec un cloud privé virtuel (VPC) dédié et préconfiguré pour vous.


## Architecture hybride {#hybrid-archi}

Campaign v8 repose sur une **architecture hybride**. Si vous effectuez une transition à partir de Campaign Classic v7, veuillez noter que toutes les diffusions passent par le serveur de midsourcing.

En conséquence :

* Le routage interne est **impossible** dans Campaign v8 et le compte externe a donc été désactivé.
* Le statut des diffusions n’est pas mis à jour instantanément : un processus technique s’exécute sur l’instance Marketing pour mettre à jour les statuts des diffusions dans les délais impartis.


Pour en savoir plus sur l’envoi de BAT de messages transactionnels si vous effectuez une transition à partir de Campaign v7, consultez [cette page](../send/transactional-template.md#transition-from-v7).


## [!DNL Campaign] et [!DNL Snowflake] {#ac-gs-snowflake}

Dans son [déploiement Enterprise (FFDA)](../architecture/enterprise-deployment.md), [!DNL Adobe Campaign] v8 fonctionne avec deux bases de données : une base de données [!DNL Campaign] locale pour la messagerie en temps réel de l’interface utilisateur et les requêtes et écritures unitaires à travers les API, et une base de données cloud [!DNL Snowflake] pour l’exécution de campagnes, les requêtes par lots et l’exécution de workflows.

Campaign v8 Enterprise présente le concept de **Full Federated Data Access** (FFDA) : toutes les données sont désormais distantes sur la base de données cloud. Avec cette nouvelle architecture, le déploiement Campaign v8 Enterprise (FFDA) simplifie la gestion des données : aucun index n&#39;est requis sur la base de données cloud. Il vous suffit de créer les tables et de copier les données pour démarrer. La technologie de base de données cloud ne nécessite pas de maintenance spécifique pour garantir le niveau de performances attendu.

Pour en savoir plus sur l’architecture de [!DNL Campaign] v8, consultez [cette page](../architecture/architecture.md).


## Utiliser votre Adobe ID pour vous connecter à Campaign{#adobe-id}

Les utilisateurs de Campaign se connectent via leur Adobe ID uniquement. Le même Adobe ID est utilisé pour conserver tous vos abonnements Adobe et produits associés sur un seul compte, pour toutes les solutions Adobe Experience Cloud.

Découvrez comment vous connecter à [!DNL Campaign] sur [cette page](connect.md).

## Analyse des données avec des cubes{#adobe-reporting}

Utilisez le module Marketing Analytics pour analyser et mesurer les données, calculer les statistiques, simplifier et optimiser la création et le calcul de rapports. Créez également des rapports et des populations cibles : une fois identifiés, ils sont stockés dans des listes qui peuvent être utilisées dans Adobe Campaign (ciblage, segmentation, etc.).

Avec Adobe Campaign v8, les rapports de cube sont optimisés et offrent de meilleures fonctionnalités d’échelle que Campaign Classic v7. Dans ce modèle de déploiement spécifique, les anciennes limitations sur les cubes ne s’appliquent pas dans Campaign v8. Découvrez-en davantage sur les cubes dans [cette section](../../v8/reporting/gs-cubes.md).

## Fonctionnalités non disponibles{#gs-unavailable-features}

Certaines fonctionnalités ne sont pas disponibles dans le cadre d’un [déploiement Grands comptes (FFDA)](../architecture/enterprise-deployment.md) de Campaign, par exemple :

* Gestion des ressources marketing
* Coupons
* Tracking web
* Questionnaires

## Fonctionnalités non prises en charge{#gs-removed}

Campaign v8 ne prend plus en charge certaines fonctionnalités historiques de Campaign Classic v7 telles que :

* Marketing des médias sociaux avec Facebook
* Connecteur ACS (offre principale)
* Intégration avec LDAP
* Connexion utilisateur/mot de passe
* Modèles de déploiement hybrides/On-premise


>[!NOTE]
>
>Certaines fonctionnalités non disponibles ou non prises en charge sont toujours visibles dans l’interface utilisateur.
