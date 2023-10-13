---
title: Utilisation de Campaign et Twitter
description: Découvrez comment intégrer votre environnement Campaign à Twitter
role: User, Admin
feature: Social Marketing
level: Beginner, Intermediate
exl-id: 5523217a-b95f-4639-b941-52eb7d5a0203
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '1122'
ht-degree: 100%

---

# Utilisation de Campaign et Twitter {#tw-ac-ovv}

Le module **Gestion des réseaux sociaux (Social Marketing)** vous permet d&#39;interagir avec vos clients via Twitter. Utilisez cette fonctionnalité pour :

* Publier des messages et envoyer des messages directs : utilisez le marketing des médias sociaux Adobe Campaign pour publier des messages sur Twitter. Vous pouvez également envoyer des messages directs à tous les abonnés de vos comptes.

* Collecter de nouveaux contacts : le marketing social d&#39;Adobe Campaign facilite également l&#39;acquisition de nouveaux contacts. Contactez les utilisateurs et demandez-leur s&#39;ils souhaitent partager leurs informations de profil. S&#39;ils acceptent, Adobe Campaign récupère automatiquement les données. Vous pouvez ainsi exécuter des campagnes de ciblage et, lorsque cela est possible, implémenter des stratégies cross-canal.

![](../assets/do-not-localize/speech.png)En tant qu&#39;utilisateur Managed Cloud Services, [contactez Adobe](../start/campaign-faq.md#support) pour connecter Campaign à Twitter. Le module complémentaire **Gérer les réseaux sociaux (marketing des médias sociaux)** doit être installé sur votre environnement, par le biais d’un package dédié, et le compte externe Twitter doit être configuré.


Pour configurer Adobe Campaign afin de publier des tweets sur vos comptes Twitter, vous devez déléguer à Adobe Campaign les droits d’écriture sur ces comptes. Pour cela, vous devez :

