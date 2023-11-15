---
product: campaign
title: Modifications à venir du canal de notification push
description: Modifications à venir du canal de notification push
feature: Push
role: Admin
level: Experienced
badge-v7: label="v7" type="Informative" tooltip="S’applique également à Campaign Classic v7"
badge-v8: label="v8" type="Positive" tooltip="S’applique à Campaign v8"
hide: true
hidefromtoc: true
source-git-commit: 65b8d84e600e1814484fa81fb814475c0a8b9296
workflow-type: tm+mt
source-wordcount: '869'
ht-degree: 23%

---

# Modifications à venir du canal de notification push {#push-upgrade}

Vous pouvez utiliser Campaign pour envoyer des notifications push sur les appareils Android. Pour ce faire, Campaign repose sur des services d&#39;abonnement spécifiques. Certaines modifications importantes apportées au service FCM (Android Firebase Cloud Messaging) seront publiées en 2024 et peuvent avoir une incidence sur votre mise en oeuvre d’Adobe Campaign. Il se peut que la configuration de vos services d’abonnement pour les messages push Android doive être mise à jour pour prendre en charge cette modification.

## Qu’est-ce qui a changé ? {#fcm-changes}

Dans le cadre des efforts continus de Google pour améliorer ses services, les API FCM héritées seront abandonnées sur **20 juin 2024**. En savoir plus sur le protocole HTTP Firebase Cloud Messaging dans [Documentation de Google Firebase](https://firebase.google.com/docs/cloud-messaging/http-server-ref){target="_blank"}.

Adobe Campaign Classic v7 et Adobe Campaign v8 prennent déjà en charge les dernières API pour envoyer des messages de notification push. Cependant, certaines anciennes implémentations dépendent toujours des API héritées. Ces mises en oeuvre doivent être mises à jour.

## Cela vous concerne-t-il ? {#fcm-impact}

Si votre mise en oeuvre actuelle prend en charge les services d’abonnement se connectant à FCM à l’aide des API héritées, vous êtes affecté. La migration vers les dernières API est obligatoire pour éviter toute distraction de service. Dans ce cas, les équipes d’Adobe vous contacteront.

Pour vérifier si vous êtes affecté, vous pouvez filtrer votre **Services et abonnements** selon le filtre ci-dessous :

![](assets/filter-services-fcm.png)


* Si l’un de vos services de notification push actifs utilise la variable **HTTP (hérité)** Votre configuration sera directement affectée par cette modification. Vous devez passer en revue vos configurations actuelles et migrer vers les API les plus récentes, comme décrit ci-dessous.

* Si votre configuration utilise exclusivement la variable **HTTP v1** API pour les notifications push Android, vous êtes déjà en conformité et aucune autre action ne sera requise de votre part.

## Migrer vers Adobe Developer Console {#fcm-migration-procedure}

### Conditions préalables {#fcm-migration-prerequisites}

* Pour Campaign Classic v7, la prise en charge de HTTP v1 a été ajoutée à la version 20.3.1. Si votre environnement s’exécute sur une ancienne version, une condition préalable à la migration vers HTTP v1 est de mettre à niveau votre environnement vers la [dernier build de Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/release-notes/latest-release.html?lang=fr){target="_blank"}. Pour Campaign v8, HTTP v1 est pris en charge par toutes les versions et aucune mise à niveau n&#39;est nécessaire.

* Le fichier JSON du compte du SDK Android Firebase Admin est nécessaire pour que l’application mobile soit déplacée vers HTTP v1. Découvrez comment obtenir ce fichier dans [Documentation de Google Firebase](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

* Pour les déploiements hybride, hébergé et Managed Services, en plus de la procédure de migration ci-dessous, contactez l’Adobe pour mettre à jour votre serveur d’exécution en temps réel (RT). Le serveur de mid-sourcing n’est pas affecté.

* En tant qu&#39;utilisateur on-premise de Campaign Classic v7, vous devez mettre à niveau les serveurs d&#39;exécution Marketing et Temps réel. Le serveur de mid-sourcing n’est pas affecté.

### Procédure de migration {#fcm-migration-steps}

Pour migrer votre environnement vers HTTP v1, procédez comme suit :

1. Accédez à votre liste de **Services et abonnements**.
1. Répertorier toutes les applications mobiles utilisant la variable **HTTP (hérité)** Version de l’API.
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

