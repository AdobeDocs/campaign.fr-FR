---
solution: Campaign v8
product: Adobe Campaign
title: Prise en main de Campaign v8
description: Découvrez les principales fonctionnalités, l’interface utilisateur et les directives globales
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
exl-id: 04b12907-3cb1-40f1-90b8-1524d84edf2d,e3e9b514-a69d-4650-b1b1-1b76b4f3d63f
source-git-commit: ab7e458db5ad5696d144c17f6e89e4437a476d11
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 88%

---

# Prise en main d’Adobe Campaign{#gs-ac-v8}

Adobe Campaign propose une plateforme qui permet de concevoir des expériences client cross-canal ainsi qu’un environnement pour l’orchestration visuelle de campagnes, la gestion d’interactions en temps réel et l’exécution cross-canal.

En utilisant Campaign, vous pouvez :

* **Favoriser la personnalisation et l’engagement par le biais d’une vue unique et accessible du client**
* **Intégrer les canaux e-mail, mobiles, en ligne et hors ligne au parcours client**
* **Automatiser la diffusion de messages et d’offres pertinents et opportuns**

![](assets/ac-capabilities.png)

## Integrated Customer Profile {#integrated-customer-profile}

Les profils sont centralisés dans une puissante base de données cloud. Il existe de nombreux mécanismes permettant d’acquérir des profils et de créer cette base de données : collecte en ligne par le biais de formulaires web, importation manuelle ou automatique de fichiers texte, réplication avec des bases de données d’entreprises ou d’autres systèmes d’information. Adobe Campaign vous permet d’intégrer des données d’historique marketing, des informations d’achat, des préférences, des données CRM et des données d’informations d’identification personnelles pertinentes dans une vue consolidée afin d’effectuer une analyse et de prendre des mesures.

Dans Adobe Campaign, les destinataires sont les profils par défaut ciblés pour l’envoi des diffusions (e-mails, SMS, etc.). Grâce aux données de destinataires stockées dans la base, vous pouvez filtrer la cible recevant toute diffusion donnée et ajouter les données de personnalisation à votre contenu de diffusion. Il existe d’autres types de profils dans la base de données qui sont conçus pour d’autres utilisations. Par exemple, les profils d’adresses de contrôle sont destinés à tester vos diffusions avant leur envoi à la cible finale.

[!DNL :bulb:] Les notions de base de la gestion des profils sont décrites dans [cette section](audiences.md).

[!DNL :bulb:] Découvrez comment ajouter des profils à Campaign dans [cette section](import.md).

## Segmentation ciblée {#targeted-segmentation}

Pour vous permettre de mettre en place des offres hautement ciblées et différenciées, Adobe Campaign intègre des fonctionnalités de ciblage et de segmentation simples d’utilisation. Grâce aux fonctionnalités d’analyse descriptive, vous avez la possibilité d’analyser les informations en amont et en aval de vos campagnes marketing. D’autre part, les fonctionnalités de gestion de filtres et l’éditeur graphique de requête vous permettent de filtrer les populations d’inscrits, ainsi que d’échantillonner ou de créer des groupes cibles en fonction d’un nombre de critères illimité.

Les fonctionnalités avancées de Data Management proposent une extension des capacités de traitement des données. Elles permettent de simplifier et d’optimiser le processus de ciblage en incluant des données non modélisées dans le datamart.

[!DNL :bulb:] En savoir plus sur la segmentation, la création et la personnalisation d’audiences dans [cette section](audiences.md).

## Orchestration de campagnes cross-canal {#cross-channel-campaign-orchestration}

Adobe Campaign vous permet de concevoir et d’orchestrer des campagnes ciblées et personnalisées sur plusieurs canaux tels que l’e-mail, le courrier, les SMS, les notifications push, etc. Vous bénéficiez dans une seule interface de toutes les fonctions nécessaires pour planifier, orchestrer, configurer, personnaliser, automatiser, exécuter et mesurer l’ensemble des campagnes et communications.

