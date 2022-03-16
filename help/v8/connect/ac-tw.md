---
title: Utilisation de Campaign et Twitter
description: Découvrez comment intégrer votre environnement Campaign à Twitter
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: true
hide: true
exl-id: 5523217a-b95f-4639-b941-52eb7d5a0203
source-git-commit: 137dba3461a82621af7d2e5f54442bf87422ad47
workflow-type: tm+mt
source-wordcount: '975'
ht-degree: 26%

---

# Utilisation de Campaign et Twitter{#tw-ac-ovv}

Le **Gestion des réseaux sociaux (Social Marketing)** vous permet d’interagir avec vos clients via Twitter. Utilisez cette fonctionnalité pour :

* Envoyer des messages : utilisez Adobe Campaign Social Marketing pour publier des messages sur Twitter. Vous pouvez également envoyer des messages directs à tous les abonnés de vos comptes.

* Collecter de nouveaux contacts - Adobe Campaign Social Marketing permet également d&#39;acquérir facilement de nouveaux contacts : contactez les utilisateurs et demandez-leur s&#39;ils souhaitent partager leurs informations de profil. S’ils acceptent, Adobe Campaign récupère automatiquement les données. Vous pouvez ainsi exécuter des campagnes de ciblage et, lorsque cela est possible, implémenter des stratégies cross-canal.

