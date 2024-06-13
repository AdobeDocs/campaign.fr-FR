---
title: Prise en main des autorisations dans Campaign v8
description: Découvrez les étapes de définition des autorisations dans Campaign v8.
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: 09db0cc1a14bffefe8d1b8d0d5a06d5b6517a5bb
workflow-type: ht
source-wordcount: '515'
ht-degree: 100%

---

# Prise en main des autorisations{#gs-permissions}

Adobe Campaign vous permet de définir et gérer les droits attribués aux utilisateurs. Ces ensembles de droits et de restrictions permettent d’autoriser ou de refuser :

* l’accès à certaines fonctionnalités
* l’accès à certaines données
* l’accès à certaines actions (création, modification ou suppression)

Ces autorisations sont définies en combinant les autorisations des groupes d’opérateurs, les droits nommés et les autorisations sur les dossiers.

Dans Adobe Campaign, les utilisateurs sont des **opérateurs** et les **groupes d’opérateurs** représentent des rôles d’utilisateur. Un opérateur/une opératrice est un utilisateur/une utilisatrice Adobe Campaign qui possède des autorisations pour se connecter et effectuer des actions. La création des utilisateurs s’effectue dans Admin Console. Les autorisations s’appliquent aux profils utilisateur ou aux groupes d’utilisateurs. Vous pouvez accorder deux types d’autorisations :

* Vous pouvez définir des groupes d&#39;opérateurs auxquels vous attribuez des droits, puis associer les opérateurs à un ou plusieurs groupes. Ce mode de fonctionnement permet de mutualiser les autorisations et d’uniformiser les profils des opérateurs. Il permet également de faciliter la gestion et la maintenance des profils utilisateur.
* Vous pouvez attribuer directement des droits nommés aux utilisateurs, éventuellement pour surcharger les droits attribués via les groupes.

## Étapes clés de l’octroi des autorisations{#key-steps-permissions}

En tant qu’administrateur/administratrice de produit, vous pouvez accorder des autorisations aux utilisateurs de votre organisation. Les autorisations sont accordées par le biais d’Adobe Admin Console et de la console cliente Campaign. Les utilisateurs peuvent se connecter à Adobe Campaign au moyen de leur Adobe ID. Découvrez comment vous connecter à Adobe Campaign sur [cette page](connect.md).

Les étapes clés sont les suivantes :

* **Étape 1** : définissez les groupes d’opérateurs et attribuez-leur des autorisations dans la console cliente Campaign. [En savoir plus](manage-permissions.md#create-product-profile).
Vous pouvez également utiliser les groupes d’opérateurs intégrés pour commencer. Ces groupes par défaut et leurs autorisations sont répertoriés dans [cette section](manage-permissions.md#ootb-productprofiles).
* **Étape 2** : créez des profils de produit correspondant à ces groupes dans Adobe Admin Console. [En savoir plus](manage-permissions.md#create-product-profile).
Vous pouvez utiliser les profils de produit intégrés pour commencer. [En savoir plus](manage-permissions.md#ootb-productprofiles).
* **Étape 3** : créez des utilisateurs et utilisatrices dans Adobe Admin Console et affectez-les à un profil de produit. [En savoir plus](manage-permissions.md#add-users).
* **Étape 4** (facultatif) : attribuez des autorisations sur les dossiers. [En savoir plus](manage-permissions.md#ootb-productprofiles).

## À propos d’Admin Console{#gs-admin-console}

Adobe Admin Console permet de gérer les droits Adobe pour l’ensemble de votre organisation dans un seul endroit. Son accès est limité aux administrateurs de produit.

Admin Console permet d’ajouter des utilisateurs, ainsi que de créer et d’attribuer des profils de produit (qui sont des groupes de rôles opérateurs).

Découvrez comment ajouter des utilisateurs sur [cette page](manage-permissions.md#add-users).

## À propos des profils de produit{#ootb-product-profiles}

Les profils de produit sont des groupes de produits et de services que vous pouvez affecter aux utilisateurs. Dans Adobe Experience Cloud, les autorisations portent sur le profil d’un produit et non sur l’utilisateur/utilisatrice. Toutefois, vous pouvez déléguer des droits d’administration à des utilisateurs spécifiques.

Dans Admin Console, chaque **profil de produit** Adobe Experience Cloud pour Campaign est associé à un **groupe d’opérateurs** dans la console cliente Campaign.

Découvrez comment créer et affecter des profils de produit sur [cette page](manage-permissions.md#create-a-product-profile).

## Droits nommés dans Campaign{#named-rights}

En tant que membre d’un profil de produit (c’est-à-dire un groupe d’opérateurs), un utilisateur/une utilisatrice dispose de droits lui permettant d’effectuer des opérations, appelés « Droit nommés » ainsi que d’un accès en lecture et/ou écriture aux données. Un opérateur /une opératrice peut être membre de plusieurs groupes d’opérateurs. Les droits et les autorisations d’accès se cumulent alors.

En savoir plus sur les droits nommés dans [cette section](manage-permissions.md#use-named-rights).
