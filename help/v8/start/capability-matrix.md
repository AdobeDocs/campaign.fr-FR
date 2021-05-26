---
solution: Campaign v8
product: Adobe Campaign
title: Matrice des fonctionnalités de Campaign Classic v7 - Campaign v8
description: Comprendre les différences entre Campaign Classic v7 et Campaign v8
feature: Vue d'ensemble
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62,7105477f-d29e-4af8-8789-82b4459761b0
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 4%

---

# [!DNL Campaign Classic] v7 - Fonctionnalités  [!DNL Campaign] v8{#gs-matrix}

En tant qu’utilisateur [!DNL Campaign Classic] v7 existant, vous ne devriez pas vous attendre à de fortes perturbations dans la manière dont vous interagissez habituellement avec [!DNL Adobe Campaign]. La plupart des modifications dans v8 ne sont pas visibles, à l’exception des petites modifications qui apparaissent dans l’interface utilisateur et les étapes de configuration.

Modifications clés :

* Création de segments jusqu’à 200 fois plus rapide
* Augmentation de la vitesse de livraison
* Création de rapports en temps réel avec des cubes

En tant qu’utilisateur de [!DNL Campaign Classic], notez que la plupart des fonctionnalités de [!DNL Campaign Classic] v7 sont disponibles avec [!DNL Campaign] v8, à l’exception d’un petit ensemble, répertorié dans [cette section](#gs-removed). D&#39;autres seront disponibles dans les prochaines versions. [En savoir plus dans cette section](#gs-unavailable-features)

[!DNL :bulb:] Pour en savoir plus sur l’architecture  [!DNL Campaign] v8, consultez  [cette page](../dev/architecture.md).

## Modifications de la configuration du produit

### [!DNL Campaign] et [!DNL Snowflake] {#ac-gs-snowflake}

[!DNL Adobe Campaign] v8 fonctionne avec deux bases de données : une base de données locale pour la messagerie en temps réel et les requêtes unitaires de l’interface utilisateur, et une base de données Cloud pour l’exécution de campagnes, les requêtes par lots et l’exécution de workflows.

C&#39;est un changement fondamental dans l&#39;architecture du logiciel. Les données sont désormais distantes et Campaign fédére l’ensemble des données, y compris les profils. [!DNL Campaign] les processus évoluent désormais de bout en bout, du ciblage à l’exécution des messages : l’ingestion de données, la segmentation, le ciblage, les requêtes, les diffusions s’exécuteront désormais en minutes. Cette nouvelle version résout tout le problème de mise à l’échelle tout en conservant le même niveau de flexibilité et d’extensibilité. Le nombre de profils est pratiquement illimité et la rétention des données peut être étendue.

Le stockage dans le cloud est effectué dans **[!DNL Snowflake]** : un nouveau **compte externe** intégré garantit la connectivité avec la base de données cloud. Il est configuré par Adobe et ne doit pas être modifié. [En savoir plus](../config/external-accounts.md).

Tout schéma/table intégré devant être déplacé ou répliqué dans la base de données cloud est fourni avec une extension de schéma intégrée sous l’espace de noms **xxl**. Ces extensions contiennent toute modification requise pour déplacer les schémas intégrés de la base de données locale [!DNL Campaign] vers la base de données [!DNL Snowflake] cloud et pour adapter leur structure en conséquence : nouvel UUID, liens mis à jour, etc.

>[!CAUTION]
>
> Les données client ne sont pas stockées dans la base de données [!DNL Campaign] locale. Par conséquent, toute table personnalisée doit être créée dans la base de données Cloud.


Des API spécifiques sont disponibles pour gérer les données entre la base locale et la base de données cloud. Découvrez le fonctionnement de ces nouvelles API et comment les utiliser dans [cette page](../dev/new-apis.md).

### Réplication des données

Un workflow technique spécifique gère la réplication des tables qui doivent être présentes des deux côtés (base de données locale Campaign et base de données Cloud). Ce workflow se déclenche toutes les heures et repose sur une nouvelle bibliothèque JavaScript intégrée.

>[!NOTE]
>
> Plusieurs stratégies de réplication ont été créées en fonction de la taille du tableau (XS, XL, etc.).
> Certaines tables sont répliquées en temps réel, d’autres le sont toutes les heures. Certaines tables auront des mises à jour incrémentielles, d’autres suivront une mise à jour complète.


[En savoir plus sur la réplication des données](../config/replication.md)

### Gestion des identifiants

Les objets de Campaign v8 utilisent désormais un **identifiant unique universel (UUID)**, qui permet d’identifier des données à l’aide de valeurs uniques illimitées.

Notez que cet identifiant est basé sur des chaînes et non séquentiel.

### Maintenance simplifiée

Les utilisateurs de Campaign n’ont pas besoin d’être des experts en base de données : il n’est plus nécessaire d’effectuer des opérations de maintenance de base de données complexes ou d’indexer des tables complexes.

## Fonctionnalités non disponibles temporaires{#gs-unavailable-features}

Notez que certaines fonctionnalités ne sont pas encore disponibles dans cette première version, telles que :

* Marketing Resource Management
* Marketing distribué
* Gestion des offres entrantes (module Interaction)
* Optimisation des campagnes
* Gestion de la réaction
* Modèles de déploiement hybride/On-premise

## Fonctionnalités supprimées{#gs-removed}

Pour s&#39;aligner sur la nouvelle architecture et le nouveau modèle de déploiement de Campaign v8, certaines fonctionnalités historiques de Campaign Classic v7 ne sont plus disponibles dans Campaign v8.

* Coupons
* Tracking web
* Questionnaires
* Social Marketing
* ACS Connector (offre Prime)

