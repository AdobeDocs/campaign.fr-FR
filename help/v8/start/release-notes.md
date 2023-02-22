---
title: Notes de mise à jour de Campaign v8
description: Dernière version de Campaign v8
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: e7f4982a9b13fe5413b6cce0a1cc58e2b3a6afa4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Dernière version{#latest-release}

Cette page répertorie les nouvelles fonctionnalités, les améliorations et les correctifs de la **dernière version de Campaign Classic v8**.

## Version 8.4.3 {#release-8-4-3}

>[!CAUTION]
>
> La mise à niveau de la console cliente est obligatoire. Découvrez comment mettre à niveau votre console cliente sur cette [page](../start/connect.md#download-ac-console).

_27 janvier 2023_

**Améliorations**

* Correction d’un problème de synchronisation des indicateurs de diffusion entre le serveur marketing et le serveur de midsourcing. (NEO-50724) <!--OKKKK-->
* Correction d’un problème qui entraînait une erreur lors de l’exportation d’un workflow. (NEO-50555) <!--OKKKK-->
* Correction d’un problème lors de l’extension d’un schéma précédemment étendu. (NEO-49118) <!--OKKKK-->
* Correction d’un problème lors de l’utilisation de deux activités d’enrichissement avec le même identifiant dans la définition du lien. (NEO-48851)
* Correction de deux problèmes qui entraînaient l’échec de la préparation de diffusion. La préparation de la diffusion pouvait échouer lorsque le nombre d’offres potentielles manipulées était trop élevé. Le deuxième problème survenait lorsque les URL des images étaient définies comme URL à suivre dans une diffusion au format texte. (NEO-48807) <!--OKKKK-->
* Correction d’un problème qui entraînait l’échec d’un workflow lorsqu’il remplaçait le nom de l’entrepôt de données défini dans le compte externe pour les comptes non FFDA. (NEO-43209) <!--OKKKK-->
* Amélioration de la sécurité des applications web pour empêcher les attaques DDoS. (NEO-50757) <!--OKKKK-->
* La gestion des données de tracking consolidées a été améliorée dans la table FFDA (nms:trackingStats) **[!UICONTROL Tracking consolidé]** afin d’éviter les doublons. (NEO-46409)
* Correction d’un problème d’opérateur logique dans les requêtes de workflow lors de l’utilisation d’une propriété `enableIf` dans une condition d’opérateur logique. La condition logique précédente a été remplacée. (NEO-45815)  <!--OKKKK-->
* La génération des profils actifs a été optimisée dans le workflow de facturation afin d’améliorer les performances. (NEO-47658) <!--OKKKK-->
* Correction d’un problème lié à l’importation de fichiers HTML lorsque les nœuds d’image (img) contenaient des URL avec des champs de personnalisation. (NEO-48396)
* Correction d’un problème avec Snowflake (tous les déploiements) lors de l’utilisation du paramètre de tri dans une activité de workflow **Partage**. (NEO-45899) <!--OKKKK-->
* Correction d’un problème qui entraînait une erreur lorsqu’un utilisateur ou une utilisatrice disposant de droits d’accès en lecture sur le dossier nmsDeliveryMapping essayait de lancer une campagne ou un workflow. (NEO-48230)
* Correction d’un problème de performances dans l’onglet HTML d’une diffusion, qui pouvait se produire lors de l’utilisation d’un code HTML volumineux. (NEO-47440)
<!-- * Fixed an issue which could lead to a "Character set mismatch" error when using certain functions such as `to_nclob` with an Oracle unicode database where NChar was not enabled. (NEO-49361)
* Fixed an issue which prevented users from inserting a Time datatype in a **Data Update** workflow activity on MSSQL. (NEO-47763)-->
* Correction d’un problème qui empêchait l’utilisation de l’option de workflow **Fusionner les lignes sélectionnées**. (NEO-48488)
* Correction d’un problème sur le connecteur Snowflake FDA en raison duquel les enregistrements étaient supprimés lors de l’utilisation de « Jointure simple de cardinalité 0 ou 1 » pendant l’enrichissement. (NEO-48737)
* Les autres références à la bibliothèque log4j ont été supprimées dans l’installation de Campaign sous Windows. (NEO-44851)
* Correction d’un problème qui pouvait entraîner une erreur lors de l’ajout de l’indicateur **Destinataires ayant ouvert** (estimatedRecipientOpen) dans les données additionnelles d’une activité de workflow **Requête**. (NEO-46665)
* La gestion des URL de tracking a été améliorée dans les workflows comportant plusieurs diffusions afin d’améliorer les performances. (NEO-50894) <!--OKKKK-->
* Correction d’un problème qui entraînait l’échec de la réplication des schémas utilisant Xtkfolder. (NEO-46787) <!--OKKKK-->
* Correction d’un problème en raison duquel la colonne personnalisée « lastModified » était déposée dans la table NmsSubscription. (NEO-48402)