![](../assets/do-not-localize/speech.png)  En tant qu’utilisateur Cloud Services géré, [contact Adobe](../start/campaign-faq.md#support) pour connecter Campaign à Twitter. Le  **Gestion des réseaux sociaux (Social Marketing)** doit être installé sur votre environnement, via le package dédié.


Pour configurer Adobe Campaign afin de publier des tweets sur vos comptes Twitter, vous devez déléguer à Adobe Campaign les droits d’écriture sur ces comptes. Pour cela :

1. Créez un compte Twitter
1. Créez un compte Twitter de test dédié à l&#39;envoi de BAT
1. Création d’une application Twitter (une application par compte Twitter)
1. Création d’un service pour **[!UICONTROL Twitter]** (un service par compte Twitter)

## Création d’un compte Twitter de test {#tw-test-account}

Outre le compte Twitter, créez un compte Twitter privé utilisable pour l’envoi [BAT de tweet](../send/twitter.md#send-tw-proofs). Pour ce faire, procédez comme suit :

1. Créez un compte Twitter.
1. Accédez aux **Paramètres** du compte.
1. Accédez à **Confidentialité et sécurité**, puis à **Audience et balisage**. Sélectionnez l’option **Protéger vos tweets**. Vos tweets et autres informations de compte ne sont visibles que par les personnes qui vous suivent.

![](assets/social_tw_test_page.png)

## Création d’une application sur Twitter {#create-an-app-on-twitter}

Créez une application Twitter pour permettre à Adobe Campaign de publier des tweets sur votre compte Twitter.  Pour ce faire, procédez comme suit :

1. Connectez-vous à votre compte Twitter.
1. Se connecter à [Portail de développement twitter](https://developer.twitter.com/en/apps).
1. Sélectionner **Création d’une application**.
1. Laissez l’assistant de Twitter vous guider tout au long du processus.

   Pour permettre à Adobe Campaign de publier des tweets sur votre compte, modifiez la variable **Autorisations** de l’application et sélectionnez **Lecture et écriture** pour le **Accès** . Dans le **Paramètres** , vous devez également laisser la variable **URL de callback** champ vide.

   ![](assets/social_tw_app.png)

>[!NOTE]
>
>Vous avez besoin d’une application par compte Twitter. Par conséquent, vous devez créer une autre application de test pour envoyer des bons à tirer à votre compte de test.

## Création d’un service Twitter dans Campaign {#create-tw-service}

Pour lier votre instance Campaign à votre compte Twitter, créez une **Twitter** service et déléguer les droits d’écriture à Campaign.

Pour entrer des paramètres, vous devez accéder à la fois à la console Adobe Campaign et à un compte Twitter :

1. Ouvrir **Twitter** et de [la page Projet et applications ;](https://developer.twitter.com/en/portal/projects-and-apps), sélectionnez l’application créée précédemment. Accédez au **Autorisations d’application**.

   ![](assets/social_tw_service.png)

   Modifiez l’onglet **Clés et jetons** pour accéder aux détails de votre application.

1. Dans **Adobe Campaign**, accédez au **[!UICONTROL Profils et cibles]** , puis sélectionnez la variable **[!UICONTROL Services et abonnements]** link
1. Créez un service.
1. Sélectionnez le type **[!UICONTROL Twitter]**.

   >[!NOTE]
   >
   >Le **[!UICONTROL Synchronisation des abonnements]** est activée par défaut : cette option récupère automatiquement la liste de vos abonnés Twitter afin que vous puissiez [envoyer des messages directs ;](../send/twitter.md#direct-tw-messages). La synchronisation est effectuée par une [workflow technique dédié](#synchro-tw-accounts).

1. Renseignez le libellé et le nom interne du service.

   >[!CAUTION]
   >
   >Le **[!UICONTROL Nom interne]** du service doit être exactement le même nom que votre compte Twitter. Pour vérifier vos paramètres, vous pouvez :

   * Cliquez sur le bouton **[!UICONTROL Enregistrer]**.
   * Dans la vue d’ensemble des services, sélectionnez la variable **Twitter** service que vous venez de créer.
   * Parcourez les **[!UICONTROL Page twitter]** tab : votre compte Twitter doit s’afficher.

1. Par défaut, les abonnés sont enregistrés dans le dossier **[!UICONTROL Visiteurs.]** Vous pouvez sélectionner un autre emplacement dans le **[!UICONTROL Dossier du visiteur]** champ . [En savoir plus](../send/twitter.md#direct-tw-messages)

1. Dans votre application Twitter, copiez le contenu de la variable **[!UICONTROL Clé client (clé API)]** et **[!UICONTROL Secret du client (secret d’API)]** et collez-les dans le champ **[!UICONTROL Clé du client]** et **[!UICONTROL Secret du client]** champs de votre campagne **Twitter** service.

1. Dans votre application Twitter, copiez le contenu de la variable **[!UICONTROL Jeton d’accès]** et **[!UICONTROL Secret du jeton d’accès]** et collez-les dans le champ **[!UICONTROL Jeton d’accès]** et **[!UICONTROL Secret du jeton d’accès]** champs de votre campagne **Twitter** service.

1. Dans la console client Campaign, cliquez sur **[!UICONTROL Enregistrer]**. Vous avez désormais délégué l’accès en écriture à Adobe Campaign.


>[!NOTE]
>
>En créer un **Twitter** par compte Twitter. Par conséquent, vous devez créer un autre service de test pour envoyer des bons à tirer à votre compte de test.

## Synchroniser votre compte Twitter {#synchro-tw-accounts}

La synchronisation entre Campaign et Twitter est gérée au travers de workflows techniques dédiés. Ces workflows sont stockés dans la variable **[!UICONTROL Administration > Exploitation > Workflows techniques > Gestion des réseaux sociaux]** dossier.

Ils sont arrêtés par défaut : vous devez les démarrer manuellement lorsque vous commencez à utiliser la variable **Social Marketing** module .

Le **[!UICONTROL Synchronisation des comptes twitter]** le workflow technique synchronise les comptes Twitter dans Adobe Campaign. Ce workflow récupère la liste des abonnés Twitter afin que vous puissiez leur envoyer des messages directs. [En savoir plus](../send/twitter.md#direct-tw-messages)

Par défaut, ce workflow est déclenché tous les jeudis à 7 h 30. Vous pouvez utiliser la variable **[!UICONTROL Traitement anticipé de la (des) tâche(s) en attente]** pour démarrer le workflow à tout moment pendant que vous mettez en oeuvre cette intégration.  Vous pouvez également modifier le planificateur pour modifier la fréquence de déclenchement du workflow. Apprenez-en davantage dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/scheduler.html){target=&quot;_blank&quot;}.

>[!CAUTION]
>
>Pour récupérer la liste des abonnés Twitter, la variable **[!UICONTROL Synchronisation des comptes twitter]** doit être cochée pour le service associé au compte. [En savoir plus](#create-tw-service)

Les abonnés sont stockés dans une table spécifique : la table des visiteurs. Pour afficher la liste des abonnés Twitter, accédez au **[!UICONTROL Profils et cibles > Visiteurs]**.

Pour chaque abonné, Adobe Campaign stocke les informations suivantes :

* **[!UICONTROL Origin]**: nom du réseau social (Twitter)
* **[!UICONTROL Id externe]** : identifiant de l&#39;utilisateur
* **[!UICONTROL Pseudo]** : nom de compte de l&#39;utilisateur
* **[!UICONTROL Nom complet]** : nom de l&#39;utilisateur
* **[!UICONTROL Langue]** : langue de l&#39;utilisateur
* **[!UICONTROL Nombre d&#39;amis]** : nombre d&#39;abonnés au compte de l&#39;utilisateur
* **[!UICONTROL Fuseau horaire]** : fuseau horaire de l&#39;utilisateur
* **[!UICONTROL Vérifié]** : ce champ indique si l&#39;utilisateur possède un compte Twitter vérifié

Une fois cette configuration terminée, vous pouvez publier des tweets sur vos comptes Twitter et envoyer des messages directs à vos abonnés. [En savoir plus](../send/twitter.md)
