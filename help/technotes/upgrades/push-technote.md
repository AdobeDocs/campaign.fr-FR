---
product: campaign
title: Modifications à venir du canal de notification push
description: Modifications à venir du canal de notification push
feature: Push
role: Admin
level: Experienced
badge-v7: label="v7" type="Informative" tooltip="S’applique également à Campaign Classic v7"
badge-v8: label="v8" type="Positive" tooltip="S’applique à Campaign v8"
exl-id: 45ac6f8f-eb2a-4599-a930-1c1fcaa3095b
source-git-commit: a494ac834b1febcafe04f4bb05eb74834df7b024
workflow-type: tm+mt
source-wordcount: '1408'
ht-degree: 56%

---

# Modifications du canal de notification push {#push-upgrade}

Vous pouvez utiliser Campaign pour envoyer des notifications push sur des appareils iOS et Android. Pour ce faire, Campaign repose sur les services d&#39;abonnement aux applications mobiles.

Certaines modifications importantes apportées au service FCM (Android Firebase Cloud Messaging) sont publiées en 2024 et peuvent avoir une incidence sur votre mise en oeuvre d’Adobe Campaign. Il se peut que la configuration de vos services d’abonnement pour les notifications push Android doive être mise à jour pour prendre en charge cette modification.

En outre, Adobe recommande vivement de passer à la connexion basée sur les jetons aux APNS plutôt qu’à une connexion basée sur certains, qui est plus sécurisée et évolutive.

## Service Google Android Firebase Cloud Messaging (FCM) {#fcm-push-upgrade}

### Qu’est-ce qui a changé ? {#fcm-changes}

