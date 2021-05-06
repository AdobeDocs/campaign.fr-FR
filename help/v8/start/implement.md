---
solution: Campaign Classic
product: campaign
title: Directives de mise en oeuvre
description: Découvrez comment implémenter Campaign v8
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
translation-type: tm+mt
source-git-commit: 6fee88c2bcfade752d45712adeab50e199f0c07c
workflow-type: tm+mt
source-wordcount: '1153'
ht-degree: 3%

---

# Instructions de mise en oeuvre de Campaign

Dans cette section, vous apprendrez comment adapter l&#39;Adobe Campaign aux exigences de votre société. Suivez les instructions suivantes pour structurer et organiser votre mise en oeuvre.

1. **Définir les paramètres** : accorder l’accès, partager la console client, configurer des canaux (courrier électronique, push, sms)
1. **Préparez votre environnement** : importer des profils, créer des audiences, concevoir des processus et des modèles de campagne, créer des règles de typologie
1. **Personnalisez votre instance** : créer de nouveaux champs de données, ajouter des tableaux/schémas
1. **Étendez votre déploiement** : connexion à des solutions d&#39;Adobe, d&#39;autres produits et systèmes - connecteurs, paramètres multisolution

## Avant de commencer

Cette section contient des informations à l’intention des développeurs spécifiques à leur mise en oeuvre sur la protection de la vie privée et la sécurité avant de commencer.

### Confidentialité

Adobe Campaign est fourni avec des processus et des paramètres qui vous permettent d’utiliser Campaign en conformité avec les lois applicables en matière de confidentialité des données et avec vos préférences de destinataire. Vous pouvez gérer :

* **Acquisition** de données : Adobe Campaign vous permet de collecter des données, y compris des informations personnelles et sensibles. Il est donc essentiel de recevoir et de gérer le consentement de vos destinataires. Pour en savoir plus, consultez la [documentation Campaign Classic](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#data-acquisition)

* **Consentement de l&#39;utilisateur et conservation** des données : Découvrez comment obtenir le consentement de l’utilisateur, configurer des mécanismes d’abonnement d’inclusion doublon, faciliter l’exclusion et configurer la rétention des données dans la documentation sur la confidentialité des  [Campaign Classic](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#consent)

* **Règles relatives** à la protection des données et de la vie privée : pour plus d’informations sur le Règlement général sur la protection des données (RMPD) de l’Union européenne, la Loi sur la protection des renseignements personnels des consommateurs (LPCCE) de Californie et d’autres exigences internationales en matière de protection des renseignements personnels, consultez la  [documentation sur la protection des renseignements personnels des ](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html) Campaign Classic.

### Sécurité

Découvrez les directives et les principes de sécurité avec Adobe Campaign dans [liste de contrôle de sécurité Campaign](../config/security.md))

## Définir les paramètres Campaign

### Ajouter les utilisateurs et octroyer des autorisations

Vous pouvez ajouter manuellement des utilisateurs à la campagne et les associer à des groupes, en les alignant avec votre hiérarchie de rôles. Les utilisateurs pourront alors se connecter et accéder aux données et autorisations qui leur conviennent.

