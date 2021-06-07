---
product: Adobe Campaign
title: Campaign Classic v7 - Matrice des fonctionnalités Campaign v8
description: Comprendre les différences entre Campaign Classic v7 et Campaign v8
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62,7105477f-d29e-4af8-8789-82b4459761b0
source-git-commit: 93b690d815f73d11de7de90b92ae188082a3e9e4
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 44%

---

# [!DNL Campaign Classic] v7 - Fonctionnalités  [!DNL Campaign] v8{#gs-matrix}

En tant qu’utilisateur [!DNL Campaign Classic] v7 existant, vous ne devriez pas vous attendre à de fortes perturbations dans la manière dont vous interagissez habituellement avec [!DNL Adobe Campaign]. La plupart des modifications apportées à v8 ne sont pas visibles, à l’exception des petites modifications qui apparaissent dans l’interface utilisateur et dans les étapes de configuration.

Modifications clés :

* Création de segments jusqu’à 200 fois plus rapide
* Augmentation de la vitesse de diffusion
* Reporting en temps réel avec des cubes

En tant qu’utilisateur de [!DNL Campaign Classic], notez que la plupart des fonctionnalités de [!DNL Campaign Classic] v7 sont disponibles avec [!DNL Campaign] v8, à l’exception d’un petit ensemble, répertorié dans [cette section](#gs-removed). Les prochaines versions proposeront d’autres fonctionnalités. [En savoir plus dans cette section](#gs-unavailable-features)

[!DNL :bulb:] Pour en savoir plus sur l’architecture  [!DNL Campaign] v8, consultez  [cette page](../dev/architecture.md).

## Modifications de la configuration des produits

### [!DNL Campaign] et [!DNL Snowflake] {#ac-gs-snowflake}

[!DNL Adobe Campaign] v8 fonctionne avec deux bases de données : une base de données locale pour la messagerie en temps réel et les requêtes unitaires de l’interface utilisateur, et une base de données Cloud pour l’exécution de campagnes, les requêtes par lots et l’exécution de workflows.

Il s’agit d’une modification fondamentale de l’architecture logicielle. Les données sont désormais distantes et Campaign fédère l’intégralité d’entre elles, y compris les profils. [!DNL Campaign]Les processus évoluent désormais de bout en bout, du ciblage à l’exécution des messages : l’ingestion des données, la segmentation, le ciblage, les requêtes et les diffusions s’exécutent désormais en quelques minutes. Cette nouvelle version résout le défi de la mise à l’échelle tout en conservant le même niveau de flexibilité et d’extensibilité. Le nombre de profils est presque illimité et la rétention des données peut être étendue.

Le stockage dans le cloud est effectué dans **[!DNL Snowflake]** : un nouveau **compte externe** intégré garantit la connectivité avec la base de données cloud. Il est configuré par Adobe et ne doit pas être modifié. [En savoir plus](../config/external-accounts.md)

Tout schéma prédéfini ou toute table intégrée devant être déplacé ou répliqué dans la base de données du cloud est fourni avec une extension de schéma intégrée sous l’espace de noms **xxl.** Ces extensions contiennent toute modification requise pour déplacer les schémas intégrés de la base de données locale [!DNL Campaign] vers la base de données [!DNL Snowflake] cloud et pour adapter leur structure en conséquence : nouvel UUID, liens mis à jour, etc.

>[!CAUTION]
>
> Les données client ne sont pas stockées dans la base de données [!DNL Campaign] locale. Par conséquent, toute table personnalisée doit être créée dans la base de données cloud.


Des API spécifiques sont disponibles pour gérer les données entre la base locale et la base de données cloud. Découvrez le fonctionnement de ces nouvelles API et comment les utiliser dans [cette page](../dev/new-apis.md).

### Réplication des données

Un workflow technique spécifique gère la réplication des tables qui doivent être présentes des deux côtés (base de données locale de Campaign et base de données dans le cloud). Ce workflow est déclenché toutes les heures et repose sur une nouvelle bibliothèque JavaScript intégrée.

>[!NOTE]
>
> Plusieurs stratégies de réplication ont été créées en fonction de la taille de la table (XS, XL, etc.).
> Certaines tables sont répliquées en temps réel tandis que d’autres le sont toutes les heures. Certaines tables disposeront de mises à jour incrémentielles tandis que d’autres bénéficieront d’une mise à jour complète.


[En savoir plus sur la réplication des données](../config/replication.md)

### Gestion des identifiants

Les objets Campaign v8 utilisent désormais un **Identifiant universel unique (UUID)**, ce qui permet d’identifier des données à l’aide de valeurs uniques illimitées..

Notez que cet identifiant est basé sur des chaînes et non séquentiel. La clé Principale n’est pas une valeur numérique dans Campaign v8 et vous devez utiliser les attributs **autouuid** et **autopk** dans vos schémas.

Dans Campaign Classic v7 et les versions antérieures, l&#39;unicité d&#39;une clé dans un schéma (c&#39;est-à-dire un tableau) est gérée au niveau du moteur de base de données. Plus généralement, les moteurs de base de données classiques tels que PostgreSQL, Oracle ou SQL Server incluent un mécanisme natif pour empêcher l’insertion de lignes dupliquées à partir d’une colonne ou d’un ensemble de colonnes via des clés Principales et/ou des index uniques. Les ID en double n’existent pas dans ces versions lorsque l’index correct et les clés Principales sont définis au niveau de la base de données.

Adobe campaign v8 est fourni avec Snowflake comme base de données. Comme cela augmente considérablement l’échelle des requêtes, l’architecture répartie de la base de données du Snowflake ne fournit pas de tels mécanismes de gestion et d’application de l’unicité d’une clé dans une table. Par conséquent, avec Adobe Campaign v8, rien n’empêche l’ingestion de clés dupliquées dans un tableau. Les utilisateurs finaux sont désormais chargés d’assurer la cohérence des clés au sein de la base de données Adobe Campaign. [En savoir plus](../dev/keys.md)

### Maintenance simplifiée

Les utilisateurs de Campaign n’ont pas besoin d’être experts en bases de données. Il n’est en effet plus nécessaire d’effectuer des opérations complexes de maintenance des bases de données ou des indexations complexes de tables.

## Reporting

Notez que les rapports Adobe Campaign sont optimisés et offrent de meilleures fonctionnalités d’échelle que Campaign Classic v7. Les limitations existantes sur les cubes ne s&#39;appliquent pas.

## Fonctionnalités non disponibles{#gs-unavailable-features}

Notez que certaines fonctionnalités ne sont pas disponibles dans cette première version, telles que :

* Marketing Resource Management (Gestion des ressources marketing)
* Marketing distribué
* Gestion des offres entrantes (module Interaction)
* Optimisation des campagnes
* Gestion de la réaction
* Modèles de déploiement hybrides/On-premise
* Messagerie LINE
* Panneau de contrôle Campaign

>[!CAUTION]
>
>Pour l’instant, Campaign v8 est **uniquement** disponible en tant que Cloud Service géré et ne peut pas être déployé dans des environnements on-premise ou hybrides.
>
>La migration depuis un environnement Campaign Classic v7 existant n&#39;est pas encore disponible.
>
>Si vous n’êtes pas sûr de votre modèle de déploiement ou si vous avez des questions, contactez votre équipe de compte.

## Fonctionnalités supprimées{#gs-removed}

Pour s’aligner sur la nouvelle architecture et le nouveau modèle de déploiement de Campaign v8, certaines fonctionnalités historiques de Campaign Classic v7 ne sont plus disponibles dans Campaign v8.

* Coupons
* Tracking web
* Questionnaires
* Marketing pour réseaux sociaux
* Connecteur ACS (offre principale)

