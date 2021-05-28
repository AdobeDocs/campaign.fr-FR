---
solution: Campaign v8
product: Adobe Campaign
title: Instructions d’implémentation
description: Découvrez comment implémenter Campaign v8
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
source-git-commit: ab7e458db5ad5696d144c17f6e89e4437a476d11
workflow-type: tm+mt
source-wordcount: '1193'
ht-degree: 84%

---

# Instructions d’implémentation de Campaign

Dans cette section, vous apprendrez comment adapter Adobe Campaign aux exigences de votre société. Suivez les instructions suivantes pour structurer et organiser votre implémentation.

1. **Définition des paramètres** : octroi d’accès, partage de la console client, configuration de canaux (e-mail, push, sms).
1. **Préparation de votre environnement** : import de profils, création d’audiences, conception de modèles de workflows et de campagnes, création de règles de typologie.
1. **Personnalisation de votre instance** : création de champs de données, ajout de tables/schémas.
1. **Extension de votre déploiement** : connexion à des solutions Adobe, autres produits et systèmes - connecteurs, paramètres de solutions multiples.

>[!CAUTION]
>
>Avec **Cloud Services gérés par Campaign**, votre environnement et votre configuration initiale ont été définis par Adobe, conformément aux termes de votre contrat de licence. Vous n’êtes pas autorisé à modifier les packages intégrés, les schémas ou les rapports installés.
>
>Si vous devez utiliser un module complémentaire Campaign ou une fonctionnalité spécifique qui n’a pas été configurée pour vous, vous devez contacter **l’assistance clientèle Adobe**.

## Avant de commencer

Cette section comporte des informations importantes au sujet de la confidentialité et de la sécurité. Celles-ci doivent être passées en revue et prises en compte avant même le démarrage de l’implémentation.

### Confidentialité

Adobe Campaign s’accompagne de processus et de paramètres qui vous permettent d’utiliser l’application conformément aux lois applicables en matière de confidentialité des données et selon les préférences des destinataires. Ce que vous pouvez gérer :

* **Acquisition des données** : Adobe Campaign vous permet de collecter des données, y compris des informations personnelles et sensibles. Il est donc essentiel que vous receviez et gériez le consentement de vos destinataires. En savoir plus dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#data-acquisition)

