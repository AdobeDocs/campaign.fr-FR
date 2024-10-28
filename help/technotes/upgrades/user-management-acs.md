---
title: Migration des utilisateurs et utilisatrices techniques vers Adobe Developer Console
description: Découvrez comment migrer la gestion des accès des utilisateurs de Campaign Standard vers Campaign V8
feature: Technote
role: Admin
source-git-commit: ccd60b7ff54bb538ae21693eff41a3943f1c6c88
workflow-type: tm+mt
source-wordcount: '841'
ht-degree: 4%

---

# Gestion des accès des utilisateurs de Campaign Standard vers Campaign V8 {#user-management-acs}

Adobe Campaign Standard et Adobe Campaign V8 permettent aux utilisateurs de définir et gérer des autorisations pour différents utilisateurs/opérateurs. Ces autorisations se composent de droits spécifiques qui accordent aux utilisateurs l’accès à diverses fonctionnalités du produit. Toutefois, les deux produits utilisent des approches et des implémentations distinctes pour gérer l’accès des utilisateurs.

Les concepts suivants sont utilisés dans Adobe Campaign Standard et Campaign V8 pour réaliser la gestion des accès des utilisateurs :

| Campaign Standard | Campaign V8 |
|---------|----------|
| Utilisateur | Opérateur |
| Rôle | Named Right |
| Groupe de sécurité | Groupe d’opérateurs |
| Organizational unit | Autorisation de dossier |

## Approche de migration du groupe Sécurité vers le groupe Opérateur

>[!CAUTION]
>
>Les fonctionnalités de ces rôles/droits nommés peuvent varier dans l’implémentation, ce qui peut entraîner des problèmes d’autorisation (par exemple, l’élévation de privilèges ou des perturbations des fonctionnalités). Nous recommandons aux utilisateurs de passer en revue ces mappages après la transition afin d’assurer un contrôle d’accès correct. [En savoir plus sur les autorisations](../../v8/start/manage-permissions.md)

Le tableau ci-dessous décrit l’approche de migration pour les groupes de rôles utilisateur lors de la transition de Adobe Campaign Standard vers Campaign V8. En Campaign Standard, un **groupe de sécurité**, appelé **groupe d’opérateurs** dans Campaign V8, est utilisé pour affecter un ensemble de rôles à un utilisateur. Bien que certains groupes de sécurité/groupes d’opérateurs soient disponibles d’usine, les utilisateurs peuvent créer de nouveaux groupes ou en modifier d’existants, si nécessaire.

| | **Campaign Standard** | **Campaign V8** |
|---------|----------|---------|
| **Terminologie**  | Groupe de sécurité | Groupe d’opérateurs |

Dans Adobe Campaign Standard et Campaign V8, les **groupes de sécurité** et les **groupes d’opérateurs** sont mappés aux profils de produit dans Admin Console. Si vous souhaitez affecter un **groupe de sécurité** ou un **groupe d’opérateurs** à un utilisateur, vous pouvez lier le **profil de produit** correspondant dans la console d’administration. Cette association est synchronisée lorsque l’utilisateur se connecte. [En savoir plus sur le profil de produit](../../v8/start/manage-permissions.md)

| **Groupe de sécurité Campaign Standard** | **Groupe d’opérateurs Campaign V8** |
|----------|---------|
| Administrateurs | Administrateurs |
| Superviseurs de diffusion | Administrateurs |
| Superviseurs de workflow | Superviseurs de workflow  |

## Approche de migration des rôles utilisateur aux droits nommés

Dans Adobe Campaign Standard, le terme **Rôle utilisateur** est appelé **Droit nommé** dans Campaign V8. Le tableau ci-dessous décrit la terminologie utilisée pour les **droits nommés** dans Campaign V8 correspondant aux **rôles utilisateur** en Campaign Standard.

