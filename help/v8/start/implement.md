---
solution: Campaign v8
product: Adobe Campaign
title: Instructions d’implémentation
description: Découvrez comment implémenter Campaign v8
feature: Vue d'ensemble
role: Data Engineer
level: Beginner
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
source-git-commit: 167730cc3e81ee47f02bcdbc2c39fe793a99c534
workflow-type: tm+mt
source-wordcount: '1193'
ht-degree: 4%

---

# Instructions de mise en oeuvre de Campaign

Dans cette section, vous apprendrez comment adapter Adobe Campaign aux exigences de votre entreprise. Suivez les instructions ci-après pour structurer et organiser votre mise en oeuvre.

1. **Définir les paramètres** : accorder l’accès, partager la console cliente, configurer les canaux (email, push, sms)
1. **Préparez votre environnement** : importer des profils, créer des audiences, concevoir des modèles de workflow et de campagne, créer des règles de typologie
1. **Personnalisez votre instance** : créer des champs de données, ajouter des tableaux/schémas
1. **Étendez votre déploiement** : se connecter aux solutions Adobe, à d’autres produits et systèmes - connecteurs, paramètres multisolution

>[!CAUTION]
>
>Avec **Cloud Services gérés par Campaign**, votre environnement et votre configuration initiale ont été définis par Adobe, conformément aux termes de votre contrat de licence. Vous n’êtes pas autorisé à modifier les packages intégrés, les schémas ou les rapports installés.
>
>Si vous devez utiliser un module complémentaire Campaign ou une fonctionnalité spécifique qui n’a pas été configurée pour vous, vous devez contacter **l’assistance clientèle Adobe**.

## Avant de commencer

Cette section contient des informations critiques sur la confidentialité et la sécurité qui doivent être examinées et prises en compte avant même de commencer la mise en oeuvre réelle.

### Confidentialité

Adobe Campaign est fourni avec des processus et des paramètres qui vous permettent d’utiliser Campaign conformément aux lois applicables sur la confidentialité des données et aux préférences de votre destinataire. Vous pouvez gérer :

* **Acquisition** de données : Adobe Campaign vous permet de collecter des données, notamment des informations personnelles et sensibles. Il est donc essentiel que vous receviez et gérez le consentement de vos destinataires. En savoir plus dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#data-acquisition)

