---
solution: Campaign Classic
product: campaign
title: Commencer avec Campaign v8
description: Découvrez les principales fonctionnalités, l'interface utilisateur et les directives globales
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
exl-id: 04b12907-3cb1-40f1-90b8-1524d84edf2d,e3e9b514-a69d-4650-b1b1-1b76b4f3d63f
translation-type: tm+mt
source-git-commit: 97cc2dd6f78fac2723306f06bea74e808c84b4ad
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 43%

---

# Commencer avec Adobe Campaign{#gs-ac-v8}

Adobe Campaign offre une plateforme pour concevoir des expériences client cross-canal et propose un environnement pour l&#39;orchestration visuelle de campagnes, la gestion d&#39;interactions en temps réel et l&#39;exécution cross-canal.

Utiliser Campaign pour :

* Favoriser la personnalisation et l&#39;engagement au travers d&#39;une vue accessible unique du client
* Intégrer les canaux de messagerie, mobiles, en ligne et hors ligne dans le parcours client
* Automatisez la diffusion de messages et d&#39;offres pertinents et opportuns

![](assets/ac-capabilities.png)

## Profil client intégré {#integrated-customer-profile}

Les profils sont centralisés dans une base de données cloud puissante. Il existe de nombreux mécanismes permettant d’acquérir des profils et créer cette base de données : collecte en ligne par le biais de formulaires Web, importation manuelle ou automatique de fichiers texte, réplication avec des bases de données d’entreprises ou d’autres systèmes d’information. Adobe Campaign vous permet d’intégrer des données d’historique marketing, d’informations d’achat, de préférences, de gestion de la relation client et toute donnée d’identification personnelle pertinente dans une vue consolidée afin d’analyser et d’agir.

Dans Adobe Campaign, les destinataires sont les profils par défaut ciblés pour l&#39;envoi des diffusions (emails, SMS, etc.). Grâce aux données de destinataires stockées dans la base de données, vous pourrez filtrer la cible qui recevra toute diffusion donnée et ajouter les données de personnalisation à votre contenu de diffusion. Il existe d&#39;autres types de profils dans la base de données qui sont conçus pour d&#39;autres utilisations. Par exemple, les profils d&#39;adresses de contrôle sont destinés à tester votre diffusions avant leur envoi à la cible finale.

: bulb: Les principes de base de la gestion des profils sont expliqués dans [cette section](audiences.md).

: bulb: Découvrez comment ajouter des profils à Campaign dans [cette section](import.md).

## Segmentation ciblée {#targeted-segmentation}

Pour vous permettre de mettre en place des offres hautement ciblées et différenciées, Adobe Campaign intègre des fonctionnalités d&#39;analyse et ciblage. Grâce aux fonctionnalités d&#39;analyse descriptive, vous avez la possibilité d&#39;analyser les informations en amont et en aval de vos campagnes marketing. D&#39;autre part, les fonctionnalités de gestion de filtres et l&#39;éditeur graphique de requête vous permettent de filtrer les populations d&#39;inscrits, d&#39;échantillonner ou de créer des groupes cibles sur un nombre illimité de critères.

La fonctionnalité de Data Management avancée étend les fonctionnalités de traitement des données. Il simplifie et optimise le processus de ciblage en incluant des données qui ne sont pas modélisées dans le datamart.

: bulb: Pour en savoir plus sur la segmentation, la création et la personnalisation d&#39;audiences, consultez [cette section](audiences.md).

## Orchestration de campagnes cross-canal {#cross-channel-campaign-orchestration}

Adobe Campaign vous permet de concevoir et d’orchestrer des campagnes ciblées et personnalisées sur plusieurs canaux : e-mail, courrier direct, SMS, notification Push. Une interface unique vous offre toutes les fonctions nécessaires pour planifier, orchestrer, configurer, personnaliser, automatiser, exécuter et mesurer toutes vos campagnes et communications.

: bulb: Découvrez comment concevoir, planifier et exécuter une campagne dans [cette section](campaigns.md).

## Workflows

Adobe Campaign propose un environnement graphique qui permet de construire des processus complexes englobant segmentation, exécution de campagnes, manipulation de fichiers, validations, etc. Un workflow permet par exemple de télécharger un fichier depuis un serveur, de le décompresser et d&#39;importer ses enregistrements dans la base de données Adobe Campaign.

Un workflow peut également faire intervenir des utilisateurs, pour leur affecter une tâche ou demander la validation d&#39;une tâche accomplie. Ainsi, il est possible d&#39;assigner une tâche à un ou plusieurs utilisateurs qui seront chargés de saisir son contenu ou spécifier sa cible, puis de faire valider un BAT avant d&#39;envoyer un message.

Les workflows peuvent intervenir dans différents contextes, par exemple :

* Ciblage afin de gérer des audiences ou envoyer des messages.
* Data management (ETL) pour manipuler des données.
* Import de données dans la base de Campaign.
* Processus techniques tels que les tâches de nettoyage de la base (cleanup), la récupération des informations de tracking, etc.

: bulb: Découvrez comment concevoir et exécuter des workflows dans [cette section](../config/workflows.md).

## Rapports et analyse {#analysis-and-reporting}

Adobe Campaign vous permet de surveiller et d’interpréter le comportement de vos clients en enrichissant progressivement leurs données et profils. Les outils de rapports et d&#39;analyse vous permettent de tirer parti de chaque nouvelle campagne, de mieux cible vos initiatives marketing et d&#39;optimiser leur impact et leur retour sur investissement.

: bulb:  Pour en savoir plus sur les fonctionnalités de rapport et de suivi, consultez [cette section](reporting.md).

## Intégrations d&#39;Adobe Experience Cloud {#adobe-experience-cloud-integrations}

Vous pouvez combiner les fonctionnalités de diffusion et les fonctionnalités de Gestion de campagne avancées d’Adobe Campaign avec un ensemble de solutions créées pour vous aider à personnaliser l’expérience de vos utilisateurs : Adobe Experience Manager, Adobe Analytics, Adobe Target ou Adobe Experience Cloud se déclenchent par exemple. Vous pouvez également intégrer à Adobe IMS et vous connecter à Campaign avec votre Adobe ID.

: bulb: Découvrez comment intégrer les services et solutions d&#39;Adobe dans [cette section](../connect/integration.md).

## En savoir plus sur les fonctionnalités de Campaign {#core-capabilities-and-add-ons}

Adobe Campaign offre un ensemble de fonctionnalités pour vous aider à mettre en oeuvre et à optimiser les fonctionnalités de marketing de conversation en fonction de vos besoins et de votre architecture. Certaines d&#39;entre elles sont des fonctionnalités de base et d&#39;autres dépendent de l&#39;installation d&#39;un package et de votre configuration. Une description détaillée du produit est disponible ici : [Description du produit Adobe Campaign v8](https://helpx.adobe.com/fr/legal/product-descriptions/adobe-campaign-classic---product-description.html).

: bulb: Vous connaissez déjà le Campaign Classic ? Découvrez les principales différences entre le Campaign Classic et Campaign v8 dans [cette page](capability-matrix.md).

## Espace de travail et personnalisation

Campaign Workspace est disponible via la console client.

: bulb:  Découvrez comment utiliser l&#39;espace de travail Campaign dans [cette section](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html)

: bulb:  Découvrez comment personnaliser des listes dans [cette section](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html)

Vous pouvez également accéder à certaines fonctionnalités via le Web.

