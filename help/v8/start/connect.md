---
solution: Campaign
product: Adobe Campaign
title: Découvrez comment vous connecter à Campaign v8
description: Connexion à Campaign v8
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
translation-type: tm+mt
source-git-commit: 1ac6b58e1d5731d4df4d6d7c6a9b25f0f41ff563
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 38%

---

# Connexion à Adobe Campaign v8{#gs-ac-connect}

La console cliente Campaign est un client riche qui vous permet de vous connecter à votre ou vos serveur(s) applicatif(s) Campaign.

Avant de commencer, vous devez :

* Vérifiez la compatibilité de votre système et de vos outils avec Adobe Campaign dans la [matrice de compatibilité](compatibility-matrix.md).
* Obtenir l’URL du serveur Campaign
* Obtention des informations d’identification de l’utilisateur

## Téléchargement et installation de la console client

Lorsque vous utilisez Campaign pour la première fois, ou si vous devez effectuer une mise à niveau vers une version plus récente, vous devez télécharger Client Console et l’installer.

Deux options sont disponibles :

1. En tant qu’administrateur Campaign, connectez-vous à Adobe [Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/encampaign.html) et téléchargez le programme d’installation de Client Console. Vous pouvez ensuite l’installer sur votre ordinateur local.

1. En tant qu’utilisateur final, l’Adobe peut déployer la console pour vous : une fois la console mise à jour, vous êtes invité à télécharger la dernière version de la console client dans une fenêtre contextuelle.

>[!CAUTION]
>
>L&#39;Adobe recommande de ne pas sélectionner l&#39;option **[!UICONTROL Ne plus poser cette question]** pour s&#39;assurer que tous les utilisateurs sont avertis lorsqu&#39;une nouvelle version de la console est disponible.  Si cette option est sélectionnée, l’utilisateur ne sera pas informé des nouvelles versions disponibles.

## Créer votre connexion

Une fois la console client installée, procédez comme suit pour créer la connexion au serveur d’applications :

1. Début la console à partir du menu Windows **[!UICONTROL Début]**, dans le groupe de programmes **Adobe Campaign**.

1. Cliquez sur le lien situé dans le coin supérieur droit des champs d’informations d’identification pour accéder à la fenêtre de configuration de la connexion.

1. Cliquez sur le menu **[!UICONTROL Ajouter > Connexion]** et saisissez le libellé et l’URL du serveur applicatif Adobe Campaign.

1. Définissez une connexion vers votre serveur applicatif Adobe Campaign à partir d’une URL. Utilisez soit un DNS ou un alias de la machine, soit votre adresse IP.

   Par exemple, vous pouvez utiliser une URL de type [`https://<machine>.<domain>.com`](https://myserver.adobe.com).

1. Si Adobe Identity Management System (IMS) est configuré pour votre organisation, cochez l’option **[!UICONTROL Se connecter à un Adobe ID]** .

1. Cliquez sur **[!UICONTROL OK]** pour enregistrer vos paramètres.

Vous pouvez ajouter autant de connexions que nécessaire pour vous connecter, par exemple, à vos environnements de test, d’évaluation et de production.

>[!NOTE]
>
>Le bouton **[!UICONTROL Ajouter]** permet de créer des **[!UICONTROL dossiers]** dans lesquels vous pourrez classer vos différentes connexions par des opérations de glisser-déposer.

## Connexion à Adobe Campaign

Pour vous connecter à une instance existante, procédez comme suit :

1. Début la console à partir du menu Windows **[!UICONTROL Début]**, dans le groupe de programmes **Adobe Campaign**.

1. Cliquez sur le lien situé dans le coin supérieur droit des champs d’informations d’identification pour accéder à la fenêtre de configuration de la connexion.

1. Sélectionnez l’instance de Campaign à laquelle vous devez vous connecter.

1. Cliquez sur **[!UICONTROL Ok]**.

1. Entrez vos informations de connexion utilisateur et cliquez sur **[!UICONTROL CONNECTER]**.

   ![](assets/sign-in-v8.png)

Selon votre configuration, vos informations d’identification peuvent être les suivantes :

* fourni par l’administrateur Campaign qui vous a accordé l’accès
* votre Adobe ID

## Accorder l&#39;accès aux utilisateurs

Adobe Campaign vous permet de définir et gérer les permissions attribuées aux différents opérateurs. Les permissions sont un ensemble de droits et restrictions qui autorisent ou interdisent :

* l&#39;accès à certaines fonctionnalités (via les droits nommés),
* Accès à certains éléments,
* Créer, modifier et/ou supprimer des éléments (diffusion, contacts, campagnes, groupes, etc.).

Pour en savoir plus sur les utilisateurs et comment définir leurs autorisations dans [cette section](permissions.md).

En tant qu’administrateur Campaign, vous êtes chargé de créer les opérateurs et de partager leurs informations d’identification avec les utilisateurs.

## Connectez-vous à Campaign avec votre Adobe ID{#connect-ims}

Les utilisateurs de Campaign peuvent se connecter à la console Adobe Campaign à l’aide de leur Adobe ID, via le système IMS (Adobe Identity Management System). Cette implémentation présente les avantages suivants :

* utilisation d&#39;un même identifiant pour toutes les solutions Experience Cloud
* mémorisation de la connexion lors de l&#39;utilisation d&#39;Adobe Campaign avec les différentes intégrations
* Stratégie de gestion des mots de passe plus stricte.
* utilisation de comptes de type Federated ID (fournisseur d&#39;identité externe)

:speak_bulon: En tant qu&#39;utilisateur Cloud Services géré, [contactez l&#39;Adobe](support.md#support) pour mettre en oeuvre l&#39;Adobe IMS avec Campaign.

## Connexion à Campaign à l’aide de votre connexion LDAP

Adobe Campaign peut être configuré de sorte que l’utilisateur accède à la plate-forme via son authentification LDAP.

:speak_bulon: En tant qu’utilisateur Cloud Services géré, [contactez l’Adobe](support.md#support) pour configurer l’intégration LDAP avec Campaign.


## Accès Web

Certaines parties de l’application sont accessibles via un navigateur Web simple à l’aide d’une interface utilisateur HTML : rapports, approbation des diffusions, surveillance des instances, etc.
