---
title: Notes de mise à jour de Campaign v8
description: Dernière version de Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: e5e08dcd1813c8eba608ba3a7b659dcd6d98d985
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 22%

---

# Dernières versions {#latest-release}

Cette page répertorie les nouvelles fonctionnalités, les améliorations et les correctifs des **dernières versions** de Campaign v8 (console). Pour en savoir plus sur les publications, les versions et les mises à niveau de Campaign, consultez [cette page](upgrades.md). Les autres versions sont répertoriées dans la section Versions précédentes de cette documentation.

## Version 8.9.1 {#release-8-9-1}

_27 janvier 2026_

>[!CAUTION]
>
> La mise à niveau de la console cliente est obligatoire. Découvrez comment mettre à niveau votre console cliente sur cette [page](../start/connect.md#upgrade-ac-console).

### Nouvelles fonctionnalités {#new-8-9-1}

Le **nouveau connecteur d&#39;envoi de SMS** est désormais disponible pour tous les clients (GA). Consultez la [documentation détaillée](../send/sms/sms.md).

Cette version est fournie avec un ensemble de fonctionnalités disponibles dans l’interface utilisateur web de Campaign :

* Fonctionnalités de diffusion multilingue (GA)
* Enrichissement du profil dans les messages transactionnels (GA)
* Live Copies et copies de langue de Adobe Experience Manager
* Expériences de contenu - Tests A/B
* Activité de diffusion au fil de l&#39;eau

Reportez-vous aux notes de mise à jour de l’interface utilisateur web de Campaign [](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=fr){target="_blank"}

### Améliorations de la sécurité {#security-8-9-1}

* Les comptes externes Snowflake prennent désormais en charge l’authentification OAuth2, fournissant des méthodes d’authentification modernes et sécurisées pour les connexions d’accès aux données fédérées. (NEO-87013)
* Correction de vulnérabilités d’accès aux fichiers de workflow en limitant les opérations aux répertoires autorisés, en empêchant l’accès non autorisé et l’exécution potentielle de code à distance. (NEO-88460)
* Placer sur la liste autorisée Ajout de contrôles d’URL FTP aux activités de code de JavaScript de workflow, limitant les connexions FTP sortantes aux adresses autorisées uniquement. (NEO-89083)

### Autres changements {#changes-8-9-1}

* Amélioration de la gestion de la mémoire de conteneur en implémentant la limitation automatique des workflows dans des conditions de mémoire élevée, avec des fonctionnalités intelligentes de redémarrage des workflows et des mécanismes de sécurisation de la mémoire pour les processus non critiques. (NEO-89041)
* Ajout de la prise en charge des fonctions de chiffrement et de déchiffrement asymétriques dans les workflows Campaign. (NEO-80257)
* Amélioration des performances de l’agent de réplication et de la résilience de la mémoire pour les chargements de données volumineux dans les déploiements FFDA. (NEO-88430)


### Correctifs {#fixes-8-9-1}

* Correction d’un problème en raison duquel les rapports dynamiques affichaient des décomptes incorrects lors du regroupement par certaines colonnes. (NEO-86898)
* Correction des incohérences de données entre les rapports dynamiques et les données réelles de la campagne. (NEO-88068)
* Correction de problèmes de concaténation avec les types de champs « char » PostgreSQL qui provoquaient des résultats inattendus dans les requêtes. (NEO-87769)
* Correction d’un problème en raison duquel la commande logInfo de JavaScript ne gérait pas correctement certains paramètres. (NEO-88263)
* Résolution des problèmes de blocage de synchronisation dans le traitement des événements temps réel de Message Center. (NEO-88330)
* Correction d’un problème en raison duquel l’éditeur visuel reformatait automatiquement le contenu d’HTML, provoquant des changements de disposition. (NEO-88409)
* Correction d&#39;un problème en raison duquel l&#39;activité Déduplication ne fonctionnait pas correctement avec les schémas temporaires. (NEO-88577)
* Correction d’un problème qui empêchait la génération des adresses de contrôle lors de l’envoi de BAT. (NEO-88720)
* Amélioration des performances des requêtes PostgreSQL en optimisant la gestion des colonnes de partition. (NEO-88771)
* Correction d’un problème en raison duquel les activités de transfert de fichiers ne géraient pas correctement les caractères de continuation de ligne. (NEO-88812)
* Optimisation améliorée des requêtes PostgreSQL pour de meilleures performances dans les jeux de données volumineux. (NEO-88885)
* Correction d’une erreur « Autorisation refusée » qui empêchait l’ouverture de campagnes hybrides. (NEO-88955)
* Prise en charge étendue des fonctionnalités de code à barres pour gérer les chaînes de texte plus longues. (NEO-88958)
* Correction d’une erreur dans les logs de campagne qui se produisait lors de l’utilisation de BAT avec des diffusions récurrentes. (NEO-88976)
* Correction d’un problème qui affectait les opérations d’envoi d’e-mails dans certains scénarios. (NEO-89019)
* Correction d&#39;un problème en raison duquel le mode de démarrage du workflow passait inopinément de Immédiat à Normal. (NEO-89025)
* Correction d&#39;erreurs qui se produisaient lors de l&#39;exécution de l&#39;activité Mise à jour de données dans des conditions spécifiques. (NEO-89031)
* Correction d’un problème en raison duquel l’activité Mise à jour de données perdait les métadonnées de schéma personnalisées. (NEO-89056)
* Correction d’une erreur de validation qui se produisait lors de la préparation de la diffusion. (NEO-89063)
* Résolution d’une génération SQL non valide lorsque les requêtes contenaient des filtres sur les relations de lien 1-1. (NEO-89065)
* Correction d’un problème en raison duquel l’activité de Requête incrémentale ne respectait pas la limite de taille configurée. (NEO-89066)
* Amélioration des performances des workflows dans les déploiements FFDA pour les opérations à grande échelle. (NEO-89098)
* Gestion de la mémoire améliorée et stabilité des processus de workflow. (NEO-89105)
* Activation de la validation de colonne stricte pour les formulaires web afin d’éviter les incohérences de données. (NEO-89111)
* Résolution des problèmes de synchronisation de Message Center qui entraînaient des retards de traitement. (NEO-89138)
* Correction d’erreurs dans le workflow « Actualiser la délivrabilité » qui empêchaient une exécution correcte. (NEO-89160)
* Correction des erreurs qui se produisaient lors de l’exécution des activités de code JavaScript dans les workflows. (NEO-89169)
* Suppression des configurations d’entrepôt de données Snowflake codées en dur pour permettre les paramètres de compte externe appropriés. (NEO-89201)
* Correction des erreurs 403 Interdit qui se produisaient lors des opérations de transfert de fichiers de workflow. (NEO-89226)
* Optimisation des requêtes lentes sur la table des destinataires dans les déploiements FFDA. (NEO-89268)
* Correction d’un problème en raison duquel les activités de requête incrémentale ignoraient les plannings configurés. (NEO-89317)
* Résolution des erreurs d’accès lors de l’ouverture de campagnes dans des environnements hybrides. (NEO-89320)