* **Consentement de l’utilisateur et conservation** des données : Découvrez comment obtenir le consentement de l’utilisateur, configurer des mécanismes d’abonnement au double opt-in, faciliter l’opt-out et configurer la rétention des données dans la documentation sur la confidentialité du  [Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#consent)

* **Réglementations relatives à la confidentialité et à la protection des** données : pour plus d’informations sur le Règlement général sur la protection des données (RGPD) de l’Union européenne, le California Consumer Privacy Act (CCPA) et d’autres exigences internationales en matière de confidentialité, reportez-vous à la  [documentation sur la confidentialité des ](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html) Campaign Classic et sur la manière dont ces réglementations affectent votre organisation et Adobe Campaign.

### Sécurité

Découvrez les consignes et les principes de sécurité avec Adobe Campaign dans la [liste de contrôle de sécurité de Campaign](../config/security.md).

## Définition des paramètres de Campaign

### Ajout d’utilisateurs et octroi d’autorisations

Vous pouvez ajouter manuellement des utilisateurs à Campaign et les associer à des groupes, en fonction de votre hiérarchie de rôles. Les utilisateurs pourront alors se connecter et accéder aux données et aux autorisations qui leur conviennent.

:[!DNL :arrow_upper_right:] : Découvrez comment ajouter des utilisateurs à Adobe Campaign dans [cette section](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html?lang=en#getting-started).

### Installation de la console cliente Campaign

La principale interface utilisateur de l’application est un client riche, c’est-à-dire une application native (Windows) qui communique avec le serveur applicatif Adobe Campaign uniquement avec les protocoles Internet standard (SOAP, HTTP, etc.). La console cliente Adobe Campaign offre une grande convivialité pour la productivité, utilise très peu de bande passante (grâce à l’utilisation d’un cache local) et est conçue pour un déploiement facile. Cette console peut être déployée à partir d’un navigateur Internet, peut être mise à jour automatiquement et ne nécessite aucune configuration réseau spécifique, car elle ne génère que du trafic HTTP(S).

[!DNL :bulb:] [En savoir plus sur la console cliente Campaign](connect.md).

## Préparation de votre environnement

Avant de commencer à envoyer des messages et de créer des campagnes marketing, vous devez :

1. Importer des profils et créer des audiences

   Campaign vous aide à ajouter des contacts à la base de données Cloud. Vous pouvez charger un fichier, planifier et automatiser plusieurs mises à jour de contact, collecter des données sur le Web ou saisir des informations de profil directement dans la table des destinataires.

   [!DNL :bulb:] [Découvrez comment importer des profils](import.md).

   Les audiences sont regroupées dans des listes et peuvent être créées par le biais de workflows. Ils peuvent ensuite être ciblés dans les diffusions cross-canal.

   [!DNL :bulb:] [Découvrez comment définir des audiences](audiences.md).

1. Créer des modèles

   Les opérations, diffusions, traitements ou workflows sont tous basés sur un modèle qui stocke les paramètres et fonctionnalités clés. Un modèle intégré est fourni pour chaque composant, pour lequel aucune configuration spécifique n’a été définie. Vous devez configurer et adapter les modèles selon vos besoins et les mettre à la disposition des utilisateurs finaux.

   [!DNL :arrow_upper_right:] [En savoir plus sur les modèles d&#39;email](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html)

   [!DNL :arrow_upper_right:] Découvrez comment utiliser des modèles de campagne dans  [cette page](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-templates.html?lang=en#orchestrating-campaigns)

   [!DNL :arrow_upper_right:] Découvrez comment configurer un modèle de workflow dans  [cette page](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html?lang=en#workflow-templates)

1. Configuration des règles de typologie

   Tirez parti des règles de typologies de Campaign pour filtrer, contrôler et contrôler l&#39;envoi des diffusions. Par exemple, les règles de fatigue contrôlent la fréquence et la quantité des messages pour éviter une sur-sollicitation des destinataires. Une fois mises en oeuvre, les règles de typologie sont référencées dans les diffusions.

   [!DNL :arrow_upper_right:] [En savoir plus sur les typologies et la gestion de la fatigue](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/about-campaign-typologies.html?lang=en#orchestrating-campaigns)

1. Familiarisez-vous avec le modèle de données intégré de Campaign

   Un modèle de données d’usine est fourni avec Adobe Campaign. Pour mettre en oeuvre et personnaliser votre environnement, vous devez connaître les tables intégrées du modèle de données Adobe Campaign et leurs relations les unes avec les autres.

   [!DNL :bulb:] [En savoir plus sur le modèle de données Campaign](../dev/datamodel.md).

## Personnalisation de votre instance

Vous pouvez personnaliser de nombreuses zones et fonctionnalités de Campaign. La plupart de nos clients personnalisent trois éléments :

1. **Tableaux et schémas**

   Adobe Campaign est fourni avec des schémas courants pour identifier les données, tels que : destinataires, logs de diffusion, abonnements, etc.

   [!DNL :bulb:] Reportez-vous à cette section pour en savoir plus sur le modèle de données intégré de  [Campaign](../dev/datamodel.md).

   [!DNL :bulb:] Vous pouvez étendre les schémas existants ou créer de nouveaux schémas à partir de zéro. En savoir plus sur [cette page](../dev/customize.md).

1. **Tableaux de bord et listes**

   Vous pouvez facilement configurer des listes, ajouter et supprimer des champs et personnaliser des colonnes.

   [!DNL :bulb:] Découvrez comment gérer les filtres et les listes dans Campaign sur  [cette page](../dev/customize.md#gs-lists-and-filters).

   Vous pouvez également créer de nouveaux tableaux de bord pour afficher les données de Campaign en fonction de vos besoins.

   [!DNL :bulb:][ En savoir plus sur cette page](../dev/customize.md#gs-custom-dashboards).

1. **Rapports**

   Campaign fournit un ensemble de rapports intégrés sur la surveillance des diffusions, les URL et les flux de clics, le suivi, les indicateurs de délivrabilité, etc.

   En complément des rapports intégrés, Adobe Campaign permet de générer des rapports dans différents contextes et de répondre à des besoins variés. Les principes d&#39;utilisation et les modes de mise en oeuvre sont présentés dans ce document.

   [!DNL :bulb:] Pour en savoir plus sur les fonctionnalités de reporting dans Campaign, consultez  [cette page](reporting.md).


## Configuration de l’automatisation des campagnes

Pour orchestrer des campagnes marketing complexes vers différentes audiences sur plusieurs canaux, utilisez les fonctionnalités d’automatisation de Campaign.

* Workflows : gestion des processus et des données

* Abonnements et landing pages

* Règles de typologie : Gestion de la fatigue et du contrôle

## Étendre votre déploiement

### Mise en oeuvre multi-solutions

Si vous utilisez d’autres solutions Adobe, vous pouvez les connecter à votre environnement Campaign et combiner des fonctionnalités.

* Campaign - Journey Orchestration
* Campaign - CDP en temps réel
* Campaign - Triggers Experience Cloud
* Campaign - Experience Manager
* Campaign - Target
* Campaign - Audience Manager / People core service
* Campaign - Asset
* Campaign - Connecteurs de données Analytics


Vous pouvez également utiliser l’authentification unique (SSO) pour vous connecter à Campaign. En savoir plus sur [cette page](connect.md).

[!DNL :bulb:] Découvrez la liste complète de la solution Adobe qui peut être intégrée à Adobe Campaign  [dans cette page](../connect/integration.md).

### Connecteurs

Connectez Campaign à des systèmes tiers pour combiner un large éventail de fonctionnalités et automatiser les processus.

[!DNL :bulb:] Pour en savoir plus sur les connecteurs disponibles, consultez  [cette section](../connect/integration.md).

**Connexion de votre CRM à Campaign**

Vous pouvez connecter votre plateforme Adobe Campaign à vos systèmes tiers CRM et synchroniser les données : contacts, comptes, achats, etc.

[!DNL :bulb:] Découvrez comment connecter votre système CRM à Campaign dans  [cette section](../connect/integration.md#gs-crm-connectors)

**Connexion à une base de données externe**

Vous pouvez connecter la base de données Campaign Cloud à des systèmes externes via le module Federated Data Access (FDA) .

[!DNL :bulb:] Découvrez comment configurer le module Campaign FDA pour définir les paramètres d&#39;accès dans  [cette section](../connect/integration.md#gs-fda)
