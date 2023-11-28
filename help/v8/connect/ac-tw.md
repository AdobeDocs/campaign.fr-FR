---
title: Utilisation de Campaign et X (Twitter)
description: Découvrez comment intégrer votre environnement Campaign à X (anciennement appelé Twitter)
role: User, Admin
feature: Social Marketing
level: Beginner, Intermediate
exl-id: 5523217a-b95f-4639-b941-52eb7d5a0203
source-git-commit: f463c5747b844544ba561a63e4cb0359c0c258c8
workflow-type: tm+mt
source-wordcount: '1132'
ht-degree: 45%

---

# Utilisation de Campaign et X (Twitter) {#tw-ac-ovv}

La variable **Gestion des réseaux sociaux (Social Marketing)** vous permet d’interagir avec vos clients via X (anciennement appelé Twitter). Utilisez cette fonctionnalité pour :

* Publier des messages et envoyer des DM : utilisez Adobe Campaign Social Marketing pour publier des messages sur X. Vous pouvez également envoyer des messages directs à tous vos abonnés.

* Collecter de nouveaux contacts : le marketing social d&#39;Adobe Campaign facilite également l&#39;acquisition de nouveaux contacts. Contactez les utilisateurs et demandez-leur s&#39;ils souhaitent partager leurs informations de profil. S&#39;ils acceptent, Adobe Campaign récupère automatiquement les données. Vous pouvez ainsi exécuter des campagnes de ciblage et, lorsque cela est possible, implémenter des stratégies cross-canal.