| **Rôle utilisateur Campaign Standard** | **Campaign V8 Named right** | **Description**  |
|----------|---------|---------|
| Administration  | Administration  | L&#39;utilisateur disposant du droit Administration dispose d&#39;un accès complet à l&#39;instance. |
| Modèle de données  | Administration | Droit pour l&#39;exécution des publications et la création de ressources personnalisées. Fonctionnalité liée à la création de schémas disponible pour l’administrateur dans Campaign V8.  |
| Délivrabilité  | Administration  | Droit pour la validation des diffusions préalablement analysées.  |
| Exporter | Exporter | Droit pour l&#39;export des données.  |
| Accès au fichier  | Accès aux fichiers  | Droit pour la validation des diffusions préalablement analysées.  |
| Import générique  | Importer  | Droit pour l&#39;import générique de données |
| Préparer les diffusions | Préparer les diffusions | Droit pour créer, modifier, préparer et supprimer des diffusions.  |
| Exécution de script SQL | Exécution de script SQL | Droit pour exécuter toute commande SQL directement sur la base de données. |
| Démarrer des diffusions  | Démarrer des diffusions  | Droit pour la validation des diffusions préalablement analysées.  |
| Exécution de la commande système | Exécution du programme | Droit pour exécuter les commandes système sur le serveur. |
| Workflow | Workflow | Droit pour gérer l&#39;exécution des workflows démarrer, arrêter, mettre en pause, etc. |

## Approche de migration à partir de l’entité organisationnelle

Dans Adobe Campaign Standard, l’ **entité organisationnelle** t est mappé au modèle de hiérarchie **Folder** existant dans Campaign V8 pour maintenir un contrôle d’accès similaire. [En savoir plus sur la gestion des dossiers](../../v8/start/folder-permissions.md)

| | **Campaign Standard** | **Campaign V8** |
|---------|----------|---------|
| **Terminologie**  | Organizational unit | Dossier |

## Approche de migration à partir du programme

Dans Campaign V8, **Programmes** sont représentés sous la forme **Dossiers**. Campaign V8 permet la création de dossiers et leur limitation d&#39;accès.

En utilisant les **Groupes** et les **droits nommés**, les **opérateurs** peuvent avoir accès à des **dossiers** spécifiques dans la hiérarchie de navigation, avec la possibilité d&#39;attribuer des autorisations de lecture, d&#39;écriture et de suppression. [En savoir plus sur la gestion des dossiers](../../v8/start/folder-permissions.md)

Comme un **Programme** est traité comme un **Dossier** dans Campaign V8, son accès peut être géré de la même manière que tout autre dossier. Après la migration, les administrateurs de Campaign Standard peuvent suivre les étapes suivantes :

1. Dans l’explorateur, cliquez avec le bouton droit de la souris sur un dossier et sélectionnez **[!UICONTROL Propriétés...]**.
1. Accédez à l’onglet **[!UICONTROL Sécurité]** .
1. Modifiez les autorisations du groupe d’opérateurs en fonction du modèle d’accès souhaité. 

## Mappage du profil de produit pour accéder aux API REST 

Pour accéder aux API transactionnelles à partir de l’instance d’exécution dans Campaign V8, un nouveau **profil de produit** est requis, en plus des profils de produit **Administrator** et **Message Center**. Ce nouveau **profil de produit** sera ajouté aux comptes techniques existants ou précréés dans Campaign Standard.

Après la migration, les utilisateurs Campaign Standards doivent passer en revue leurs **mappings de profil de produit** et attribuer le **profil de produit** approprié s’ils ne souhaitent pas lier leurs **comptes techniques** au **profil de produit** de l’administrateur. Pour les intégrations futures, nous vous recommandons d’utiliser l’**ID de tenant** de Campaign V8 dans l’ **URL REST** au lieu de l’ **ID de tenant** du Campaign Standard précédent.

## Migration de l&#39;accès aux ressources Campaign natives pour les opérateurs Campaign Standards

Les opérateurs migrés depuis Campaign Standard auront accès en lecture à des ressources intégrées spécifiques dans Campaign V8.

## Groupes de sécurité et rôles non migrés {#non-migrated-groups-roles}

Vous trouverez ci-dessous une liste des rôles de Campaign Standard qui n’ont pas été transférés :

* Compte de relais par défaut 

* Message Center Push 

Vous trouverez ci-dessous une liste des mappages de groupes de sécurité Campaign Standards qui n’ont pas été transférés.

* Agents Message Center

* Agents push Message Center

* Chargés d&#39;application Adobe Experience Manager

* Compte de relais
 


 

 


