---
solution: Campaign Classic
product: campaign
title: Campaign Classic v7 - Matrice des fonctionnalités Campaign v8
description: Comprendre les différences entre Campaign Classic v7 et Campaign v8
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62,7105477f-d29e-4af8-8789-82b4459761b0
translation-type: tm+mt
source-git-commit: 04859274593f507a0b07f46cf6a65434b6a4bc60
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 3%

---

# Campaign Classic v7 - fonctionnalités de Campaign v8{#gs-matrix}


En tant qu’utilisateur Campaign Classic v7, vous devez vous attendre à toute perturbation importante de la façon dont vous jouez habituellement avec Adobe Campaign. La plupart des modifications ne sont pas visibles, à l’exception des petites modifications qui apparaissent dans l’interface utilisateur et les étapes de configuration.

Changements clés :

* Créez des segments jusqu’à 200 fois plus rapides

* Augmentation de la vitesse de diffusion

* Rapports en temps réel

En tant qu’utilisateur Campaign Classic, notez que la plupart des fonctionnalités de Campaign Classic v7 sont disponibles avec Campaign v8, à l’exception d’un petit ensemble de fonctionnalités, répertoriées dans [cette section](#gs-removed). D&#39;autres seront disponibles dans les prochaines versions. [En savoir plus](#gs-unavailable-features)


## Modifications de la configuration du produit

### Campaign et Snowflake {#ac-gs-snowflake}

L’enregistrement Cloud est effectué dans le Snowflake : un nouveau compte externe assure la connectivité avec la base de données Cloud. [En savoir plus](#ac-gs-snowflake).

C&#39;est un changement fondamental dans l&#39;architecture logicielle. Les données sont maintenant distantes : Campaign fédére l&#39;ensemble des données, y compris les Profils. Le processus Campaign évolue désormais de bout en bout, du ciblage à l’exécution de Diffusions : L’assimilation des données, la segmentation, le ciblage, les requêtes et l’exécution des Diffusions s’exécuteront désormais en quelques minutes.

Cette nouvelle version résout tout le défi de l&#39;évolutivité, en maintenant le même niveau de flexibilité et d&#39;extensibilité. Le nombre de profils est presque illimité et la rétention des données peut être étendue.

Un nouveau **compte externe** intégré est dédié à la FDA complète. C&#39;est le coeur de la connectivité de la base de données Cloud. Nous vous recommandons de partir tel quel.

Tout schéma/table intégré qui doit être déplacé ou répliqué dans Cloud Database est fourni avec une extension de schéma intégrée sous espace de nommage **xxl**. En ce qui concerne l&#39;extension de schéma, le nouvel espace de nommage XXL sera utilisé pour toute nouvelle configuration d&#39;OOTB comme JavaScript, JSSP, etc.

Ces extensions contiennent toutes les modifications nécessaires pour déplacer les schémas intégrés de la base de données locale Campaign vers la base de données Snowflake Cloud et pour adapter leur structure en conséquence : nouveau UUID, liens mis à jour, etc.

>[!CAUTION]
>
> Les données client ne sont pas stockées dans la base de données Campaign locale. Par conséquent, toute table personnalisée doit être créée dans la base de données Cloud.


### Réplication des données

Un processus technique spécifique gère la réplication des tables qui doivent être présentes des deux côtés (base de données locale Campaign et base de données Cloud). Ce flux de travaux est déclenché toutes les heures et repose sur une nouvelle bibliothèque JavaScript intégrée.

>[!NOTE]
>
> Plusieurs stratégies de réplication ont été créées en fonction de la taille du tableau (XS, XL, etc.).
> Certains tableaux sont répliqués en temps réel, d’autres sur une base horaire. Certaines tables seront mises à jour progressivement, d’autres seront mises à jour.


[En savoir plus sur la réplication des données](../config/replication.md)

### Gestion des identifiants

Les objets Campaign v8 utilisent désormais **l’identifiant unique (UUID)**, ce qui implique des valeurs uniques illimitées pour identifier les données.

Veuillez noter que cet identifiant est basé sur des chaînes et n’est pas séquentiel.

### Maintenance simplifiée

Les utilisateurs de Campaign n&#39;ont pas besoin d&#39;être experts en bases de données : plus de workflows longs de maintenance de bases de données ou d&#39;indexation de tables complexes.

## Fonctionnalités indisponibles temporaires{#gs-unavailable-features}

Veuillez noter que certaines fonctionnalités ne sont pas disponibles dans cette première version, mais seront bientôt disponibles, par exemple :

* Marketing Resource Management
* Marketing distribué
* Messages d’entrée de Gestion des Offres (module Interaction)
* Optimisation des campagnes
* Gestion de la réaction
* Marketing social avec Twitter
* Modèles de déploiement hybrides/sur site

## Fonctionnalités supprimées{#gs-removed}

Pour s’aligner sur la nouvelle architecture et le nouveau modèle de déploiement de Campaign v8, certaines fonctionnalités Campaign Classic v7 historiques ne sont pas disponibles dans Campaign v8.

* Bons
* Tracking web
* Questionnaires
* Marketing social avec Facebook
* Connecteur ACS (Offre privilégiée)
* Base de données Microsoft SQL
* Oracle de données
