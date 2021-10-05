---
title: Instructions d'implémentation
description: Découvrez comment implémenter Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 09562b6c-3d3d-4808-a70b-202172867f46
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: ht
source-wordcount: '1213'
ht-degree: 100%

---

# Instructions d&#39;implémentation de Campaign

Dans cette section, vous apprendrez comment adapter Adobe Campaign aux exigences de votre société. Suivez les instructions suivantes pour structurer et organiser votre implémentation.

1. **Définition des paramètres** : octroi d&#39;accès, partage de la console cliente, configuration de canaux (e-mail, push, sms).
1. **Préparation de votre environnement** : import de profils, création d&#39;audiences, conception de modèles de workflows et de campagnes, création de règles de typologie.
1. **Personnalisation de votre instance** : création de champs de données, ajout de tables/schémas.
1. **Extension de votre déploiement** : connexion à des solutions Adobe, autres produits et systèmes - connecteurs, paramètres de solutions multiples.

>[!CAUTION]
>
>Avec **Managed Cloud Services de Campaign**, votre environnement et votre configuration initiale ont été définis par Adobe, conformément aux termes de votre contrat de licence. Vous n&#39;êtes pas autorisé à modifier les packages, les schémas ou les rapports natifs installés.
>
>Si vous devez utiliser un module complémentaire Campaign ou une fonctionnalité spécifique qui n&#39;a pas été configurée pour vous, vous devez contacter **l&#39;assistance clientèle Adobe**.

## Avant de commencer

Cette section comporte des informations importantes au sujet de la confidentialité et de la sécurité. Celles-ci doivent être passées en revue et prises en compte avant même le démarrage de l&#39;implémentation.

### Confidentialité

Adobe Campaign s&#39;accompagne de processus et de paramètres qui vous permettent d&#39;utiliser l&#39;application conformément aux lois applicables en matière de confidentialité des données et selon les préférences des destinataires. Ce que vous pouvez gérer :

* **Acquisition des données** : Adobe Campaign vous permet de collecter des données, y compris des informations personnelles et sensibles. Il est donc essentiel que vous receviez et gériez le consentement de vos destinataires. Apprenez-en davantage en consultant la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=fr#data-acquisition).

* **Consentement des utilisateurs et rétention de données** : découvrez comment obtenir le consentement des utilisateurs, configurer des mécanismes d&#39;abonnement avec double opt-in, faciliter l&#39;opt-out et configurer la rétention des données dans la [documentation sur la confidentialité de Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=fr#consent).

* **Règlements relatifs à la protection des informations personnelles et de la confidentialité** : {target=&quot;_blank&quot;} pour plus d&#39;informations sur le règlement général sur la protection des données (RGPD) de l&#39;Union européenne, la loi sur la protection des informations personnelles des consommateurs de Californie (CCPA) et d&#39;autres exigences internationales en matière de protection des données personnelles, consultez la [documentation sur la protection de la confidentialité de Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=fr), qui décrit également l&#39;impact de ces règlements sur votre organisation.

### Sécurité

Découvrez les instructions et principes relatifs à la sécurité d&#39;Adobe Campaign dans la [liste de contrôle de sécurité Campaign](../config/security.md).

## Définition des paramètres de Campaign

### Ajout d&#39;utilisateurs et octroi des autorisations

Vous pouvez ajouter manuellement des utilisateurs à Campaign et les associer à des groupes, en les alignant avec votre hiérarchie de rôles. Les utilisateurs pourront alors se connecter et accéder aux données et autorisations adéquates.

