---
product: campaign
title: Modifications à venir du canal de notification push
description: Modifications à venir du canal de notification push
hide: true
hidefromtoc: true
source-git-commit: 9ff84e523e7de6f1d6bb4e8cd193d19743fcf90c
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 23%

---

# Modifications à venir du canal de notification push {#push-upgrade}

Vous pouvez utiliser Campaign pour envoyer des notifications push sur les appareils Android. Pour ce faire, Campaign repose sur des comptes externes et des services d’abonnement Android spécifiques. Certaines modifications importantes apportées au service FCM (Android Firebase Cloud Messaging) seront publiées en 2024 et peuvent avoir une incidence sur votre mise en oeuvre d’Adobe Campaign.

## Qu’est-ce qui a changé ? {#fcm-changes}

Dans le cadre des efforts continus de Google pour améliorer ses services, les API FCM héritées seront abandonnées sur **20 juin 2024**. En savoir plus sur le protocole HTTP Firebase Cloud Messaging dans [Documentation Google](https://firebase.google.com/docs/cloud-messaging/http-server-ref){target="_blank"}.

Adobe Campaign Classic v7 et Adobe Campaign v8 prennent déjà en charge les dernières API pour envoyer des messages de notification push. Cependant, certaines anciennes implémentations dépendent toujours des API héritées. Ces mises en oeuvre doivent être mises à jour.

## Cela vous concerne-t-il ? {#fcm-impact}

Si votre mise en oeuvre actuelle prend en charge les services d’abonnement se connectant à FCM à l’aide des API héritées, vous êtes affecté. La migration vers les dernières API est obligatoire pour éviter toute distraction de service. Dans ce cas, les équipes d’Adobe vous contacteront.

Pour vérifier si vous êtes affecté, vous pouvez filtrer votre **Services et abonnements** selon le filtre ci-dessous :

![](assets/filter-services-fcm.png)


* Si l’une de vos campagnes de notification push active utilise la variable **HTTP (hérité)** Votre configuration sera directement affectée par cette modification. Vous devez passer en revue vos configurations actuelles et migrer vers les API les plus récentes, comme décrit ci-dessous.

* Si votre configuration utilise exclusivement la variable **HTTP v1** API pour les notifications push Android, vous êtes déjà en conformité et aucune autre action ne sera requise de votre part.

## Migrer vers Adobe Developer Console{#fcm-migration-procedure}

### Conditions préalables{#fcm-migration-prerequisites}

* Pour Campaign Classic v7, la prise en charge de HTTP v1 a été ajoutée à la version 20.3.1. Si votre environnement s’exécute sur une ancienne version, une condition préalable à la migration vers HTTP v1 est de mettre à niveau votre environnement vers la [dernier build de Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/release-notes/latest-release.html?lang=fr){target="_blank"}. Pour Campaign v8, HTTP v1 est pris en charge par toutes les versions. Aucune mise à niveau n’est nécessaire.

* Pour effectuer la migration, le fichier JSON du compte du SDK Android Firebase Admin est nécessaire pour que l’application mobile soit déplacée vers HTTPv1. Voir cette [page](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

* Pour les déploiements hybride, hébergé et Managed Services, contactez l’Adobe pour mettre à jour votre serveur d’exécution en temps réel (RT).

### Procédure de migration {#fcm-migration-steps}

Pour migrer votre environnement vers HTTP v1, procédez comme suit sur vos serveurs d’exécution Marketing et Temps réel :

1. Accédez à votre liste de **Services et abonnements**.

1. Localisez toutes les applications mobiles à l’aide du **HTTP (hérité)** Version de l’API.

1. Pour chacune de ces applications mobiles, définissez **Version de l’API** to **HTTP v1**.

1. Cliquez sur le bouton **[!UICONTROL Charger le fichier json du projet pour extraire les détails du projet...]** lien pour charger directement votre fichier de clé JSON.

   Vous pouvez également saisir manuellement les informations suivantes :
   * **[!UICONTROL Identifiant du projet]**
   * **[!UICONTROL Clé privée]**
   * **[!UICONTROL Email client]**

   ![](assets/android-http-v1-config.png)

1. Cliquez sur **[!UICONTROL Tester la connexion]** pour vérifier que votre configuration est correcte et que le serveur marketing a accès au FCM. Pour les déploiements Mid-sourcing, la variable **[!UICONTROL Tester la connexion]** ne peut pas vérifier si le serveur a accès au service FCM (Android Firebase Cloud Messaging).

1. Vous pouvez, si nécessaire, enrichir un contenu de message push avec certaines **[!UICONTROL variables d&#39;application]**. Elles sont entièrement personnalisables et font partie de la payload du message envoyé à l&#39;appareil mobile.

1. Cliquez sur **[!UICONTROL Terminer]**, puis sur **[!UICONTROL Enregistrer]**.

Vous trouverez ci-dessous les noms de payload FCM pour personnaliser davantage votre notification push. Ces options sont détaillées [here](#fcm-apps).

| Type de message | Élément de message configurable (nom de payload FCM) | Options configurables (nom de payload FCM) |
|:-:|:-:|:-:|
| Message de données | N/A | validate_only |
| Message de notification | title, body, android_channel_id, icon, sound, tag, color, click_action, image, ticker, sticky, visibility, notification_priority, notification_count <br> | validate_only |


>[!NOTE]
>
>Une fois ces modifications appliquées à tous vos serveurs, toutes les nouvelles diffusions de notifications push vers les appareils Android utilisent l’API HTTP v1. Les diffusions push existantes en reprise, en cours et en cours d’utilisation utilisent toujours l’API HTTP (héritée).

### Quel est l’impact pour mes applications Android ? {#fcm-apps}

Aucune modification spécifique n’est requise du code des applications mobiles Android et le comportement de notification ne doit pas changer.

Cependant, avec HTTP v1, vous pouvez personnaliser davantage votre notification push avec **[!UICONTROL Options supplémentaires HTTPV1]**.

![](assets/android-push-additional-options.png)

Vous pouvez ainsi :

* Utilisez la variable **[!UICONTROL Ticker]** pour définir le texte de la coche de votre notification.
* Utilisez la variable **[!UICONTROL Image]** pour définir l’URL de l’image à afficher dans votre notification.
* Utilisez la variable **[!UICONTROL Nombre de notifications]** pour définir le nombre de nouvelles informations non lues à afficher directement sur l’icône de l’application.
* Définissez la variable **[!UICONTROL Attractif]** sur false afin que la notification soit automatiquement ignorée lorsque l’utilisateur clique dessus. Si elle est définie sur true, la notification reste affichée même lorsque l&#39;utilisateur clique dessus.
* Définissez la variable **[!UICONTROL Priorité des notifications]** niveau de votre notification par défaut, minimum, faible ou élevé.
* Définissez la variable **[!UICONTROL Visibilité]** niveau de votre notification au public, privé ou secret.

Pour plus d&#39;informations sur les **[!UICONTROL options supplémentaires HTTPv1]** et sur la façon de remplir ces champs, consultez la [documentation FCM](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#androidnotification){target="_blank"}.

