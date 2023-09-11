---
title: Migration des opérateurs Campaign vers Adobe Identity Management System (IMS)
description: Découvrez comment migrer les opérateurs Campaign vers Adobe Identity Management System (IMS)
hide: true
hidefromtoc: true
source-git-commit: 74d97c4c61a305aff1d2f108a8a24cb6943dea07
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Migration des opérateurs Campaign vers Adobe Identity Management System (IMS) {#migrate-users-to-ims}

Campaign v8.6 et les versions ultérieures apportent des améliorations au processus d’authentification de Campaign v8. Tous les opérateurs vont utiliser [Adobe Identity Management System (IMS)](https://helpx.adobe.com/fr/enterprise/using/identity.html){target="_blank"} **only** pour vous connecter à Campaign. La connexion avec l’utilisateur/mot de passe (ou authentification native) ne sera plus autorisée. Adobe recommande d&#39;effectuer cette migration dans Campaign v8.5.2 afin de pouvoir migrer en douceur vers Campaign v8.6.

En tant que client des services gérés v7 Campaign Classic, si vous effectuez une migration vers Campaign v8, cette procédure s’applique également à vous.

Cet article décrit les étapes à suivre pour migrer un opérateur ou une opératrice technique vers un compte technique sur Adobe Developer Console.

## Qu’est-ce qui a changé ?{#move-to-ims-changes}

Avec Campaign v8, tous les utilisateurs standard doivent déjà se connecter à la console cliente Adobe Campaign à l&#39;aide de leur Adobe ID, via Adobe Identity Management System (IMS). Toutefois, avec certaines configurations plus anciennes, les connexions utilisateur/mot de passe étaient toujours disponibles. **Cela ne sera plus autorisé à partir de Campaign v8.6.**

En outre, dans le cadre de l&#39;effort visant à renforcer la sécurité et le processus d&#39;authentification, l&#39;application cliente Adobe Campaign appelle désormais les API Campaign directement à l&#39;aide du jeton de compte technique IMS. La migration des opérateurs techniques est présentée dans un article dédié, disponible dans la section [cette page](ims-migration.md).

Cette modification s’applique à partir de Campaign v8.5.2 et sera **obligatoire** à partir de Campaign v8.6.


## Cela vous concerne-t-il ?{#migrate-ims-impacts}

Si les opérateurs de votre entreprise se connectent à la console cliente Campaign à l’aide de leur login/mot de passe (c’est-à-dire authentification native), vous êtes affecté et devez migrer ces opérateurs vers Adobe IMS comme décrit ci-dessous.

Migration vers [Adobe Identity Management System (IMS)](https://helpx.adobe.com/fr/enterprise/using/identity.html){target="_blank"} est un impératif de sécurité pour sécuriser et normaliser vos environnements, car la plupart des autres solutions et applications Adobe Experience Cloud sont déjà sur IMS.

## Migrer vers Adobe Developer Console{#ims-migration-procedure}

### Conditions préalables{#ims-migration-prerequisites}

Avant de commencer le processus de migration, vous devez contacter votre représentant d’Adobe (Gestionnaire de transition) afin que les équipes techniques d’Adobe puissent migrer vos groupes d’opérateurs existants et vos droits nommés vers Adobe Identity Management System (IMS).

### Principales étapes {#ims-migration-steps}

Les étapes clés de cette migration sont répertoriées ci-dessous :

1. Adobe met à niveau vos environnements vers Campaign v8.5.2.
1. Après la mise à niveau, vous pouvez toujours créer de nouveaux utilisateurs avec les deux méthodes, en tant qu’utilisateur natif ou avec IMS.
1. Votre administrateur Campaign interne doit ajouter des emails uniques à tous les utilisateurs natifs sur la console cliente Campaign et confirmer l’Adobe du Gestionnaire de transition une fois que cela a été fait. Cette étape est présentée dans la section [cette section](#ims-migration-id).
1. Utilisez Adobe pour sécuriser une date d’Adobe afin d’exécuter la migration automatisée pour vos utilisateurs (opérateurs) et profils de produits non techniques. Cette étape nécessite une fenêtre d’une heure sans temps d’arrêt pour aucune de vos instances.
1. Votre administrateur Campaign interne valide ces modifications et fournit une validation. Après cette migration, vous ne devez plus créer d&#39;opérateur qui s&#39;authentifierait avec son identifiant et son mot de passe.

Vous pouvez maintenant planifier la migration des utilisateurs techniques vers IMS en fonction de [cette technote](ims-migration.md)et confirmez auprès de votre gestionnaire de transition d’Adobe une fois terminé.
Adobe marquera alors la migration comme terminée et activera les indicateurs pour bloquer la création d’un utilisateur natif et la connexion d’un utilisateur natif.

## Questions fréquentes {#ims-migration-faq}

### Quand puis-je démarrer la migration ? {#ims-migration-start}

Condition préalable à la migration vers [Adobe Identity Management System (IMS)](https://helpx.adobe.com/fr/enterprise/using/identity.html){target="_blank"} est de mettre à niveau votre environnement vers Campaign v8.5.2.

Vous pouvez démarrer la migration IMS sur votre environnement intermédiaire, une fois qu’elle a été mise à niveau vers Campaign v8.5.2, et planifier en conséquence l’environnement de production.

### Que se passe-t-il après l&#39;upgrade de build vers Campaign v8.5.2 ? {#ims-migration-after-upgrade}

Une fois les environnements mis à niveau vers Campaign v8.5.2, vous pouvez lancer la transition vers [Adobe Identity Management System (IMS)](https://helpx.adobe.com/fr/enterprise/using/identity.html){target="_blank"}.

La création d’un utilisateur natif est toujours autorisée jusqu’à la fin de la migration IMS.

### Quand la migration est-elle terminée ? {#ims-migration-end}

Une fois la migration des utilisateurs finaux et la migration des utilisateurs techniques vers Adobe Identity Management System (IMS) terminée, vous devez contacter votre gestionnaire de transition Adobe pour que l’Adobe puisse marquer votre migration comme terminée, bloquer la création des utilisateurs à partir de la console cliente et désactiver la connexion des utilisateurs natifs.


### Comment créer des utilisateurs après la migration ? {#ims-migration-native}

Une fois la migration IMS complète terminée, Adobe appliquera les restrictions qui bloqueront la création d’utilisateurs natifs. Ces restrictions ne sont pas appliquées tant que la migration IMS n’est pas terminée.

Pour les nouveaux clients : la création d’un nouvel utilisateur natif n’est pas autorisée depuis le début.

En tant qu’administrateur de Campaign, vous pouvez accorder des autorisations aux utilisateurs de votre entreprise via Adobe Admin Console et la console cliente Campaign. Les utilisateurs peuvent se connecter à Adobe Campaign au moyen de leur Adobe ID. En savoir plus dans [cette documentation](../../v8/start/gs-permissions.md).

### Comment ajouter des emails pour les utilisateurs natifs actuels ? {#ims-migration-id}

En tant qu’administrateur de Campaign, vous devez ajouter des ID d’email à tous les utilisateurs natifs à partir de la console cliente. Pour ce faire, suivez les étapes ci-après :

1. Connectez-vous à la console cliente et accédez à **Administration > Gestion des accès > Opérateurs**.
1. Sélectionnez l&#39;opérateur à mettre à jour dans la liste des opérateurs.
1. Saisissez l&#39;email de l&#39;opérateur dans la **Points de contact** du formulaire de l&#39;opérateur.
1. Enregistrez vos modifications.

Vous pouvez également importer un fichier CSV pour mettre à jour tous les profils d’opérateurs avec leur email.


### Comment se connecter à Campaign via IMS ? {#ims-migration-log}

Découvrez comment vous connecter à Campaign avec votre Adobe ID dans [cette section](../../v8/start/connect.md).

### Y aura-t-il un temps d’arrêt pendant cette migration ? {#ims-migration-downtime}

Pour finaliser la migration (migrer les utilisateurs et les profils de produits), Adobe nécessite une fenêtre d&#39;une heure sans temps d&#39;arrêt sur aucune de vos instances (workflows, etc.).

Pendant cette période, tous les utilisateurs de Campaign doivent se déconnecter et se reconnecter avec leur Adobe ID une fois la migration vers IMS terminée.

### Qu’advient-il des utilisateurs connectés lors de la migration des utilisateurs IMS ? {#ims-migration-log-off}

Adobe recommande vivement que tous les utilisateurs soient déconnectés pendant la fenêtre de migration.

### Les utilisateurs de mon entreprise utilisent déjà IMS. Dois-je encore effectuer la migration IMS ?

Cette migration comporte deux aspects : la migration des utilisateurs finaux et la migration des utilisateurs techniques (utilisés dans les API de votre code personnalisé).

Si tous vos utilisateurs (opérateurs Campaign) sont sur IMS, il n&#39;est pas nécessaire d&#39;effectuer cette migration. Cependant, vous devez toujours migrer les utilisateurs techniques que vous avez peut-être utilisés dans le code personnalisé. En savoir plus sur [cette page](ims-migration.md).

Une fois cette migration terminée, vous devez contacter votre Gestionnaire de transition Adobe afin que l’Adobe termine la migration.