[!DNL :bulb:] Découvrez comment concevoir, planifier et exécuter une campagne dans [cette section](campaigns.md).

## Workflows

Adobe Campaign propose un environnement graphique qui permet de construire des processus complexes englobant segmentation, exécution de campagnes, manipulation de fichiers, validations, etc. Un workflow permet par exemple de télécharger un fichier depuis un serveur, de le décompresser et d&#39;importer ses enregistrements dans la base de données Adobe Campaign.

Un workflow peut également faire intervenir des utilisateurs, pour leur affecter une tâche ou demander la validation d&#39;une tâche accomplie. Ainsi, il est possible d&#39;assigner une tâche à un ou plusieurs utilisateurs qui seront chargés de saisir son contenu ou spécifier sa cible, puis de faire valider un BAT avant d&#39;envoyer un message.

Les workflows peuvent intervenir dans différents contextes, par exemple :

* Ciblage afin de gérer des audiences ou envoyer des messages.
* Data management (ETL) pour manipuler des données.
* Import de données dans la base de Campaign.
* Processus techniques tels que les tâches de nettoyage de la base (cleanup), la récupération des informations de tracking, etc.

[!DNL :bulb:] Découvrez comment concevoir et exécuter des workflows dans [cette section](../config/workflows.md).

## Reporting et analyse {#analysis-and-reporting}

Adobe Campaign vous permet de suivre et comprendre les comportements de vos clients en enrichissant progressivement leurs données et profil. Grâce aux outils de reporting et d’analyse, vous capitalisez sur chaque nouvelle campagne, bénéficiez d’un meilleur ciblage de vos actions marketing et optimisez leur impact ainsi que leur retour sur investissement.

[!DNL :bulb:] Pour en savoir plus sur les fonctionnalités de rapport et de suivi, consultez  [cette section](reporting.md).

## Intégrations d’Adobe Experience Cloud {#adobe-experience-cloud-integrations}

Vous pouvez combiner les fonctionnalités de diffusion et de gestion de campagnes avancées d’Adobe Campaign avec un ensemble de solutions créées pour vous aider à personnaliser l’expérience de vos utilisateurs, notamment Adobe Experience Manager, Adobe Analytics, Adobe Target ou les triggers Adobe Experience Cloud.

[!DNL :bulb:] Découvrez comment intégrer les services et solutions d’Adobe dans [cette section](../connect/integration.md).

## En savoir plus sur les fonctionnalités de Campaign {#core-capabilities-and-add-ons}

Adobe Campaign vous propose un ensemble de fonctionnalités qui vous permettent d’implémenter et optimiser les fonctionnalités de marketing conversationnel selon vos besoins et votre architecture. Certaines de ces fonctionnalités sont intégrées. D’autres dépendent de l’installation d’un package au sein de votre configuration. Une description détaillée du produit est disponible ici : [Description du produit Adobe Campaign v8](https://helpx.adobe.com/fr/legal/product-descriptions/adobe-campaign-classic---product-description.html).

[!DNL :bulb:] Vous connaissez déjà Campaign Classic ? Découvrez les principales différences entre Campaign Classic et Campaign v8 sur [cette page](capability-matrix.md).

## Espace de travail et personnalisation

L’espace de travail Campaign est disponible via la [console cliente](../dev/general-architecture.md).

[!DNL :bulb:] [En savoir plus sur la console client Campaign](../start/connect.md).

L&#39;espace de travail de Campaign peut être adapté selon vos besoins.

[!DNL :arrow_upper_right:]  Découvrez comment utiliser l&#39;espace de travail Campaign dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-workspace.html?lang=fr)

[!DNL :arrow_upper_right:]  Découvrez comment personnaliser des listes dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=fr)

Vous pouvez également accéder à certaines fonctionnalités via le Web.

[!DNL :bulb:] [En savoir plus sur l’accès web de Campaign](../start/connect.md#web-access).


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