![](../assets/do-not-localize/speech.png) En tant qu’utilisateur Cloud Service géré, [contact Adobe](../start/campaign-faq.md#support) pour connecter Campaign à X. Le  **Gestion des réseaux sociaux (Social Marketing)** le module complémentaire doit être installé sur votre environnement, par le biais du module dédié, et le compte externe Twitter doit être configuré.


Pour configurer Adobe Campaign de manière à publier des tweets sur vos comptes X, vous devez déléguer à Adobe Campaign les droits d’écriture sur ces comptes. Pour cela, vous devez :

1. Créez un compte X et inscrivez-vous à un compte Développeur. [En savoir plus](#dev-account)
1. (facultatif) Créez un compte de test X pour envoyer des bons à tirer. [En savoir plus](#tw-test-account)
1. Créez une application X (une application par compte X). [En savoir plus](#create-an-app-on-twitter)
1. Création d’un service pour **[!UICONTROL Twitter]** (un service par compte X). [En savoir plus](#create-tw-service)
1. Synchronisez votre compte X avec Campaign. [En savoir plus](#synchro-tw-accounts)

## Compte de développeur X {#dev-account}

Pour commencer avec cette intégration, vous devez vous inscrire à un [Compte de développeur X](https://developer.twitter.com){target="_blank"}.

Campaign utilise la version 1.1 de l’API X. Pour l’utiliser, vous devez demander un accès élevé via le portail destiné aux développeurs. En savoir plus sur X Eleved Access [dans cette page](https://developer.twitter.com/en/portal/products/elevated){target="_blank"}.

## Création d’une application sur X {#create-an-app-on-twitter}

Une fois que vous avez reçu l’autorisation d’accès élevé, créez une application X pour permettre à Adobe Campaign de créer des publications sur votre compte X. Pour ce faire, procédez comme suit :

1. Connectez-vous à votre compte X.
1. Se connecter à [Portail de développement X](https://developer.twitter.com/en/apps).
1. Sélectionnez **Créer une application**.
1. Laissez X assistant vous guider tout au long du processus.
1. Pour permettre à Adobe Campaign de créer des publications sur votre compte, modifiez la variable **Autorisations des applications** dans la section Configuration de l’authentification de l’utilisateur de votre application. Sélectionnez **Lecture, écriture et messages directs**.

   ![](assets/tw-permissions.png)

1. Dans la section **Type d’application**, sélectionnez **Application web, application automatisée ou robot**. Vous pouvez laisser le champ **URL de rappel** vide et enregistrer votre configuration.

   ![](assets/tw-app-type.png)

1. Revenez au tableau de bord de votre application, sélectionnez votre application et accédez à l’onglet **Clés et jetons**. Sous **Jeton d’accès et secret**, si l’autorisation **Lecture, écriture et messages directs** n’est pas mentionnée, vous devez régénérer le jeton et le secret de votre application. Notez que toutes les clés et tous les jetons doivent être enregistrés lors de leur création. Vous en aurez besoin pour configurer votre service Campaign Twitter.

   ![](assets/tw-permissions-check.png)


>[!NOTE]
>
>Vous avez besoin d’une application par compte X. Par conséquent, vous devez créer une autre application de test pour envoyer des BAT à votre compte de test.
>

## Créer un service Twitter dans Campaign {#create-tw-service}

Pour lier votre instance Campaign à votre compte X, créez une **Twitter** service et déléguer les droits d’écriture à Campaign.

>[!CAUTION]
>
>En créer un **Twitter** service par compte X. Par conséquent, vous devez créer un autre service de test pour envoyer des BAT à votre [compte de test](#tw-test-account).
>
>Chaque service **Twitter** doit également être créé par Adobe sur votre instance MID. Contactez votre représentant Adobe pour que votre environnement soit configuré.
>

Pour entrer des paramètres, vous devez accéder à la console cliente Adobe Campaign et aux autorisations de votre application X.

1. Dans **Adobe Campaign**, accédez à l&#39;onglet **[!UICONTROL Profils et cibles]**, puis sélectionnez le lien **[!UICONTROL Services et abonnements]**.
1. Créez un service.
1. Sélectionnez le type **[!UICONTROL Twitter]**.
1. Renseignez le libellé et le nom interne du service.

   >[!CAUTION]
   >
   >La variable **[!UICONTROL Nom interne]** du service doit être exactement le même nom que votre compte X.
   >

1. Par défaut, les abonnés sont enregistrés dans le dossier **[!UICONTROL Visiteurs]**. Vous pouvez sélectionner un autre emplacement dans le champ **[!UICONTROL Dossier des visiteurs]**. [En savoir plus](../send/twitter.md#direct-tw-messages)

   ![](assets/tw-service-in-ac.png)

   >[!NOTE]
   >
   >La variable **[!UICONTROL Synchronisation des abonnements]** est activée par défaut : cette option récupère automatiquement la liste de vos abonnés X afin que vous puissiez [envoyer des messages directs ;](../send/twitter.md#direct-tw-messages). La synchronisation est effectuée par un [workflow technique dédié](#synchro-tw-accounts).

1. Dans votre application X, copiez le contenu de la variable **Clé API** et **[Clé API secrète]** et collez-les dans le champ **[!UICONTROL Clé du client]** et **[!UICONTROL Secret du client]** champs de votre campagne **Twitter** service.

1. Dans votre application X, copiez le contenu de la variable **Jeton d’accès** et **Secret du jeton d’accès** et collez-les dans le champ **[!UICONTROL Jeton d’accès]** et **[!UICONTROL Secret du jeton d’accès]** champs de votre campagne **Twitter** service.

1. Dans la console cliente Campaign, cliquez sur **[!UICONTROL Enregistrer]**. Vous avez désormais délégué l’accès en écriture à Adobe Campaign.

Pour vérifier vos paramètres, vous pouvez :

* Modifier le service **Twitter** que vous venez de créer.
* Parcourir l’onglet **[!UICONTROL Page Twitter]** : votre compte Twitter doit s’afficher.
  ![](assets/tw-page.png)

## Synchroniser votre compte X {#synchro-tw-accounts}

La synchronisation entre Campaign et X est gérée au travers de workflows techniques dédiés. Ces workflows sont stockés dans le dossier **[!UICONTROL Administration > Exploitation > Workflows techniques > Gestion des réseaux sociaux]**.

Ils sont arrêtés par défaut : vous devez les démarrer manuellement lorsque vous commencez à utiliser le module **Marketing social**.

La variable **[!UICONTROL Synchronisation des comptes de Twitter]** le workflow technique synchronise X comptes dans Adobe Campaign. Ce workflow récupère la liste des abonnés X afin que vous puissiez leur envoyer des messages directs. [En savoir plus](../send/twitter.md#direct-tw-messages)

Par défaut, ce workflow est déclenché tous les jeudis à 7 h 30. Vous pouvez utiliser l’option **[!UICONTROL Exécuter la ou les tâches en attente maintenant]** pour démarrer le workflow à tout moment pendant que vous mettez en œuvre cette intégration.  Vous pouvez également modifier le planificateur pour modifier la fréquence de déclenchement du workflow. En savoir plus sur [cette page](../../automation/workflow/scheduler.md).

>[!CAUTION]
>
>Pour récupérer la liste des abonnés X, la variable **[!UICONTROL Synchronisation des comptes de twitter]** doit être cochée pour le service associé au compte. [En savoir plus](#create-tw-service)

Les abonnés sont stockés dans un tableau spécifique : la table des visiteurs. Pour afficher la liste de X abonnés, accédez à la **[!UICONTROL Profils et cibles > Visiteurs]**.

Pour chaque abonné, Adobe Campaign stocke les informations suivantes :

* **[!UICONTROL Origine]** : Twitter
* **[!UICONTROL ID externe]** : identifiant de l’utilisateur
* **[!UICONTROL Nom d’utilisateur]** : nom du compte de l’utilisateur
* **[!UICONTROL Nom complet]** : nom de l’utilisateur
* **[!UICONTROL Nombre d’amis]** : nombre d’abonnés au compte de l’utilisateur
* **[!UICONTROL Vérifié]** : ce champ indique si l’utilisateur possède un compte Twitter vérifié

Une fois cette configuration terminée, vous pouvez créer des publications sur vos comptes X et envoyer des messages directs à vos abonnés. [En savoir plus](../send/twitter.md)

## Création d’un compte de test sur X {#tw-test-account}

En plus d’un compte X, créez un compte X privé utilisable pour l’envoi. [BAT de tweet](../send/twitter.md#send-tw-proofs). Pour ce faire, procédez comme suit :

1. Créez un compte X.
1. Accédez aux **Paramètres** du compte.
1. Accédez à **Confidentialité et sécurité** et **Audience et balisage** et vérifiez la variable **Protect de vos publications** . Les publications et autres informations de compte ne sont visibles que par les personnes qui vous suivent.

![](assets/social_tw_test_page.png)

Configurez votre application X et le service Campaign pour qu’ils fonctionnent avec ce compte de test, comme décrit ci-dessus.
