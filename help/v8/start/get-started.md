---
solution: Campaign v8
product: Adobe Campaign
title: Prise en main de Campaign v8
description: Découvrez les principales fonctionnalités, l'interface utilisateur et les directives globales
feature: Vue d'ensemble
role: Data Engineer
level: Beginner
exl-id: 04b12907-3cb1-40f1-90b8-1524d84edf2d,e3e9b514-a69d-4650-b1b1-1b76b4f3d63f
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '898'
ht-degree: 38%

---

# Prise en main d’Adobe Campaign{#gs-ac-v8}

Adobe Campaign offre une plateforme pour concevoir des expériences client cross-canal et un environnement pour l’orchestration visuelle des campagnes, la gestion des interactions en temps réel et l’exécution cross-canal.

Utilisez Campaign pour :

* **** Personnalisation et engagement au moyen d’une vue accessible unique du client
* **** Intégrer les canaux email, mobile, en ligne et hors ligne dans le parcours client
* **** Automatiser la diffusion de messages et d’offres pertinents et en temps voulu

![](assets/ac-capabilities.png)

## Profil client intégré {#integrated-customer-profile}

Les profils sont centralisés dans une base de données cloud puissante. Il existe de nombreux mécanismes permettant d’acquérir des profils et créer cette base de données : collecte en ligne par le biais de formulaires Web, importation manuelle ou automatique de fichiers texte, réplication avec des bases de données d’entreprises ou d’autres systèmes d’information. Avec Adobe Campaign, vous pouvez incorporer dans une vue consolidée l’historique marketing, les informations d’achat, les préférences, les données de gestion de la relation client et toutes les données relatives aux informations d’identification personnelles afin d’analyser et d’agir.

Dans Adobe Campaign, les destinataires sont les profils par défaut ciblés pour l&#39;envoi des diffusions (emails, SMS, etc.). Grâce aux données de destinataires stockées dans la base de données, vous pourrez filtrer la cible qui recevra toute diffusion donnée et ajouter les données de personnalisation à votre contenu de diffusion. Il existe d&#39;autres types de profils dans la base de données qui sont conçus pour d&#39;autres utilisations. Par exemple, les profils d&#39;adresses de contrôle sont destinés à tester votre diffusions avant leur envoi à la cible finale.

:bulb: Les principes de base de la gestion des profils sont expliqués dans [cette section](audiences.md).

:bulb: Découvrez comment ajouter des profils à Campaign dans [cette section](import.md).

## Segmentation ciblée {#targeted-segmentation}

Pour vous permettre de mettre en place des offres hautement ciblées et différenciées, Adobe Campaign intègre des fonctionnalités d&#39;analyse et ciblage. Grâce aux fonctionnalités d&#39;analyse descriptive, vous avez la possibilité d&#39;analyser les informations en amont et en aval de vos campagnes marketing. D&#39;autre part, les fonctionnalités de gestion de filtres et l&#39;éditeur graphique de requête vous permettent de filtrer les populations d&#39;inscrits, d&#39;échantillonner ou de créer des groupes cibles sur un nombre illimité de critères.

La fonctionnalité avancée de Data Management étend les fonctionnalités de traitement des données. Elle simplifie et optimise le processus de ciblage en incluant des données qui ne sont pas modélisées dans le datamart.

:bulb: Pour en savoir plus sur la segmentation, la création d’audiences et la personnalisation, consultez [cette section](audiences.md).

## Orchestration de campagnes cross-canal {#cross-channel-campaign-orchestration}

Adobe Campaign vous permet de concevoir et orchestrer des campagnes ciblées et personnalisées sur plusieurs canaux : email, courrier, SMS, notification push. Une seule interface vous fournit toutes les fonctions nécessaires pour planifier, orchestrer, configurer, personnaliser, automatiser, exécuter et mesurer toutes vos campagnes et communications.

:bulb: Découvrez comment concevoir, planifier et exécuter une campagne dans [cette section](campaigns.md).

## Workflows

