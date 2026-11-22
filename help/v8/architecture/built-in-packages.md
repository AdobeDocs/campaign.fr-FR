---
title: Packages natifs
description: Découvrez les packages natifs de Campaign v8, en quoi ils diffèrent des packages de données personnalisés et lesquels sont disponibles
feature: Architecture
role: Admin, Developer
level: Beginner
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: bae31391-3416-5fbd-bc4b-2cdcae2922db
    internal-label: Architecture
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: e656c701-3899-4db3-989c-de0980ddfffa
    internal-label: Installation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: b37128ff4180befd5655c0c16b9ff0834235a84a
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 17%
---
# Packages natifs {#built-in-packages}

Les packages natifs (également appelés packages standard) contiennent les fonctionnalités d’Adobe Campaign. Dans Campaign v8, Adobe installe et gère ces packages pour vous. Vous n’avez pas besoin de les installer.

## Packages intégrés et packages personnalisés {#built-in-vs-custom}

Campaign utilise deux types de packages. Assurez-vous de travailler avec le bon.

| | Packages natifs | Packages personnalisés |
|---|---|---|
| Intérêt | Fournissez les fonctionnalités de Campaign, telles que les canaux, les intégrations et les modules complémentaires. | Exportez et importez votre propre configuration et vos propres données, par exemple d’un environnement d’évaluation vers un environnement de production. |
| Qui les gère ? | Adobe les installe et les gère. Avec Managed Cloud Services, vous ne pouvez pas modifier les packages natifs installés. | Vous pouvez les créer, les exporter et les importer. |
| Où en savoir plus | Cette page. | [Utiliser des packages de données](../dev/packages.md) |

## Vérifier les packages installés {#check-installed-packages}