1. Vous inscrire sur Twitter et créer un compte de développeur. [En savoir plus](#dev-account)
1. Créez un compte Twitter de test dédié à l’envoi de BAT (facultatif). [En savoir plus](#tw-test-account)
1. Créez une application Twitter (une application par compte Twitter). [En savoir plus](#create-an-app-on-twitter)
1. Créez un service pour **[!UICONTROL Twitter]** (un service par compte Twitter). [En savoir plus](#create-tw-service)
1. Synchronisez votre compte Twitter avec Campaign. [En savoir plus](#synchro-tw-accounts)

## Compte de développeur Twitter {#dev-account}

Pour commencer avec cette intégration, vous devez vous inscrire à un [Compte de développeur Twitter](https://developer.twitter.com){target="_blank"}.

Campaign utilise la version 1.1 de l’API Twitter. Pour l’utiliser, vous devez demander un accès élevé via le portail destiné aux développeurs. Pour en savoir plus sur l’accès élevé à Twitter, consultez [cette page](https://developer.twitter.com/en/portal/products/elevated){target="_blank"}.

## Créer une application sur Twitter {#create-an-app-on-twitter}

Une fois que vous avez reçu l’autorisation d’accès élevé, créez une application Twitter pour permettre à Adobe Campaign de publier des tweets sur votre compte Twitter. Pour ce faire, procédez comme suit :

1. Connectez-vous à votre compte Twitter.
1. Connectez-vous au [Portail de développement Twitter](https://developer.twitter.com/en/apps).
1. Sélectionnez **Créer une application**.
1. Laissez-vous guider par l&#39;assistant Twitter.
1. Pour permettre à Adobe Campaign de publier des tweets sur votre compte, modifiez les **Autorisations d’application** dans la section Configuration de l’authentification de l’utilisateur de votre application. Sélectionnez **Lecture, écriture et messages directs**.

   ![](assets/tw-permissions.png)

1. Dans la section **Type d’application**, sélectionnez **Application web, application automatisée ou robot**. Vous pouvez laisser le champ **URL de rappel** vide et enregistrer votre configuration.

   ![](assets/tw-app-type.png)

1. Revenez au tableau de bord de votre application, sélectionnez votre application et accédez à l’onglet **Clés et jetons**. Sous **Jeton d’accès et secret**, si l’autorisation **Lecture, écriture et messages directs** n’est pas mentionnée, vous devez régénérer le jeton et le secret de votre application. Notez que toutes les clés et tous les jetons doivent être enregistrés lors de leur création. Vous en aurez besoin pour configurer votre service Campaign Twitter.

   ![](assets/tw-permissions-check.png)


>[!NOTE]
>
>Vous avez besoin d&#39;une application par compte Twitter. Par conséquent, vous devez créer une autre application de test pour envoyer des BAT à votre compte de test.
>

## Créer un service Twitter dans Campaign {#create-tw-service}

Pour lier votre instance Campaign à votre compte Twitter, créez un service **Twitter** et déléguez les droits d&#39;écriture à Campaign.

>[!CAUTION]
>
>Créez un service **Twitter** par compte Twitter. Par conséquent, vous devez créer un autre service de test pour envoyer des BAT à votre [compte de test](#tw-test-account).
>
>Chaque service **Twitter** doit également être créé par Adobe sur votre instance MID. Contactez votre représentant Adobe pour que votre environnement soit configuré.
>

Pour entrer des paramètres, vous devez accéder à la fois à la console cliente Adobe Campaign et aux autorisations de votre application Twitter.

1. Dans **Adobe Campaign**, accédez à l&#39;onglet **[!UICONTROL Profils et cibles]**, puis sélectionnez le lien **[!UICONTROL Services et abonnements]**.
1. Créez un service.
1. Sélectionnez le type **[!UICONTROL Twitter]**.
1. Renseignez le libellé et le nom interne du service.

   >[!CAUTION]
   >
   >Le **[!UICONTROL Nom interne]** du service doit être identique au nom du compte Twitter.
   >

1. Par défaut, les abonnés sont enregistrés dans le dossier **[!UICONTROL Visiteurs]**. Vous pouvez sélectionner un autre emplacement dans le champ **[!UICONTROL Dossier des visiteurs]**. [En savoir plus](../send/twitter.md#direct-tw-messages)

   ![](assets/tw-service-in-ac.png)

   >[!NOTE]
   >
   >L&#39;option **[!UICONTROL Synchroniser les abonnements]** est activée par défaut : cette option récupère automatiquement la liste de vos abonnés Twitter afin que vous puissiez [leur envoyer des messages directs](../send/twitter.md#direct-tw-messages). La synchronisation est effectuée par un [workflow technique dédié](#synchro-tw-accounts).

1. À partir de votre application Twitter, copiez le contenu des champs **Clé API** et **[Clé secrète API]** et collez-les dans les champs **[!UICONTROL Clé du client]** et **[!UICONTROL Secret du client]** de votre service Campaign **Twitter**.

1. À partir de votre appli Twitter, copiez le contenu des champs **Jeton d’accès** et **Secret de jeton d’accès**, puis collez-les dans les champs **[!UICONTROL Jeton d’accès]** et **[!UICONTROL Secret de jeton d’accès]** de votre service **Twitter** Campaign.

1. Dans la console cliente Campaign, cliquez sur **[!UICONTROL Enregistrer]**. Vous avez désormais délégué l’accès en écriture à Adobe Campaign.

Pour vérifier vos paramètres, vous pouvez :

* Modifier le service **Twitter** que vous venez de créer.
* Parcourir l’onglet **[!UICONTROL Page Twitter]** : votre compte Twitter doit s’afficher.
  ![](assets/tw-page.png)


## Synchroniser votre compte Twitter {#synchro-tw-accounts}

La synchronisation entre Campaign et Twitter est gérée via des workflows techniques dédiés. Ces workflows sont stockés dans le dossier **[!UICONTROL Administration > Exploitation > Workflows techniques > Gestion des réseaux sociaux]**.

Ils sont arrêtés par défaut : vous devez les démarrer manuellement lorsque vous commencez à utiliser le module **Marketing social**.

Le workflow technique **[!UICONTROL Synchronisation des comptes Twitter]** synchronise les comptes Twitter dans Adobe Campaign. Ce workflow récupère la liste des abonnés Twitter afin que vous puissiez leur envoyer des messages directs. [En savoir plus](../send/twitter.md#direct-tw-messages)

Par défaut, ce workflow est déclenché tous les jeudis à 7 h 30. Vous pouvez utiliser l&#39;option **[!UICONTROL Traitement anticipé de la (des) tâche(s)]** pour démarrer le workflow à tout moment pendant que vous mettez en œuvre cette intégration.  Vous pouvez également modifier le planificateur pour modifier la fréquence de déclenchement du workflow. En savoir plus sur [cette page](../../automation/workflow/scheduler.md).

>[!CAUTION]
>
>Pour récupérer la liste des abonnés Twitter, l&#39;option **[!UICONTROL Synchronisation des comptes Twitter]** doit être cochée pour le service associé au compte. [En savoir plus](#create-tw-service)

Les abonnés sont stockés dans un tableau spécifique : la table des visiteurs. Pour afficher la liste des abonnés Twitter, accédez à **[!UICONTROL Profils et cibles > Visiteurs]**.

Pour chaque abonné, Adobe Campaign stocke les informations suivantes :

* **[!UICONTROL Origine]** : Twitter
* **[!UICONTROL ID externe]** : identifiant de l’utilisateur
* **[!UICONTROL Nom d’utilisateur]** : nom du compte de l’utilisateur
* **[!UICONTROL Nom complet]** : nom de l’utilisateur
* **[!UICONTROL Nombre d’amis]** : nombre d’abonnés au compte de l’utilisateur
* **[!UICONTROL Vérifié]** : ce champ indique si l’utilisateur possède un compte Twitter vérifié

Une fois cette configuration terminée, vous pouvez publier des tweets sur vos comptes Twitter et envoyer des messages directs à vos abonnés. [En savoir plus](../send/twitter.md)

## Créer un compte Twitter de test {#tw-test-account}

Outre le compte Twitter, créez un compte Twitter privé utilisable pour l&#39;envoi de [BAT de tweet](../send/twitter.md#send-tw-proofs). Pour ce faire, procédez comme suit :

1. Créez un compte Twitter.
1. Accédez aux **Paramètres** du compte.
1. Accédez à **Confidentialité et sécurité**, puis à **Audience et balisage**. Sélectionnez l&#39;option **Protéger vos tweets**. Vos tweets et autres informations de compte ne sont visibles que par les personnes qui vous suivent.

![](assets/social_tw_test_page.png)

Configurez votre application Twitter et le service Campaign pour qu’ils fonctionnent avec ce compte de test, comme décrit ci-dessus.