Adobe Campaign propose un environnement graphique qui permet de construire des processus complexes englobant segmentation, exécution de campagnes, manipulation de fichiers, validations, etc. Un workflow permet par exemple de télécharger un fichier depuis un serveur, de le décompresser et d&#39;importer ses enregistrements dans la base de données Adobe Campaign.

Un workflow peut également faire intervenir des utilisateurs, pour leur affecter une tâche ou demander la validation d&#39;une tâche accomplie. Ainsi, il est possible d&#39;assigner une tâche à un ou plusieurs utilisateurs qui seront chargés de saisir son contenu ou spécifier sa cible, puis de faire valider un BAT avant d&#39;envoyer un message.

Les workflows peuvent intervenir dans différents contextes, par exemple :

* Ciblage afin de gérer des audiences ou envoyer des messages.
* Data management (ETL) pour manipuler des données.
* Import de données dans la base de Campaign.
* Processus techniques tels que les tâches de nettoyage de la base (cleanup), la récupération des informations de tracking, etc.

:bulb: Découvrez comment concevoir et exécuter des workflows dans [cette section](../config/workflows.md).

## Rapports et analyses {#analysis-and-reporting}

Adobe Campaign vous permet de surveiller et d’interpréter le comportement de vos clients en enrichissant progressivement leurs données et profils. Les outils de reporting et d’analyse vous permettent de capitaliser sur chaque nouvelle campagne, de mieux cibler vos initiatives marketing et d’optimiser leur impact et leur retour sur investissement.

:bulb: Pour en savoir plus sur les fonctionnalités de rapport et de suivi, consultez [cette section](reporting.md).

## Intégrations d&#39;Adobe Experience Cloud {#adobe-experience-cloud-integrations}

Vous pouvez combiner les fonctionnalités de diffusion et de gestion de campagnes avancées d&#39;Adobe Campaign avec un ensemble de solutions conçues pour vous aider à personnaliser l&#39;expérience de vos utilisateurs : Les déclencheurs Adobe Experience Manager, Adobe Analytics, Adobe Target ou Adobe Experience Cloud, par exemple.

:bulb: Découvrez comment intégrer avec les services et solutions Adobe dans [cette section](../connect/integration.md).

## En savoir plus sur les fonctionnalités de Campaign {#core-capabilities-and-add-ons}

Adobe Campaign propose un ensemble de fonctionnalités pour vous aider à mettre en oeuvre et optimiser les fonctionnalités de marketing conversationnel selon vos besoins et votre architecture. Certaines d’entre elles sont des fonctionnalités de base et d’autres dépendent de l’installation d’un package sur votre configuration. Une description détaillée du produit est disponible ici : [Description du produit Adobe Campaign v8](https://helpx.adobe.com/fr/legal/product-descriptions/adobe-campaign-classic---product-description.html).

:bulb: Vous connaissez déjà Campaign Classic ? Découvrez les différences clés entre Campaign Classic et Campaign v8 dans [cette page](capability-matrix.md).

## Espace de travail et personnalisation

L’espace de travail Campaign est disponible via la [console cliente](../dev/general-architecture.md).

:bulb: [En savoir plus sur la console cliente Campaign](../start/connect.md).

L&#39;espace de travail de Campaign peut être adapté selon vos besoins.

:flèche_upper_right :  Découvrez comment utiliser l’espace de travail Campaign dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html)

:flèche_upper_right :  Découvrez comment personnaliser des listes dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html)

Vous pouvez également accéder à certaines fonctionnalités par le biais du Web.

:bulb: [En savoir plus sur l’accès Web de Campaign](../start/connect.md#web-access).


## Langues

L&#39;interface utilisateur de Campaign v8 est disponible dans les langues suivantes :

* Anglais (Royaume-Uni)
* Anglais (US)
* Français
* Allemand
* Japonais

La langue est sélectionnée lors du processus d&#39;installation.

>[!CAUTION]
>
>La langue ne peut pas être modifiée après la création de l&#39;instance.

Formats des dates et heures affectés par la langue. Voir à ce propos la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html?lang=en#date-and-time).