Dans le cadre des efforts constants de Google pour améliorer ses services, les API FCM héritées seront abandonnées le **20 juin 2024**. Pour en savoir plus sur le protocole HTTP Firebase Cloud Messaging, consultez la [documentation de Google Firebase](https://firebase.google.com/docs/cloud-messaging/http-server-ref){target="_blank"}.

Adobe Campaign Classic v7 et Adobe Campaign v8 prennent déjà en charge les dernières API pour envoyer des notifications push. Cependant, certaines anciennes implémentations dépendent toujours des API héritées. Ces implémentations doivent être mises à jour.

### Cela vous concerne-t-il ? {#fcm-impact}

Si votre implémentation actuelle prend en charge les services d’abonnement se connectant à FCM à l’aide des API héritées, cela vous concerne. La transition vers les dernières API est obligatoire pour éviter toute distraction de service. Dans ce cas, les équipes Adobe vous contacteront.

Pour vérifier si cela vous concerne, vous pouvez filtrer vos **services et abonnements** selon le filtre ci-dessous :

![](assets/filter-services-fcm.png)


* Si l’un de vos services de notification push actifs utilise l’API **HTTP (héritée)**, votre configuration sera directement affectée par cette modification. Vous devez passer en revue vos configurations actuelles et passer aux API les plus récentes, comme décrit ci-dessous.

* Si votre configuration utilise exclusivement l’API **HTTP v1** pour les notifications push Android, vous êtes déjà en conformité et aucune autre action ne sera requise de votre part.

### Comment effectuer la mise à jour ? {#fcm-transition-procedure}

#### Conditions préalables {#fcm-transition-prerequisites}

* Pour Campaign Classic v7, la prise en charge de HTTP v1 a été ajoutée à la version 20.3.1. Si votre environnement s’exécute sur une ancienne version, une condition préalable à la transition vers HTTP v1 est de mettre à niveau votre environnement vers l’ [dernier build de Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/release-notes/latest-release.html?lang=fr){target="_blank"}. Pour Campaign v8, HTTP v1 est pris en charge par toutes les versions et aucune mise à niveau n’est nécessaire.

* Le fichier JSON du compte du service SDK Firebase Admin Android est nécessaire pour que l’application mobile soit déplacée vers HTTP v1. Découvrez comment obtenir ce fichier dans la [documentation de Google Firebase](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

* Pour les déploiements hybride, hébergé et Managed Services, en plus de la procédure de transition ci-dessous, contactez l’Adobe pour mettre à jour votre serveur d’exécution en temps réel (RT). Le serveur de midsourcing n’est pas affecté.

* En tant qu’utilisateur ou utilisatrice On-Premise de Campaign Classic v7, vous devez mettre à niveau les serveurs d’exécution Marketing et en temps réel. Le serveur de midsourcing n’est pas affecté.

#### Procédure de transition {#fcm-transition-steps}

Pour déplacer votre environnement vers HTTP v1, procédez comme suit :

1. Accédez à votre liste de **services et abonnements**.
1. Répertoriez toutes les applications mobiles à l’aide de la version d’API **HTTP (héritée)**.
1. Pour chacune de ces applications mobiles, définissez la **version d’API** sur **HTTP v1**.
1. Cliquez sur le lien **[!UICONTROL Charger le fichier JSON du projet pour extraire les détails du projet…]** pour charger directement votre fichier clé JSON.

   Vous pouvez également saisir manuellement les informations suivantes :

   * **[!UICONTROL Identifiant du projet]**
   * **[!UICONTROL Clé privée]**
   * **[!UICONTROL Email client]**

   ![](assets/android-http-v1-config.png)

1. Cliquez sur **[!UICONTROL Tester la connexion]** pour vérifier que votre configuration est correcte et que le serveur marketing a accès au FCM. Pour les déploiements de midsourcing, le bouton **[!UICONTROL Tester la connexion]** ne peut pas vérifier si le serveur a accès au service Android FCM (Firebase Cloud Messaging).
1. Vous pouvez, si nécessaire, enrichir un contenu de message push avec certaines **[!UICONTROL variables d&#39;application]**. Elles sont entièrement personnalisables et font partie de la payload du message envoyé à l&#39;appareil mobile.
1. Cliquez sur **[!UICONTROL Terminer]**, puis sur **[!UICONTROL Enregistrer]**.

Vous trouverez ci-dessous les noms de payload FCM pour personnaliser davantage votre notification push. Ces options sont décrites [ici](#fcm-apps).

| Type de message | Élément de message configurable (nom de payload FCM) | Options configurables (nom de payload FCM) |
|:-:|:-:|:-:|
| Message de données | N/A | validate_only |
| Message de notification | title, body, android_channel_id, icon, sound, tag, color, click_action, image, ticker, sticky, visibility, notification_priority, notification_count <br> | validate_only |


>[!NOTE]
>
>Une fois ces modifications appliquées à tous vos serveurs, toutes les nouvelles diffusions de notifications push vers les appareils Android utilisent l’API HTTP v1. Les diffusions de notifications push existantes en reprise, et actuellement utilisées continueront à utiliser l’API HTTP (héritée).

### Quel est l’impact pour mes applications Android ? {#fcm-apps}

Aucune modification spécifique du code des applications mobiles Android n’est requise et le comportement de notification ne doit pas changer.

Cependant, avec HTTP v1, vous pouvez personnaliser davantage votre notification push avec des **[!UICONTROL options supplémentaires HTTPV1]**.

![](assets/android-push-additional-options.png)

Vous pouvez ainsi :

* utiliser le champ **[!UICONTROL Bandeau déroulant]** pour définir le texte du bandeau déroulant de votre notification ;
* utiliser le champ **[!UICONTROL Image]** pour définir l’URL de l’image à afficher dans votre notification ;
* utiliser le champ **[!UICONTROL Nombre de notifications]** pour définir le nombre de nouvelles informations non lues à afficher directement sur l’icône de l’application ;
* définir l’option **[!UICONTROL Permanent]** sur false afin que la notification soit automatiquement ignorée lorsque l’utilisateur ou l’utilisatrice clique dessus. Si elle est définie sur true, la notification reste affichée même lorsque l’utilisateur ou l’utilisatrice clique dessus ;
* définir le niveau de **[!UICONTROL priorité de notification]** de votre notification : par défaut, minimum, faible ou élevé ;
* définir le niveau de **[!UICONTROL visibilité]** de votre notification sur public, privé ou secret.

Pour plus d’informations sur les **[!UICONTROL options supplémentaires HTTP v1]** et sur la façon de remplir ces champs, consultez la [documentation FCM](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#androidnotification){target="_blank"}.




## Service Apple iOS Push Notification (APNS) {#apns-push-upgrade}

### Qu’est-ce qui a changé ? {#ios-changes}

Comme recommandé par Apple, vous devez sécuriser vos communications avec le service Apple Push Notification (APN) en utilisant des jetons d’authentification sans état.

L’authentification par jeton offre un moyen sans état de communiquer avec les APNS. La communication sans état est plus rapide que la communication basée sur un certificat, car elle ne nécessite pas d’APNS pour rechercher le certificat, ou d’autres informations, liés à votre serveur de fournisseur. L’utilisation de l’authentification par jeton présente d’autres avantages :

* Vous pouvez utiliser le même jeton depuis plusieurs serveurs de fournisseurs.

* Vous pouvez utiliser un jeton pour distribuer des notifications pour toutes les applications de votre entreprise.

En savoir plus sur les connexions basées sur les jetons aux APNS dans [Documentation destinée aux développeurs Apple](https://developer.apple.com/documentation/usernotifications/establishing-a-token-based-connection-to-apns){target="_blank"}.

Adobe Campaign Classic v7 et Adobe Campaign v8 prennent en charge les connexions basées sur des jetons et sur des certificats. Si votre mise en oeuvre repose sur une connexion basée sur un certificat, Adobe vous recommande vivement de la mettre à jour vers une connexion basée sur un jeton.

### Cela vous concerne-t-il ? {#ios-impact}

Si votre mise en oeuvre actuelle repose sur des demandes basées sur des certificats pour vous connecter aux APNS, vous êtes concerné. Il est recommandé de passer à une connexion basée sur un jeton.

Pour vérifier si cela vous concerne, vous pouvez filtrer vos **services et abonnements** selon le filtre ci-dessous :

![](assets/filter-services-ios.png)


* Si l’un de vos services de notification push actifs utilise la variable **Authentification par certificat** , vos mises en oeuvre actuelles doivent être examinées et déplacées vers un **Authentification basée sur les jetons** comme décrit ci-dessous.

* Si votre configuration utilise exclusivement la variable **Authentification basée sur les jetons** pour les notifications push iOS, votre mise en oeuvre est déjà à jour et aucune autre action ne sera requise de votre part.

### Comment effectuer la mise à jour ? {#ios-transition-procedure}

#### Conditions préalables {#ios-transition-prerequisites}

* Pour Campaign Classic v7, la prise en charge de **Authentification basée sur les jetons** Le mode a été ajouté à la version 20.2. Si votre environnement s’exécute sur une ancienne version, une condition préalable à cette modification est de mettre à niveau votre environnement vers [dernier build de Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/release-notes/latest-release.html?lang=fr){target="_blank"}. Pour Campaign v8, **Authentification basée sur les jetons** est pris en charge par toutes les versions et aucune mise à niveau n’est nécessaire.

* Vous avez besoin d’une clé de signature de jeton d’authentification APNS pour générer les jetons utilisés par votre serveur. Vous demandez cette clé à votre compte de développeur Apple, en suivant la procédure décrite à la section [Documentation destinée aux développeurs Apple](https://developer.apple.com/documentation/usernotifications/establishing-a-token-based-connection-to-apns){target="_blank"}.

* Pour les déploiements hybride, hébergé et Managed Services, en plus de la procédure de transition ci-dessous, contactez l’Adobe pour mettre à jour votre serveur d’exécution en temps réel (RT). Le serveur de midsourcing n’est pas affecté.

* En tant qu’utilisateur ou utilisatrice On-Premise de Campaign Classic v7, vous devez mettre à niveau les serveurs d’exécution Marketing et en temps réel. Le serveur de midsourcing n’est pas affecté.

#### Procédure de transition {#ios-transition-steps}

Pour déplacer vos applications mobiles iOS vers le mode d&#39;authentification basé sur les jetons, procédez comme suit :

1. Accédez à votre liste de **services et abonnements**.
1. Répertorier toutes les applications mobiles utilisant la variable **Authentification par certificat** mode .
1. Modifiez chacune de ces applications mobiles et accédez au **Certificat/clé privée** .
1. Dans la **Mode d’authentification** , sélectionnez **Authentification basée sur les jetons**.
1. Renseignez les paramètres de connexion de l&#39;APNS **[!UICONTROL ID de clé]**, **[!UICONTROL Identifiant de l’équipe]** et **[!UICONTROL Bundle Id]** sélectionnez ensuite votre certificat p8 en cliquant sur **[!UICONTROL Entrez la clé privée...]**.

   ![](assets/token-based-certif.png)

1. Cliquez sur **[!UICONTROL Tester la connexion]** pour vérifier que votre configuration est correcte et que le serveur a accès aux APNS. Pour les déploiements Mid-sourcing, la variable **[!UICONTROL Tester la connexion]** ne peut pas vérifier si le serveur a accès aux APNS.
1. Cliquez sur **[!UICONTROL Suivant]** pour passer à la configuration de l’application de production et procédez comme décrit ci-dessus.
1. Cliquez sur **[!UICONTROL Terminer]**, puis sur **[!UICONTROL Enregistrer]**.

Votre application iOS est maintenant déplacée vers le mode d&#39;authentification basé sur les jetons.