↗️ Découvrez comment ajouter des utilisateurs à Adobe Campaign dans [cette section](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html?lang=fr#getting-started).{target=&quot;_blank&quot;}

### Installation de la console cliente Campaign

La principale interface utilisateur de l&#39;application est un client riche. En d&#39;autres termes, il s&#39;agit d&#39;une application native (Windows) qui communique avec le serveur d&#39;applications Adobe Campaign uniquement via les protocoles Internet standard (SOAP, HTTP, etc.). La console cliente Adobe Campaign est très conviviale, permet d&#39;être productif, utilise très peu de bande passante (grâce à l&#39;utilisation d&#39;un cache local) et est conçue pour offrir un déploiement facile. Cette console peut être déployée à partir d&#39;un navigateur Internet et mise à jour automatiquement. En outre, elle ne nécessite aucune configuration réseau spécifique, car elle génère uniquement du trafic HTTP(S).

?? [En savoir plus sur la console cliente Campaign](connect.md).

## Préparation de votre environnement

Avant de commencer à envoyer des messages et à créer des campagnes marketing, vous devez :

1. Importer des profils et créer des audiences

   Campaign vous aide à ajouter des contacts à la base de données cloud. Vous pouvez charger un fichier, planifier et automatiser plusieurs mises à jour des contacts, collecter des données sur le Web ou saisir des informations de profil directement dans la table des destinataires.

   ?? [Découvrez comment importer des profils](import.md).

   Les audiences sont regroupées dans des listes et peuvent être créées par le biais de workflows. Elles peuvent ensuite être ciblées dans des diffusions cross-canal.

   ?? [Découvrez comment définir des audiences](audiences.md).

1. Création de modèles

   Les campagnes, diffusions, traitements ou workflows sont tous basés sur un modèle qui stocke les paramètres et fonctionnalités clés. Un modèle natif est fourni pour chaque composant, pour lequel aucune configuration spécifique n&#39;a été définie. Vous devez configurer et adapter les modèles en fonction de vos besoins, puis les rendre disponibles auprès des utilisateurs finaux.

   ↗️ [En savoir plus sur les modèles d’email](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=fr){target=&quot;_blank&quot;}

   ↗️ Découvrez comment utiliser les modèles de campagnes dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-templates.html?lang=fr#orchestrating-campaigns).{target=&quot;_blank&quot;}

   ↗️ Découvrez comment configurer un modèle de workflow dans la documentation de [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html?lang=fr#workflow-templates){target=&quot;_blank&quot;}

1. Configuration des règles de typologie

   Tirez parti des règles de typologies de Campaign pour filtrer, contrôler et surveiller l&#39;envoi de diffusions. Par exemple, les règles de fatigue contrôlent la fréquence et la quantité de messages pour éviter la sollicitation excessive de destinataires. Une fois implémentées, les règles de typologie sont référencées dans les diffusions.

   ↗️ En savoir plus sur les typologies et la gestion de la fatigue dans la documentation de [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/about-campaign-typologies.html?lang=fr#orchestrating-campaigns){target=&quot;_blank&quot;}

1. Familiarisez-vous avec le modèle de données natif de Campaign

   Un modèle de données d&#39;usine est fourni avec Adobe Campaign. Afin d&#39;implémenter et de personnaliser votre environnement, vous devez connaître les tables natives du modèle de données d&#39;Adobe Campaign ainsi que la manière dont elles sont liées les unes aux autres.

   ?? [En savoir plus sur le modèle de données de Campaign](../dev/datamodel.md).

## Personnalisation de votre instance

Vous pouvez personnaliser de nombreuses zones et fonctionnalités Campaign. La plupart de nos clients personnalisent trois choses :

1. **Tables et schémas**

   Adobe Campaign s&#39;accompagne de schémas courants pour identifier les données tels que : destinataires, logs de diffusion, abonnements, etc.

   ?? Reportez-vous à cette section pour en savoir plus sur le [modèle de données natif de Campaign](../dev/datamodel.md).

   ?? Vous pouvez étendre les schémas existants ou en créer d&#39;autres de A à Z. Apprenez-en davantage en consultant [cette page](../dev/customize.md).

1. **Tableaux de bord et listes**

   Vous pouvez facilement configurer des listes, ajouter et supprimer des champs ou personnaliser des colonnes.

   ?? Découvrez comment gérer les filtres et les listes de Campaign sur [cette page](../dev/customize.md#gs-lists-and-filters).

   Vous pouvez également créer des tableaux de bord pour afficher les données de Campaign en fonction de vos besoins.

   ?? Apprenez-en davantage en consultant [cette page](../dev/customize.md#gs-custom-dashboards).

1. **Rapports**

   Campaign fournit un ensemble de rapports natifs relatifs à la surveillance des diffusions, aux URL et flux de clics, au tracking, aux indicateurs de délivrabilité, etc.

   En complément des rapports natifs, Adobe Campaign permet de générer des rapports dans différents contextes et de répondre à des besoins variés. Ce document détaille les principes d&#39;utilisation ainsi que les modes d&#39;implémentation.

   ?? Apprenez-en davantage sur les fonctionnalités de reporting de Campaign en consultant [cette page](reporting.md).


## Configuration de l&#39;automatisation des campagnes

Pour orchestrer des campagnes marketing complexes vers différentes audiences sur plusieurs canaux, tirez parti des fonctionnalités d&#39;automatisation de Campaign.

* Workflows : gestion des processus et des données

* Abonnements et landing pages

* Règles de typologie : gestion du contrôle et de la fatigue

## Extension de votre déploiement

### Implémentation de solutions multiples

Si vous utilisez d&#39;autres solutions Adobe, vous pouvez les connecter à votre environnement Campaign et ainsi combiner les fonctionnalités.

* Campaign - Journey Orchestration
* Campaign - Real-time CDP
* Campaign - Triggers Experience Cloud
* Campaign - Experience Manager
* Campaign - Target
* Campaign - Audience Manager/People core service
* Campaign - Asset
* Campaign - Connecteurs de données Analytics


Vous pouvez également utiliser l&#39;authentification unique (SSO) pour vous connecter à Campaign. Apprenez-en davantage en consultant [cette page](connect.md).

?? Découvrez la liste complète des solutions Adobe qui peuvent être intégrées à Adobe Campaign [sur cette page](../connect/integration.md).

### Connecteurs

Connectez Campaign à des systèmes tiers afin de combiner un large éventail de fonctionnalités et d&#39;automatiser les processus.

?? Apprenez-en davantage sur les connecteurs disponibles en consultant [cette section](../connect/integration.md).

**Connexion de votre CRM à Campaign**

Vous pouvez connecter votre plateforme Adobe Campaign à vos systèmes CRM tiers et synchroniser les données : contacts, comptes, achats, etc.

?? Découvrez comment connecter votre système CRM à Campaign dans [cette section](../connect/integration.md#gs-crm-connectors).

**Connexion à une base de données externe**

Vous pouvez connecter la base de données cloud de Campaign à des systèmes externes via le module Federated Data Access (FDA).

?? Découvrez comment configurer le module FDA de Campaign pour définir les paramètres d&#39;accès dans [cette section](../connect/integration.md#gs-fda).