Pour vérifier quels packages natifs sont installés sur votre instance, accédez à **[!UICONTROL Administration > Configuration > Gestion des packages > Packages installés]**. Vous pouvez également les consulter dans la Surveillance des instances du Panneau de Contrôle. En savoir plus dans la [Présentation de la surveillance des campagnes](../start/monitor.md#monitor-instance).

Si vous avez besoin d’un package ou d’un module complémentaire qui n’a pas été configuré pour vous, contactez l’assistance clientèle d’Adobe ou votre gestionnaire de transition Adobe.

## Liste des packages natifs {#list-of-built-in-packages}

Le tableau suivant répertorie les packages intégrés pour plus d’informations. La disponibilité de chaque package est soumise à votre contrat de licence et à votre modèle de déploiement.

| Package | Description |
|---|---|
| Diffusion | Surveille les diffusions et les problèmes rencontrés lors de l’envoi des messages. [En savoir plus](../start/monitor.md) |
| Campagnes marketing (Campaign) | Définit, optimise, exécute et analyse des campagnes marketing et de communication. [En savoir plus](../start/campaigns.md) |
| Ressources marketing (MRM) | Contrôle les actions marketing en mode collaboratif, avec la gestion et le suivi des tâches, des budgets et des ressources marketing. [En savoir plus](../../automation/mrm/about-marketing-resource-management.md) |
| Moteur d’offres (Interaction) | Répond en temps réel lors d&#39;une interaction avec un contact en proposant une ou plusieurs offres adaptées. [En savoir plus](../interaction/interaction.md) |
| Réseaux sociaux (Social Marketing) | Synchronise Adobe Campaign avec X (anciennement Twitter). [En savoir plus](../connect/ac-tw.md) |
| Contrôle et exécution des messages transactionnels (Message Center) | Gère les messages de déclenchement générés à partir d&#39;événements dans les systèmes d&#39;information, avec une disponibilité accrue et une meilleure gestion de la charge. [En savoir plus](../send/transactional.md) |
| Canal Line | Envoie les diffusions via le canal LINE. [En savoir plus](../send/line/line.md) |
| Canal courrier | Envoie les diffusions via le canal courrier. [En savoir plus](../send/direct-mail.md) |
| Canal mobile (SMS) | Envoie les diffusions via le canal mobile (SMS). [En savoir plus](../send/sms/sms.md) |
| Canal des applications mobiles | Envoie des notifications personnalisées aux appareils iOS et Android par le biais d’applications. [En savoir plus](../send/push.md) |
| Gestion de contenu (Content Manager) | Crée des newsletters ou des sites web récurrents, puis valide et publie vos messages. [En savoir plus](../../automation/workflow/content-management.md) |
| Questionnaires en ligne (Survey Manager) | Crée et gère des formulaires en ligne pour ajouter ou modifier des informations de profil, s’abonner, se désabonner ou participer à un concours. [En savoir plus](../dev/surveys/about-surveys.md) |
| Marketing Analytics | Analyse et mesure les données, calcule les statistiques et simplifie la création de rapports. [En savoir plus](../reporting/gs-reporting.md) |
| Gestion de la réaction | Mesure le succès et la rentabilité des campagnes marketing ou des offres sur tous les canaux. [En savoir plus](../../automation/response/about-response-manager.md) |
| Accès à des données externes (Federated Data Access) | Traite les informations stockées dans des bases de données externes sans modifier la structure des données Adobe Campaign. [En savoir plus](../connect/fda.md) |
| Optimisation des campagnes (Campaign Optimization) | Contrôle, filtre et surveille les diffusions afin que les messages répondent aux besoins des clients et aux politiques de communication de l’entreprise. [En savoir plus](../../automation/campaign-opt/campaign-typologies.md) |
| Su de la délivrabilité (Email Deliverability) | Mesure si vos messages atteignent la boîte de réception sans bounces ou sans être marqués comme spam. [En savoir plus](../send/monitoring-deliverability.md) |
| Gestion des coupons | Crée des ensembles de coupons à ajouter aux offres marketing. [En savoir plus](../send/personalized-coupons.md) |
| Inbox Rendering (IR) | Prévisualise les messages dans les contextes de réception et vérifie la compatibilité avec les principaux clients de messagerie web et de bureau. [En savoir plus](../send/inbox-rendering.md) |
| Marketing central/local (Marketing distribué) | Met en œuvre des opérations de coopération entre des entités centrales, telles que le siège social, et des entités locales, telles que des points de vente. [En savoir plus](../../automation/distributed-marketing/about-distributed-marketing.md) |
| Connecteurs CRM | Associe Adobe Campaign à des systèmes CRM tiers. [En savoir plus](../connect/crm.md) |
| Connecteurs Web Analytics | Permet à Adobe Campaign et Adobe Analytics d’interagir. [En savoir plus](../connect/ac-aa.md) |
| Intégration AEM | Gère le contenu des e-mails et des formulaires dans Adobe Experience Manager. [En savoir plus](../connect/ac-aem.md) |
| Intégration des audiences partagées Adobe Experience Cloud | Échange et partage des audiences avec les solutions et applications [!DNL Adobe CX Enterprise] (anciennement Adobe Experience Cloud). [En savoir plus](../start/shared-audiences.md) |
| Intégration avec Adobe Experience Cloud | Importe et exporte les audiences des solutions [!DNL Adobe CX Enterprise] (anciennement Adobe Experience Cloud) dans Adobe Campaign. [En savoir plus](../connect/integration.md) |
| Règlement sur la protection des informations personnelles | Ajoute des fonctionnalités pour faciliter la conformité en matière de confidentialité. [En savoir plus](../start/privacy.md) |
| Assistance AMP | Envoie des e-mails dynamiques avec l’AMP interactif pour le format des e-mails. [En savoir plus](../send/defining-interactive-content.md) |


>[!NOTE]
>
>Les packages Ressources marketing (MRM), Gestion des coupons et Questionnaires en ligne ne sont pas disponibles dans le contexte d’un déploiement Grands comptes (FFDA) de Campaign. En savoir plus sur la [Disponibilité des fonctionnalités](../architecture/enterprise-deployment.md#feature-availability).

## Rubriques connexes {#related-topics}

* [Utiliser des packages de données](../dev/packages.md) : créez, exportez et importez vos propres packages personnalisés.
* [Workflows techniques](../../automation/workflow/technical-workflows.md) : les workflows techniques intégrés et le package qui les installe.
* [Disponibilité des fonctionnalités dans les déploiements FFDA](enterprise-deployment.md#feature-availability) : fonctionnalités qui ne sont pas disponibles dans les déploiements Enterprise (FFDA).
* [Fonctionnalités non prises en charge](../start/v7-to-v8.md#gs-removed) : les fonctionnalités de Campaign Classic v7 qui ne sont plus prises en charge dans v8.
* [Principes globaux](general-architecture.md) : éléments que vous pouvez ou ne pouvez pas modifier dans un environnement Managed Cloud Services.
* [Prise en main de Campaign v8](../start/get-started.md) : aperçu des principales fonctionnalités et des modules complémentaires.