* **Consentement des utilisateurs et rétention de données** : découvrez comment obtenir le consentement des utilisateurs, configurer des mécanismes d’abonnement avec double opt-in, faciliter l’opt-out et configurer la rétention des données dans la [documentation sur la confidentialité de Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=en#consent).

* **Règlements relatifs à la protection des données et de la confidentialité** : pour plus d’informations sur le règlement général sur la protection des données (RGPD) de l’Union européenne, la loi sur la protection des informations personnelles des consommateurs de Californie (CCPA) et d’autres exigences internationales en matière de protection des données personnelles, consultez la [documentation sur la protection de la confidentialité de Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html), qui décrit également l’impact de ces règlements sur votre organisation.

### Sécurité

Découvrez les consignes et les principes de sécurité avec Adobe Campaign dans la [liste de contrôle de sécurité de Campaign](../config/security.md).

## Définition des paramètres de Campaign

### Ajout d’utilisateurs et octroi des autorisations

Vous pouvez ajouter manuellement des utilisateurs à Campaign et les associer à des groupes, en les alignant avec votre hiérarchie de rôles. Les utilisateurs pourront alors se connecter et accéder aux données et autorisations adéquates.

[!DNL :arrow_upper_right:] Découvrez comment ajouter des utilisateurs à Adobe Campaign dans  [cette section](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html?lang=fr#getting-started).

### Installation de la console client Campaign

La principale interface utilisateur de l’application est un client riche. En d’autres termes, il s’agit d’une application native (Windows) qui communique avec le serveur d’applications Adobe Campaign uniquement via les protocoles Internet standard (SOAP, HTTP, etc.). La console client Adobe Campaign s’accompagne d’une grande convivialité pour la productivité, utilise très peu de bande passante (grâce à l’utilisation d’un cache local) et est conçue pour offrir un déploiement facile. Cette console peut être déployée à partir d’un navigateur Internet et mise à jour automatiquement. En outre, elle ne nécessite aucune configuration réseau spécifique, car elle génère uniquement du trafic HTTP(S).

[!DNL :bulb:] [En savoir plus sur la console client Campaign](connect.md).

## Préparation de votre environnement

Avant de commencer à envoyer des messages et à créer des campagnes marketing, vous devez :

1. Importer des profils et créer des audiences

   Campaign vous aide à ajouter des contacts à la base de données cloud. Vous pouvez charger un fichier, planifier et automatiser plusieurs mises à jour des contacts, collecter des données sur le Web ou saisir des informations de profil directement dans la table des destinataires.

   [!DNL :bulb:] [Découvrez comment importer des profils](import.md).

   Les audiences sont regroupées dans des listes et peuvent être créées par le biais de workflows. Elles peuvent ensuite être ciblées dans des diffusions cross-canal.

   [!DNL :bulb:] [Découvrez comment définir des audiences](audiences.md).

1. Création de modèles

   Les campagnes, diffusions, traitements ou workflows sont tous basés sur un modèle qui stocke les paramètres et fonctionnalités clés. Un modèle natif est fourni pour chaque composant, pour lequel aucune configuration spécifique n’a été définie. Vous devez configurer et adapter les modèles en fonction de vos besoins, puis les rendre disponibles auprès des utilisateurs finaux.

   [!DNL :arrow_upper_right:] [En savoir plus sur les modèles d&#39;email](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=fr)

   [!DNL :arrow_upper_right:] Découvrez comment utiliser des modèles de campagne dans  [cette page](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-templates.html?lang=fr#orchestrating-campaigns)

   [!DNL :arrow_upper_right:] Découvrez comment configurer un modèle de workflow dans  [cette page](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html?lang=fr#workflow-templates)

1. Configuration des règles de typologie

   Tirez parti des règles de typologies de Campaign pour filtrer, contrôler et surveiller l’envoi de diffusions. Par exemple, les règles de fatigue contrôlent la fréquence et la quantité de messages pour éviter la sollicitation excessive de destinataires. Une fois implémentées, les règles de typologie sont référencées dans les diffusions.

   [!DNL :arrow_upper_right:] [En savoir plus sur les typologies et la gestion de la fatigue](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/about-campaign-typologies.html?lang=fr#orchestrating-campaigns)

1. Familiarisez-vous avec le modèle de données natif de Campaign

   Un modèle de données d’usine est fourni avec Adobe Campaign. Afin d’implémenter et de personnaliser votre environnement, vous devez connaître les tables natives du modèle de données d’Adobe Campaign ainsi que la manière dont elles sont liées les unes aux autres.

   [!DNL :bulb:] [En savoir plus sur le modèle de données de Campaign](../dev/datamodel.md).

## Personnalisation de votre instance

Vous pouvez personnaliser de nombreuses zones et fonctionnalités Campaign. La plupart de nos clients personnalisent trois choses :

1. **Tables et schémas**

   Adobe Campaign s’accompagne de schémas courants pour identifier les données tels que : destinataires, logs de diffusion, abonnements, etc.

   [!DNL :bulb:] Reportez-vous à cette section pour en savoir plus sur le [modèle de données natif de Campaign](../dev/datamodel.md).

   [!DNL :bulb:] Vous pouvez étendre les schémas existants ou créer de nouveaux schémas à partir de zéro. En savoir plus sur [cette page](../dev/customize.md).

1. **Tableaux de bord et listes**

   Vous pouvez facilement configurer des listes, ajouter et supprimer des champs ou personnaliser des colonnes.

   [!DNL :bulb:] Découvrez comment gérer les filtres et les listes de Campaign sur [cette page](../dev/customize.md#gs-lists-and-filters).

   Vous pouvez également créer des tableaux de bord pour afficher les données de Campaign en fonction de vos besoins.

   [!DNL :bulb:] En savoir plus sur [cette page](../dev/customize.md#gs-custom-dashboards).

1. **Rapports**

   Campaign fournit un ensemble de rapports natifs relatifs à la surveillance des diffusions, aux URL et flux de clics, au tracking, aux indicateurs de délivrabilité, etc.

   En complément des rapports natifs, Adobe Campaign permet de générer des rapports dans différents contextes et de répondre à des besoins variés. Ce document détaille les principes d’utilisation ainsi que les modes d’implémentation.

   [!DNL :bulb:] En savoir plus sur les fonctionnalités de reporting de Campaign sur [cette page](reporting.md).


## Configuration de l’automatisation des campagnes

Pour orchestrer des campagnes marketing complexes vers différentes audiences sur plusieurs canaux, tirez parti des fonctionnalités d’automatisation de Campaign.

* Workflows : gestion des processus et des données

* Abonnements et landing pages

* Règles de typologie : gestion du contrôle et de la fatigue

## Extension de votre déploiement

### Implémentation de solutions multiples

Si vous utilisez d’autres solutions Adobe, vous pouvez les connecter à votre environnement Campaign et ainsi combiner les fonctionnalités.

* Campaign - Journey Orchestration
* Campaign - Real-time CDP
* Campaign - Triggers Experience Cloud
* Campaign - Experience Manager
* Campaign - Target
* Campaign - Audience Manager/People core service
* Campaign - Asset
* Campaign - Connecteurs de données Analytics


Vous pouvez également utiliser l’authentification unique (SSO) pour vous connecter à Campaign. En savoir plus sur [cette page](connect.md).

[!DNL :bulb:] Découvrez la liste complète des solutions Adobe qui peuvent être intégrées à Adobe Campaign [sur cette page](../connect/integration.md).

### Connecteurs

Connectez Campaign à des systèmes tiers afin de combiner un large éventail de fonctionnalités et d’automatiser les processus.

[!DNL :bulb:] En savoir plus sur les connecteurs disponibles dans [cette section](../connect/integration.md).

**Connexion de votre CRM à Campaign**

Vous pouvez connecter votre plateforme Adobe Campaign à vos systèmes CRM tiers et synchroniser les données : contacts, comptes, achats, etc.

[!DNL :bulb:] Découvrez comment connecter votre système CRM à Campaign dans  [cette section](../connect/integration.md#gs-crm-connectors)

**Connexion à une base de données externe**

Vous pouvez connecter la base de données cloud de Campaign à des systèmes externes via le module Federated Data Access (FDA).

[!DNL :bulb:] Découvrez comment configurer le module Campaign FDA pour définir les paramètres d&#39;accès dans  [cette section](../connect/integration.md#gs-fda)
