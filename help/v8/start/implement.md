---
title: Instructions d'implémentation
description: Découvrez comment implémenter Campaign v8
feature: Overview
role: User
level: Intermediate
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '1146'
ht-degree: 85%

---

# Instructions d’implémentation de Campaign{#gs-implementation}

Dans cette section, découvrez comment adapter Adobe Campaign aux exigences de votre entreprise. Suivez les instructions suivantes pour structurer et organiser votre implémentation.

1. **Définition des paramètres** : octroi d’accès, partage de la console cliente, configuration de canaux (e-mail, notification push, SMS). [En savoir plus](#implementation-ac-settings)
1. **Préparation de votre environnement** : importation de profils, création d’audiences, conception de modèles de workflows et de campagnes, création de règles de typologie. [En savoir plus](#implementation-prepare-your-env)
1. **Personnalisation de votre instance** : création de champs de données, ajout de tableaux/schémas. [En savoir plus](#implementation-custom-your-instance)
1. **Automatisation de vos processus** : configuration des fonctionnalités d’automatisation d’Adobe Campaign. [En savoir plus](#implementation-automation)
1. **Extension de votre déploiement** : connexion aux solutions, autres produits et systèmes Adobe (connecteurs, paramètres de solutions multiples). [En savoir plus](#implementation-extend)

>[!CAUTION]
>
>Avec **Campaign Managed Cloud Services**, votre environnement et votre configuration initiale ont été définis par Adobe, conformément aux termes de votre contrat de licence. Vous n’avez pas l’autorisation de modifier les modules et les schémas intégrés ou les rapports.
>
>Si vous devez utiliser un module complémentaire Campaign ou une fonctionnalité spécifique qui n’a pas été configurée pour vous, vous devez contacter la **personne chargée de votre transition Adobe**.

## Avant de commencer{#before-starting}

Cette section comporte des informations importantes au sujet de la confidentialité et de la sécurité. Celles-ci doivent être passées en revue et prises en compte avant même le démarrage de l&#39;implémentation.

### Confidentialité{#implementation-privacy}

Adobe Campaign s’accompagne de processus et de paramètres qui vous permettent d’utiliser l’application conformément aux lois applicables en matière de confidentialité des données et selon les préférences des destinataires. Ce que vous pouvez gérer :

* **Acquisition des données** : Adobe Campaign vous permet de collecter des données, y compris des informations personnelles et sensibles. Il est donc essentiel que vous receviez et gériez le consentement de vos destinataires.

  Apprenez-en davantage en consultant la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=fr#data-acquisition){target="_blank"}.

* **Consentement de l’utilisateur ou de l’utilisatrice et conservation des données** : vous devez obtenir le consentement de l’utilisateur ou de l’utilisatrice, configurer des mécanismes d’abonnement au double opt-in, faciliter la désinscription et configurer la conservation des données.

  Apprenez-en davantage en consultant la [documentation sur la confidentialité de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=fr#consent){target="_blank"}.

* **Réglementations relatives à la confidentialité et à la protection des données** : voir [cette section](privacy.md) pour plus d’informations sur les exigences en matière de confidentialité et sur la manière dont ces réglementations impactent votre entreprise et Adobe Campaign.

### Sécurité

Découvrez les instructions et principes relatifs à la sécurité d&#39;Adobe Campaign dans la [liste de contrôle de sécurité Campaign](../config/security.md).

## Définition des paramètres de Campaign{#implementation-ac-settings}

### Ajout d&#39;utilisateurs et octroi des autorisations{#implementation-add-users}

Vous pouvez ajouter manuellement des utilisateurs à Campaign et les associer à des groupes en les alignant avec votre hiérarchie de rôles. Les utilisateurs pourront alors se connecter et accéder aux données et autorisations adéquates.

Découvrez comment ajouter des utilisateurs à Adobe Campaign dans [cette section](../start/gs-permissions.md).

### Installer la console cliente Campaign{#implementation-install-console}

La principale interface utilisateur de l’application est un client riche. En d’autres termes, il s’agit d’une application native (Windows) qui communique avec le serveur d’applications Adobe Campaign uniquement via les protocoles Internet standard (SOAP, HTTP, etc.). La console cliente Adobe Campaign est très conviviale pour la productivité, utilise très peu de bande passante (grâce à l’utilisation d’un cache local) et est conçue pour être facilement déployée. Cette console peut être déployée à partir d’un navigateur Internet et mise à jour automatiquement. En outre, elle ne nécessite aucune configuration réseau spécifique, car elle génère uniquement du trafic HTTP(S).

[En savoir plus sur la console cliente Campaign](connect.md).

## Préparation de votre environnement{#implementation-prepare-your-env}

Avant de commencer à envoyer des messages et à créer des campagnes marketing, vous devez :

1. **Importer des profils et créer des audiences**

   Campaign vous aide à ajouter des contacts à la base de données cloud. Vous pouvez charger un fichier, planifier et automatiser plusieurs mises à jour des contacts, collecter des données sur le Web ou saisir des informations de profil directement dans la table des destinataires.

   [Découvrez comment importer des profils](import.md).

   Les audiences sont regroupées dans des listes et peuvent être créées par le biais de workflows. Elles peuvent ensuite être ciblées dans des diffusions cross-canal.

   [Découvrez comment définir des audiences](audiences.md).

1. **Utiliser des modèles**

   Les campagnes, diffusions, traitements ou workflows sont tous basés sur un modèle qui stocke les paramètres et fonctionnalités clés. Un modèle natif est fourni pour chaque composant, pour lequel aucune configuration spécifique n&#39;a été définie. Vous devez configurer et adapter les modèles en fonction de vos besoins, puis les rendre disponibles auprès des utilisateurs finaux.


   Découvrez comment utiliser les modèles de campagne dans [cette page](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-templates.html?lang=fr){target="_blank"}.

   Découvrez comment configurer un modèle de workflow dans [cette page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=fr){target="_blank"}.

   En savoir plus sur les modèles d’email dans [Documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=fr){target="_blank"}.


1. **Configurer les règles de typologie**

   Tirez parti des règles de typologies de Campaign pour filtrer, contrôler et surveiller l&#39;envoi de diffusions. Par exemple, les règles de fatigue contrôlent la fréquence et la quantité de messages pour éviter la sollicitation excessive de destinataires. Une fois implémentées, les règles de typologie sont référencées dans les diffusions.

   En savoir plus sur les typologies et la gestion de la fatigue dans [cette section](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=fr){target="_blank"}.

1. **Se familiariser avec le modèle de données natif de Campaign**

   Un modèle de données d’usine est fourni avec Adobe Campaign. Afin d’implémenter et de personnaliser votre environnement, vous devez connaître les tables natives du modèle de données d’Adobe Campaign ainsi que la manière dont elles sont liées les unes aux autres.

   [En savoir plus sur le modèle de données Campaign](../dev/datamodel.md).

## Personnaliser votre instance{#implementation-custom-your-instance}

Vous pouvez personnaliser de nombreuses zones et fonctionnalités Campaign. La plupart de nos clients personnalisent trois choses :

1. **Tables et schémas**

   Adobe Campaign s’accompagne de schémas courants pour identifier les données tels que : destinataires, logs de diffusion, abonnements, etc.

   Consultez cette section pour en savoir plus sur [Modèle de données intégré à Campaign](../dev/datamodel.md).

   Vous pouvez étendre les schémas existants ou créer de nouveaux schémas à partir de zéro. Apprenez-en davantage en consultant [cette page](../dev/customize.md).

1. **Tableaux de bord et listes**

   Vous pouvez facilement configurer des listes, ajouter et supprimer des champs ou personnaliser des colonnes.

   Découvrez comment gérer les filtres et les listes dans Campaign dans [cette page](../dev/customize.md#gs-lists-and-filters).

   Vous pouvez également créer des tableaux de bord pour afficher les données de Campaign en fonction de vos besoins.

   En savoir plus sur [cette page](../dev/customize.md#gs-custom-dashboards).

1. **Rapports**

   Campaign fournit un ensemble de rapports natifs relatifs à la surveillance des diffusions, aux URL et flux de clics, au tracking, aux indicateurs de délivrabilité, etc.

   En complément des rapports natifs, Adobe Campaign permet de générer des rapports dans différents contextes et de répondre à des besoins variés. Ce document détaille les principes d&#39;utilisation ainsi que les modes d&#39;implémentation.

   En savoir plus sur les fonctionnalités de reporting dans Campaign dans [cette page](../reporting/gs-reporting.md).


## Configuration de l&#39;automatisation des campagnes{#implementation-automation}

Pour orchestrer des campagnes marketing complexes vers différentes audiences sur plusieurs canaux, tirez parti des fonctionnalités d&#39;automatisation de Campaign.

* Utilisez des **workflows** pour gérer les processus et les données. Apprenez-en davantage en consultant [cette documentation](../../automation/workflow/about-workflows.md).

* Configurez les processus d’**abonnement** et les **pages de destination**.  Apprenez-en davantage en consultant [cette page](../start/subscriptions.md).

* Configurez les **règles de typologie** pour définir la gestion de la fatigue et du contrôle.  Apprenez-en davantage en consultant [cette documentation](../../automation/campaign-opt/campaign-typologies.md).


## Extension de votre déploiement{#implementation-extend}

### Implémentation de solutions multiples{#implementation-multi-solutions}

Si vous utilisez d&#39;autres solutions Adobe, vous pouvez les connecter à votre environnement Campaign et ainsi combiner les fonctionnalités.

* Campaign - Journey Orchestration
* Campaign - Real-time CDP
* Campaign - Triggers Experience Cloud
* Campaign - Experience Manager
* Campaign - Target
* Campaign - Audience Manager/People core service
* Campaign - Asset
* Campaign - Connecteurs de données Analytics


Vous pouvez également utiliser l’authentification unique (SSO) pour vous connecter à Campaign. En savoir plus sur [cette page](connect.md).

Découvrez la liste complète de la solution Adobe qui peut être intégrée à Adobe Campaign [dans cette page](../connect/integration.md).

### Connecteurs{#implementation-connectors}

Connectez Campaign à des systèmes tiers afin de combiner un large éventail de fonctionnalités et d&#39;automatiser les processus.

En savoir plus sur les connecteurs disponibles dans [cette section](../connect/integration.md).

**Connexion de votre CRM à Campaign**

Vous pouvez connecter votre plateforme Adobe Campaign à vos systèmes CRM tiers et synchroniser les données : contacts, comptes, achats, etc.

Découvrez comment connecter votre système CRM à Campaign dans [cette section](../connect/integration.md#gs-crm-connectors)

**Connexion à une base de données externe**

Vous pouvez connecter la base de données cloud de Campaign à des systèmes externes via le module Federated Data Access (FDA).

Découvrez comment configurer le module Campaign FDA pour définir les paramètres d’accès dans [cette section](../connect/integration.md#gs-fda)
