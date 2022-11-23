---
title: Prise en main des autorisations dans Campaign v8
description: Découvrez les étapes de définition des autorisations dans Campaign v8
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: b63dc1616bc7ce1387a7bd0590c289b59f11b33f
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 11%

---

# Prise en main des autorisations{#gs-permissions}

Adobe Campaign vous permet de définir et gérer les droits attribués aux utilisateurs. Il s’agit d’un ensemble de droits et de restrictions qui autorisent ou refusent :

* Accès à certaines fonctionnalités
* Accès à certaines données
* Accès à certaines actions (création, modification, suppression)

Ces permissions sont définies en combinant les permissions des groupes d&#39;opérateurs, les droits nommés et les permissions sur les dossiers.

Dans Adobe Campaign, les utilisateurs sont des **opérateurs** et les **groupes d’opérateurs** représentent des rôles d’utilisateur. Un opérateur est un utilisateur Adobe Campaign qui possède des autorisations pour se connecter et effectuer des actions. Les utilisateurs sont créés dans le Admin Console. Les autorisations s’appliquent aux profils utilisateur ou aux groupes d’utilisateurs. Vous pouvez accorder deux types d’autorisations :

* Vous pouvez définir des groupes d&#39;opérateurs auxquels vous attribuez des droits, puis associer les opérateurs à un ou plusieurs groupes. Vous pouvez ainsi réutiliser des droits et rendre les profils d’opérateurs plus cohérents. Il facilite également la gestion et la maintenance des profils utilisateur.
* Vous pouvez attribuer des droits nommés directement aux utilisateurs, dans certains cas pour surcharger les droits attribués via les groupes.

## Étapes clés d’octroi des autorisations{#key-steps-permissions}

En tant qu’administrateur de produit, vous pouvez accorder des autorisations aux utilisateurs de votre entreprise. Les autorisations sont accordées via la console cliente Adobe Admin Console et Campaign. Les utilisateurs se connectent à Adobe Campaign avec leur Adobe ID. Découvrez comment vous connecter à Adobe Campaign dans [cette page](connect.md).

Les étapes clés sont les suivantes :

* **Étape 1**: Définissez les groupes d&#39;opérateurs et attribuez-leur des permissions dans la console cliente Campaign. [En savoir plus](manage-permissions.md#create-product-profile).
Vous pouvez également utiliser des groupes d’opérateurs intégrés pour commencer. Ces groupes par défaut et leurs autorisations sont répertoriés dans la section [cette section](manage-permissions.md#ootb-productprofiles).
* **Étape 2**: Créez des profils de produit dans le Admin Console qui correspondent à ces groupes. [En savoir plus](manage-permissions.md#create-product-profile).
Vous pouvez utiliser des profils de produit intégrés pour commencer. [En savoir plus](manage-permissions.md#ootb-productprofiles).
* **Étape 3**: Créez des utilisateurs dans le Admin Console et affectez-les à un profil de produit. [En savoir plus](manage-permissions.md#add-users).
* **Étape 4** (facultatif) : Attribuez des autorisations aux dossiers. [En savoir plus](manage-permissions.md#ootb-productprofiles).

## À propos du Admin Console{#gs-admin-console}

Adobe Admin Console est un emplacement central pour la gestion des droits d’Adobe dans l’ensemble de votre organisation. Il est accessible uniquement aux administrateurs de produit.

Utilisez le Admin Console pour ajouter des utilisateurs, créer et attribuer des profils de produit (qui sont des groupes de rôles d’opérateurs).

Découvrez comment ajouter des utilisateurs dans [cette page](manage-permissions.md#add-users).

## A propos des profils de produit{#ootb-product-profiles}

Les profils de produit sont des groupes de produits et de services que vous pouvez affecter aux utilisateurs. Dans Adobe Experience Cloud, les autorisations dépendent du profil d’un produit et non de l’utilisateur. Vous pouvez toutefois déléguer des droits d’administration à des utilisateurs spécifiques.

Dans le Admin Console, chaque Adobe Experience Cloud **profil de produits** pour Campaign, est associé à une **groupe d&#39;opérateurs** dans la console cliente Campaign.

Découvrez comment créer et affecter des profils de produit dans [cette page](manage-permissions.md#create-a-product-profile).

## Droits nommés de la campagne{#named-rights}

En tant que membre d’un profil de produit (c’est-à-dire d’un groupe d’opérateurs), un utilisateur a les droits d’effectuer des opérations, appelées &quot;Droits nommés&quot;, et dispose d’un accès en lecture et/ou écriture aux données. Un opérateur peut être membre de plusieurs groupes d&#39;opérateurs. Les droits et les autorisations d&#39;accès se cumulent alors.

En savoir plus sur les droits nommés dans [cette section](manage-permissions.md#use-named-rights).