:flèche_supérieur_droite : Découvrez comment ajouter des utilisateurs à Adobe Campaign dans [cette section](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html?lang=en#getting-started).

### Installation de la console client Campaign

La principale interface utilisateur de l&#39;application est un client riche, en d&#39;autres termes, une application native (Windows) qui communique avec le serveur d&#39;applications Adobe Campaign uniquement avec les protocoles Internet standard (SOAP, HTTP, etc.). La console client Adobe Campaign offre une grande convivialité pour la productivité, utilise très peu de bande passante (grâce à l&#39;utilisation d&#39;un cache local) et est conçue pour un déploiement facile. Cette console peut être déployée à partir d&#39;un navigateur Internet, peut être mise à jour automatiquement et ne nécessite aucune configuration réseau spécifique car elle ne génère que du trafic HTTP(S).

: bulb: [En savoir plus sur Campaign Client Console](connect.md).

## Préparer votre environnement

Avant de commencer à envoyer des messages et à créer des campagnes marketing, vous devez :

1. Importer des profils et créer des audiences

   Campaign vous aide à ajouter des contacts à la base de données Cloud. Vous pouvez charger un fichier, planifier et automatiser plusieurs mises à jour des contacts, collecter des données sur le Web ou saisir des informations sur les profils directement dans la table du destinataire.

   : bulb: [Découvrez comment importer des profils](import.md).

   Les Audiences sont regroupées en listes et peuvent être créées par le biais de flux de travaux. Ils peuvent ensuite être ciblés dans des diffusions inter-canaux.

   : bulb: [Découvrez comment définir des audiences](audiences.md).

1. Création de modèles

   Les campagnes, diffusions, tâches ou workflows sont tous basés sur un modèle qui stocke les paramètres et fonctionnalités clés. Un modèle intégré est fourni pour chaque composant, pour lequel aucune configuration spécifique n’a été définie. Vous devez configurer et adapter les modèles en fonction de vos besoins et les rendre disponibles pour les utilisateurs finaux.

   :flèche_supérieur_droite : [En savoir plus sur les modèles de courrier électronique](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html)

   :flèche_supérieur_droite : Découvrez comment utiliser les modèles de campagne dans [cette page](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-templates.html?lang=en#orchestrating-campaigns)

   :flèche_supérieur_droite : Découvrez comment configurer un modèle de processus dans [cette page](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html?lang=en#workflow-templates)

1. Configurer des règles de typologie

   Tirez parti des règles de Typologies de campagne pour filtrer, contrôler et surveiller l&#39;envoi de diffusions. Par exemple, les règles de fatigue contrôlent la fréquence et la quantité de messages pour éviter la sollicitation excessive de destinataires. Une fois implémentées, les règles de typologie sont référencées dans les diffusions.

   :flèche_supérieur_droite : [En savoir plus sur les typologies et la gestion de la fatigue](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/about-campaign-typologies.html?lang=en#orchestrating-campaigns)

1. Familiarisez-vous avec le modèle de données intégré Campaign

   Un modèle de données d’usine est fourni avec Adobe Campaign. Pour mettre en oeuvre et personnaliser votre environnement, vous devez connaître les tableaux intégrés du modèle de données Adobe Campaign et leur interaction.

   : bulb: [En savoir plus sur le modèle de données Campaign](../dev/datamodel.md).

## Personnaliser votre instance

Vous pouvez personnaliser de nombreuses zones et fonctionnalités Campaign. La plupart de nos clients personnalisent trois choses :

1. **Tableaux et schémas**

   Adobe Campaign s’accompagne de schémas courants pour identifier des données telles que : destinataires, logs de diffusion, abonnements, etc.

   : bulb: Reportez-vous à cette section pour en savoir plus sur le modèle de données intégré [Campaign](../dev/datamodel.md).

   : bulb: Vous pouvez étendre les schémas existants ou créer de nouveaux schémas à partir de rien. En savoir plus sur [cette page](../dev/customize.md).

1. **Tableaux de bord et listes**

   Vous pouvez facilement configurer des listes, ajouter et supprimer des champs et personnaliser des colonnes.

   : bulb: Découvrez comment gérer les filtres et les listes à Campaign dans [cette page](../dev/customize.md#gs-lists-and-filters).

   Vous pouvez également créer de nouveaux tableaux de bord pour afficher les données Campaign en fonction de vos besoins.

   : bulb: En savoir plus sur [cette page](../dev/customize.md#gs-custom-dashboards).

1. **Rapports**

   Campaign fournit un ensemble de rapports intégrés sur la surveillance des diffusions, les URL et les flux de clics, le suivi, les indicateurs de délivrabilité, etc.

   En complément des rapports intégrés, Adobe Campaign permet de générer des rapports dans différents contextes et de répondre à des besoins variés. Les principes d&#39;utilisation et les modes de mise en oeuvre sont détaillés dans ce document.

   : bulb: Pour en savoir plus sur les fonctionnalités de rapports à Campaign, voir [cette page](reporting.md).


## Configuration de l’automatisation de campagne

Pour orchestrer des campagnes marketing complexes vers différentes audiences sur plusieurs canaux, tirez parti des fonctionnalités d’automatisation Campaign.

* Workflows : gestion des processus et des données

* Abonnements et landings page

* Règles de typologie : gestion de la fatigue et du contrôle

## Étendre votre déploiement

### Implémentation de solutions multiples

Si vous utilisez d&#39;autres solutions d&#39;Adobe, vous pouvez les connecter à votre environnement Campaign et combiner des fonctionnalités.

* Campaign - Journey Orchestration
* Campaign - CDP en temps réel
* Campaign - Déclencheurs Experience Cloud
* Campaign - Experience Manager
* Campaign - Cible
* Campaign - Audience Manager / Service principal Personnel
* Campaign - Actif
* Campaign - Connecteurs de données Analytics


Vous pouvez également utiliser l’authentification unique (SSO) pour vous connecter à Campaign. En savoir plus sur [cette page](connect.md).

: bulb: Découvrez la liste complète de la solution d&#39;Adobe qui peut être intégrée à Adobe Campaign [dans cette page](../connect/integration.md).

### Connecteurs

Connectez Campaign à des systèmes tiers afin de combiner un large éventail de fonctionnalités et d’automatiser les processus.

: bulb: Pour en savoir plus sur les connecteurs disponibles, consultez [cette section](../connect/integration.md).

**Connectez votre gestion de la relation client à Campaign**

Vous pouvez connecter votre plateforme Adobe Campaign à vos systèmes tiers CRM et synchroniser les données : contacts, comptes, achats, etc.

: bulb: Découvrez comment connecter votre système de gestion de la relation client à Campaign dans [cette section](../connect/integration.md#gs-crm-connectors)

**Connexion à une base de données externe**

Vous pouvez connecter la base de données Campaign Cloud à des systèmes externes via le module Federated Data Access (FDA).

: bulb: Découvrez comment configurer le module Campaign FDA pour définir les paramètres d&#39;accès dans [cette section](../connect/integration.md#gs-fda)
