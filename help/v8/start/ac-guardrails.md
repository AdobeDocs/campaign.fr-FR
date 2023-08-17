---
title: Mécanismes de sécurisation de Campaign v8
description: Mécanismes de sécurisation de Campaign v8
feature: Overview
role: User
level: Beginner, Intermediate, Experienced
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
source-git-commit: 754a575b4359633f2bba5c51598725ca577b28d5
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 100%

---

# Mécanismes de sécurisation des produits{#guardrails}

Les droits, les limites de produit et les mécanismes de sécurisation des performances sont répertoriés dans la section [Page de description du produit Adobe Campaign Managed Cloud Services](https://helpx.adobe.com/fr/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

Vous trouverez ci-dessous des mécanismes de sécurisation et des limites supplémentaires lors de l’utilisation de [!DNL Adobe Campaign].

Les limites et les mécanismes de sécurisation identifient les fonctionnalités, l’architecture ou les processus qui ne sont pas pris en charge par cette version du produit ou qui n’interagissent pas correctement avec celle-ci. Examinez attentivement ces limites.

* Adobe Campaign v8 n’est pas disponible pour les déploiements on-premise/hybrides. Il est disponible uniquement en tant que Managed Cloud Service d’Adobe
* Aucune migration automatique vers Adobe Campaign v8 n’est disponible pour les clientes et clients existants.
* Dans le contexte d’un [Déploiement Enterprise (FFDA)](../architecture/enterprise-deployment.md), aucune réplication de données bidirectionnelle n’est fournie : la réplication se produit uniquement de la base de données locale Campaign vers la base de données Cloud.
* Les fonctionnalités répertoriées [dans cette section](v7-to-v8.md#gs-unavailable-features) ne sont pas disponibles dans la versio actuelle de Campaign v8.
* Certaines fonctionnalités non disponibles ou supprimées sont toujours visibles dans l&#39;interface utilisateur.
* Dans le contexte d’un [Déploiement Enterprise (FFDA)](../architecture/enterprise-deployment.md), les mécanismes d’abonnement (opt-in) et de désabonnement (opt-out), et l’enregistrement mobile sont des processus asynchrones. Les demandes sont traitées toutes les heures par l&#39;intermédiaire d&#39;un workflow technique spécifique. [En savoir plus](../architecture/replication.md#tech-wf)
* Dans le contexte d’un [Déploiement Entreprise (FFDA)](../architecture/enterprise-deployment.md), les doublons doivent être gérés manuellement par les utilisateurs et utilisatrices finaux. [En savoir plus](../architecture/keys.md)
* Adobe Campaign v8 ne prend pas en charge le débit étendu sur les API et les applications web. Pour les besoins spécifiques, contactez Adobe pour obtenir des conseils.
* Dans le contexte d’un [Déploiement Entreprise (FFDA)](../architecture/enterprise-deployment.md), le module Optimisation de campagne Adobe Campaign ne prend pas en compte les diffusions planifiées dans les règles de typologie de pression. Apprenez-en davantage en consultant [cette page](../../automation/campaign-opt/pressure-rules.md).