---
title: Migrer les opérateurs et opératrices de Campaign vers Adobe Identity Management System (IMS)
description: Découvrez comment migrer les opérateurs et opératrices Campaign vers Adobe Identity Management System (IMS).
hide: true
hidefromtoc: true
source-git-commit: 53412ab167721c8a8f9d84e07112b0f410d4785d
workflow-type: tm+mt
source-wordcount: '1094'
ht-degree: 100%

---

# Migrer les opérateurs et opératrices de Campaign vers Adobe Identity Management System (IMS) {#migrate-users-to-ims}

Campaign v8.6 et les versions ultérieures apportent des améliorations au processus d’authentification de Campaign v8. Tous les opérateurs et opératrices doivent utiliser [Adobe Identity Management System (IMS)](https://helpx.adobe.com/fr/enterprise/using/identity.html){target="_blank"} **uniquement** pour se connecter à Campaign. La connexion avec l’utilisateur/mot de passe (ou authentification native) ne sera plus autorisée. Adobe recommande d’effectuer cette migration dans Campaign v8.5.2 afin de pouvoir migrer en douceur vers Campaign v8.6.

En tant que client ou cliente des services gérés v7 de Campaign Classic, si vous effectuez une migration vers Campaign v8, cette procédure s’applique également à vous.

Cet article décrit les étapes à suivre pour migrer un opérateur ou une opératrice technique vers un compte technique sur Adobe Developer Console.

## Qu’est-ce qui a changé ?{#move-to-ims-changes}

Avec Campaign v8, les utilisateurs et utilisatrices standard pouvaient déjà se connecter à la console cliente Adobe Campaign à l’aide de leur Adobe ID, via le système IMS (Adobe Identity Management System). Toutefois, avec certaines configurations plus anciennes, les connexions utilisateur/mot de passe étaient toujours disponibles. **Cela ne sera plus autorisé à partir de Campaign v8.6.**

En outre, dans le cadre des mesures visant à renforcer la sécurité et le processus d’authentification, l’application cliente Adobe Campaign appelle désormais les API Campaign directement à l’aide du jeton de compte technique IMS. La migration des opérateurs et opératrices techniques est présentée dans un article dédié, disponible sur [cette page](ims-migration.md).

Cette modification s’applique à partir de Campaign v8.5.2 et sera **obligatoire** à partir de Campaign v8.6.

## Cela vous concerne-t-il ?{#migrate-ims-impacts}

Si les opérateurs et opératrices de votre entreprise se connectent à la console cliente Campaign à l’aide de leur nom d’utilisateur/mot de passe (c’est-à-dire via une authentification native), cette étape vous concerne et vous devez migrer ces opérateurs et opératrices vers Adobe IMS comme décrit ci-dessous.

La migration vers [Adobe Identity Management System (IMS)](https://helpx.adobe.com/fr/enterprise/using/identity.html){target="_blank"} est un impératif de sécurité visant à sécuriser et normaliser vos environnements, car la plupart des autres solutions et applications Adobe Experience Cloud sont déjà sur IMS.

## Migrer vers Adobe Developer Console{#ims-migration-procedure}

### Conditions préalables{#ims-migration-prerequisites}

Avant de commencer le processus de migration, contactez votre représentant ou représentante Adobe (Gestionnaire de transition), afin que les équipes techniques d’Adobe puissent migrer vos groupes d’opérateurs et opératrices existants et vos droits nommés vers Adobe Identity Management System (IMS).

### Principales étapes {#ims-migration-steps}

Les étapes clés de cette migration sont répertoriées ci-dessous :

1. Adobe met à niveau vos environnements vers Campaign v8.5.2.
1. Après la mise à niveau, vous pouvez toujours créer de nouveaux utilisateurs et de nouvelles utilisatrices avec les deux méthodes, en tant qu’utilisateur natif ou utilisatrice native ou avec IMS.
1. Votre administrateur ou administratrice Campaign interne doit faire correspondre des e-mails uniques à chaque utilisateur natif ou utilisatrice native sur la console cliente Campaign et envoyer une confirmation au/à la Gestionnaire de transition Adobe une fois l’opération terminée. Cette étape est détaillée dans [cette section](#ims-migration-id).
1. Utilisez Adobe pour sécuriser une date Adobe, afin d’exécuter la migration automatisée pour vos utilisateurs et utilisatrices (opérateurs et opératrices) et profils de produits non techniques. Cette étape nécessite une fenêtre d’une heure sans temps d’arrêt pour aucune de vos instances.
1. Votre administrateur ou administratrice Campaign interne valide ces modifications et fournit une validation. Après cette migration, vous ne devez plus créer d’opérateur ou d’opératrice qui s’authentifierait avec son identifiant et son mot de passe.

Vous pouvez désormais migrer vos opérateurs et opératrices techniques vers la console Adobe Developer, comme décrit dans [cette note technique](ims-migration.md). Cette étape est obligatoire si vous utilisez des API Campaign.

Une fois la migration terminée, confirmez auprès de votre Gestionnaire de transition Adobe. Adobe marque alors la migration comme terminée et bloque la création des utilisateurs natifs et utilisatrices natives, ainsi que leur connexion. Votre environnement est ensuite sécurisé et normalisé.

## Questions fréquentes {#ims-migration-faq}

### Quand puis-je démarrer la migration ? {#ims-migration-start}

La mise à niveau de votre environnement vers Campaign v8.5.2 constitue une condition préalable à la migration vers [Adobe Identity Management System (IMS)](https://helpx.adobe.com/fr/enterprise/using/identity.html){target="_blank"}.

Vous pouvez démarrer la migration IMS sur votre environnement intermédiaire, une fois qu’elle a été mise à niveau vers Campaign v8.5.2, et planifier en conséquence l’environnement de production.

### Que se passe-t-il après la mise à niveau de version vers Campaign v8.5.2 ? {#ims-migration-after-upgrade}

Une fois les environnements mis à niveau vers Campaign v8.5.2, vous pouvez lancer la transition vers [Adobe Identity Management System (IMS)](https://helpx.adobe.com/fr/enterprise/using/identity.html){target="_blank"}.

La création d’un utilisateur natif ou d’une utilisatrice native est toujours autorisée jusqu’à la fin de la migration IMS.

### Quand la migration est-elle terminée ? {#ims-migration-end}

Une fois la migration des utilisateurs finaux et utilisatices finales ainsi que des utilisateurs et utilisatrices et techniques vers Adobe Identity Management System (IMS) terminée, vous devez contacter votre Gestionnaire de transition Adobe pour qu’Adobe puisse marquer votre migration comme terminée, bloquer la création des personnes à partir de la console cliente et désactiver la connexion des utilisateurs finaux et utilisatrices finales.


### Comment créer des utlisateurs et utilisatrices après la migration ? {#ims-migration-native}

Une fois la migration IMS complète terminée, Adobe applique les restrictions qui bloquent la création des utilisateurs natifs et utilisatrices natives. Ces restrictions ne sont pas appliquées tant que la migration IMS n’est pas terminée.

Pour les nouvelles clientes et les nouveaux clients : la création d’un utilisateur natif ou d’une utilisatrice native n’est pas autorisée dès le départ.

En tant qu’administrateur ou administratrice Campaign, vous pouvez accorder des autorisations aux utilisateurs et utilisatrices de votre entreprise via Adobe Admin Console et la console cliente Campaign. Les utilisateurs et utilisatrices peuvent se connecter à Adobe Campaign au moyen de leur Adobe ID. Apprenez-en davantage en consultant [cette documentation](../../v8/start/gs-permissions.md).

### Comment ajouter des e-mails pour les personnes natives actuelles ? {#ims-migration-id}

En tant qu’administrateur ou administratrice Campaign, vous devez ajouter des ID d’e-mail à toutes les personnes natives à partir de la console cliente. Pour ce faire, suivez les étapes ci-après :

1. Connectez-vous à la console cliente et accédez à **Administration > Gestion des accès > Opérateurs**.
1. Sélectionnez l’opérateur ou l’opératrice à mettre à jour dans la liste.
1. Saisissez l’e-mail de l’opérateur ou de l’opératrice dans la section **Points de contact** du formulaire.
1. Enregistrez vos modifications.

Vous pouvez également importer un fichier CSV pour mettre à jour les e-mails de l’ensemble des profils des opérateurs et opératrices.


### Comment se connecter à Campaign via IMS ? {#ims-migration-log}

Découvrez comment vous connecter à Campaign avec votre Adobe ID dans [cette section](../../v8/start/connect.md).

### Y aura-t-il un temps d’arrêt pendant cette migration ? {#ims-migration-downtime}

Pour finaliser la migration (migrer les personnes et les profils de produits), Adobe nécessite une fenêtre d’une heure sans temps d’arrêt sur aucune de vos instances (workflows, etc.).

Pendant ce délai, tous les utilisateurs et toutes les utilisatrices de Campaign doivent se déconnecter et se reconnecter avec leur Adobe ID une fois la migration vers IMS terminée.

### Qu’advient-il des personnes connectées lors de la migration des utilisateurs et utilisatrices IMS ? {#ims-migration-log-off}

Adobe recommande vivement que toutes les personnes soient déconnectées pendant la période de migration.

### Les utilisateurs et utilisatrices de mon entreprise utilisent déjà IMS. Dois-je encore effectuer la migration IMS ?{#ims-migration-needed}

Cette migration comporte deux aspects : la migration des utilisateurs finaux et utilisatrices finales et la migration des utilisateurs et utilisatrices techniques (utilisée dans les API de votre code personnalisé).

Si l’ensemble de vos utilisateurs et utilisatrices (opérateurs et opératrices Campaign) sont sur IMS, il n’est pas nécessaire d’effectuer cette migration. Cependant, vous devez toujours migrer les utilisateurs et utilisatrices techniques que vous avez peut-être utilisés dans le code personnalisé. En savoir plus sur [cette page](ims-migration.md).

Une fois cette migration terminée, vous devez contacter votre Gestionnaire de transition Adobe afin qu’Adobe termine la migration.

## Liens utiles {#ims-useful-links}

* [Migration des utilisateurs et utilisatrices techniques vers Adobe Developer Console](ims-migration.md)
* [Comment se connecter à Campaign v8](../../v8/start/connect.md)
* [Accès et autorisations dans Adobe Campaign v8](../../v8/start/gs-permissions.md)
* [Notes de mise à jour d’Adobe Campaign v8](../../v8/start/release-notes.md)
* [Présentation d’Adobe Identity Management System (IMS)](https://helpx.adobe.com/fr/enterprise/using/identity.html){target="_blank"}

