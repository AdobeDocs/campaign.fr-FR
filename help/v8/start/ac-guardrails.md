---
title: Mécanismes de sécurisation de Campaign v8
description: Mécanismes de sécurisation de Campaign v8
feature: Configuration
role: User
level: Beginner
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
TQID: 'https://experienceleague.adobe.com/4FF81xd4CiMT3fusDRU32n0-ap16O1RVUEhGIbz33Os'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: a14877cc-63b1-41d9-bf0b-5f97cadd0417
    internal-label: Configuration guidelines
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 93%
---
# Mécanismes de sécurisation des produits{#guardrails}

Les droits, les limites de produit et les mécanismes de sécurisation des performances sont répertoriés dans la page de description du produit [](https://helpx.adobe.com/fr/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

Vous trouverez ci-dessous des mécanismes de sécurisation et des limites supplémentaires lors de l’utilisation de [!DNL Adobe Campaign].

Les limites et les mécanismes de sécurisation identifient les fonctionnalités, l’architecture ou les processus qui ne sont pas pris en charge par cette version du produit ou qui n’interagissent pas correctement avec celle-ci. Examinez attentivement ces limites.

* Adobe Campaign v8 n’est pas disponible pour les déploiements on-premise/hybrides. Il est disponible uniquement en tant que Managed Cloud Service d’Adobe
* Aucune migration automatique vers Adobe Campaign v8 n’est disponible pour les clientes et clients existants.
* Dans le contexte d’un [Déploiement Enterprise (FFDA)](../../v8/architecture/enterprise-deployment.md), aucune réplication de données bidirectionnelle n’est fournie : la réplication se produit uniquement de la base de données locale Campaign vers la base de données Cloud.
* Les fonctionnalités répertoriées [dans cette section](v7-to-v8.md#gs-unavailable-features) ne sont pas disponibles dans la versio actuelle de Campaign v8.
* Certaines fonctionnalités non disponibles ou supprimées sont toujours visibles dans l&#39;interface utilisateur.
* Dans le contexte d’un [Déploiement Enterprise (FFDA)](../architecture/enterprise-deployment.md), les mécanismes d’abonnement (opt-in) et de désabonnement (opt-out), et l’enregistrement mobile sont des processus asynchrones. Les demandes sont traitées toutes les heures par l&#39;intermédiaire d&#39;un workflow technique spécifique. [En savoir plus](../architecture/replication.md#tech-wf)
* Dans le contexte d’un [Déploiement Entreprise (FFDA)](../architecture/enterprise-deployment.md), les doublons doivent être gérés manuellement par les utilisateurs et utilisatrices finaux. [En savoir plus](../architecture/keys.md)
* Adobe Campaign v8 ne prend pas en charge le débit étendu sur les API et les applications web. Pour les besoins spécifiques, contactez Adobe pour obtenir des conseils.
* Dans le contexte d’un [Déploiement Entreprise (FFDA)](../architecture/enterprise-deployment.md), le module Optimisation de campagne Adobe Campaign ne prend pas en compte les diffusions planifiées dans les règles de typologie de pression. Apprenez-en davantage en consultant [cette page](../../automation/campaign-opt/pressure-rules.md).