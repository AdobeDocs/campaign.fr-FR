---
title: Envoi de notification push avec Adobe Campaign
description: Prise en main des notifications push dans Campaign
feature: Push
role: Data Engineer
level: Beginner
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
source-git-commit: d8ceefe1dd56aecb810878d99395ac900f889c2e
workflow-type: tm+mt
source-wordcount: '1249'
ht-degree: 100%

---

# Création et envoi de notifications push{#push-notifications-create}

Les diffusions d&#39;applications mobiles vous permettent d&#39;envoyer des notifications aux systèmes iOS et Android.

Pour envoyer des notifications push dans Adobe Campaign, vous devez effectuer les opérations suivantes :

1. Configuration de votre environnement Campaign
1. Créez un service d&#39;information de type application mobile pour votre application mobile.
1. Ajoutez, à ce service, les versions iOS et Android de l&#39;application.
1. Créez une diffusion pour iOS et Android.

![](../assets/do-not-localize/book.png) Découvrez comment prendre en main les applications mobiles dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=fr).{target="_blank"}

## Intégrer le SDK {#push-sdk}

Vous pouvez utiliser le SDK mobile Adobe Experience Platform en configurant l’extension Adobe Campaign dans l’interface utilisateur de collecte de données. Le SDK mobile Adobe Experience Platform permet d’optimiser les solutions et services Experience Cloud d’Adobe dans vos applications mobiles. La configuration des SDK s’effectue dans l’interface utilisateur de collecte de données, qui offre des options de configuration flexibles et des intégrations extensibles basées sur des règles. [En savoir plus dans la documentation Adobe Developer](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic){target="_blank"}.

Découvrez comment configurer et installer le SDK mobile Adobe Experience Platform [dans cette vidéo](https://experienceleague.adobe.com/docs/campaign-classic-learn/tutorials/sending-messages/push-channel/configure-push-using-aep-mobile-sdk.html?lang=fr){target="_blank"}.

Vous pouvez également intégrer le SDK Campaign pour faciliter l’intégration de votre application mobile dans la plateforme Adobe Campaign. Les versions de SDK compatibles sont répertoriées dans la [Matrice de compatibilité Campaign](../start/compatibility-matrix.md#MobileSDK).

Découvrez comment intégrer les SDK Android et iOS de Campaign à votre application sur [cette page](../config/push-config.md).

## Configuration des paramètres de votre application dans Campaign{#push-config}

Vous devez définir les paramètres de vos applications iOS et Android dans Adobe Campaign.

![](../assets/do-not-localize/book.png) Les instructions de configuration pour iOS sont décrites dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=fr#sending-messages).{target="_blank"}

![](../assets/do-not-localize/book.png) Les instructions de configuration pour Android sont décrites dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=fr#sending-messages).{target="_blank"}

## Création de votre première notification push{#push-create}

Cette section présente les éléments spécifiques à la diffusion de notifications iOS et Android.

>[!CAUTION]
>
>Dans le contexte d’un [Déploiement Enterprise (FFDA)](../architecture/enterprise-deployment.md), l’enregistrement mobile est désormais **asynchrone**. [En savoir plus](../architecture/staging.md)

Pour créer une nouvelle diffusion, accédez à l&#39;onglet **[!UICONTROL Campagnes]**, cliquez sur **[!UICONTROL Diffusions]**, puis sur le bouton **[!UICONTROL Créer]** au-dessus de la liste des diffusions existantes.

![](assets/delivery_step_1.png)

’![](../assets/do-not-localize/book.png) Pour plus d’informations générales sur la création d&#39;une diffusion, consultez la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=fr#sending-messages){target="_blank"}

### Envoyer des notifications sur iOS {#send-notifications-on-ios}

>[!NOTE]
>
>Cette fonctionnalité est disponible à partir de Campaign v8.3. Pour vérifier votre version, reportez-vous à [cette section](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

1. Sélectionnez le modèle de diffusion **[!UICONTROL Diffuser sur iOS]**.

   ![](assets/push_ios_1.png)

1. Pour définir la cible de la notification, cliquez sur le lien **[!UICONTROL Pour]**, puis sur **[!UICONTROL Ajouter]**.

   ![](assets/push_ios_2.png)

1. Sélectionnez **[!UICONTROL Abonnés d&#39;une application mobile iOS (iPhone, iPad)]**, choisissez le service correspondant à votre application mobile, puis sélectionnez la version iOS de l&#39;application.

   ![](assets/push_ios_3.png)

1. Choisissez votre **[!UICONTROL Type de notification]** entre **[!UICONTROL Notification générale (alerte, son, pastille)]** ou **[!UICONTROL Notification silencieuse]**.

   ![](assets/push_ios_4.png)

   >[!NOTE]
   >
   >Le mode **Notification silencieuse** permet d&#39;envoyer une notification &quot;silencieuse&quot; à une application mobile. L&#39;utilisateur n&#39;est pas averti de l&#39;arrivée de la notification. Elle est directement transférée à l&#39;application.

1. Dans le champ **[!UICONTROL Titre]**, saisissez le libellé du titre qui doit apparaître dans la liste des notifications disponibles depuis le centre de notifications.

   Ce champ vous permet de définir la valeur du paramètre **Titre** de la payload de notification iOS.

1. Vous pouvez ajouter un **[!UICONTROL Sous-titre]**, valeur du paramètre **sous-titre** de la payload de notification iOS.

1. Saisissez le contenu du message dans la section **[!UICONTROL Contenu du message]** de l’assistant.

1. Dans l’onglet **[!UICONTROL Son et pastille]** vous pouvez modifier les options suivantes :

   * **[!UICONTROL Nettoyer la pastille]** : activez cette option pour actualiser la valeur de la pastille.

   * **[!UICONTROL Valeur]** : définissez un nombre qui sera utilisé pour afficher directement sur l’icône de l’application le nombre de nouvelles informations non lues.

   * **[!UICONTROL Mode d’alerte critique]** : activez cette option pour ajouter du son à votre notification, même si le téléphone de l&#39;utilisateur est en mode thème ou si l’iPhone est en mode silencieux.

   * **[!UICONTROL Nom]** : sélectionnez le son que doit émettre le terminal mobile à la réception de la notification.

   * **[!UICONTROL Volume]** : volume de votre son de 0 à 100.

      >[!NOTE]
      > 
      >Les sons doivent être inclus dans l’application et définis lors de la création du service.
      >
      >Les instructions de configuration pour iOS sont décrites dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=fr){target="_blank"}.
   ![](assets/push_ios_5.png)

1. Dans l’onglet **[!UICONTROL Variables de l’application]**, vos **[!UICONTROL variables d’application]** sont automatiquement ajoutées. Elles permettent de définir le comportement des notifications. Par exemple, vous pouvez configurer l’affichage d’un écran spécifique lorsque l’utilisateur active la notification.

   Pour en savoir plus à ce sujet, consultez la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=fr){target="_blank"}.

1. Dans l’onglet **[!UICONTROL Avancé]**, vous pouvez modifier les options générales suivantes :

   * **[!UICONTROL Contenu mutable]** : activez cette option pour permettre à l’application mobile de télécharger le contenu multimédia.

   * **[!UICONTROL Thread-id]** : identifiant utilisé pour regrouper les notifications associées.

   * **[!UICONTROL Catégorie]** : nom de votre identifiant de catégorie qui affichera les boutons d’action. Ces notifications permettent à l&#39;utilisateur d&#39;effectuer plus rapidement différentes tâches en réponse à celles-ci, sans ouvrir l&#39;application ou la parcourir.

   ![](assets/push_ios_6.png)

1. Pour une notification sensible à l’heure, vous pouvez spécifier les options suivantes :

   * **[!UICONTROL Identifiant du contenu Target]** : identifiant utilisé pour cibler la fenêtre d&#39;application à afficher au premier plan à l&#39;ouverture de la notification.

   * **[!UICONTROL Image de Launch]** : nom du fichier image de Launch à afficher. Si l’utilisateur choisit de lancer votre application, l’image sélectionnée s’affichera au lieu de l’écran de lancement de votre application.

   * **[!UICONTROL Niveau d&#39;interruption]**:

      * **[!UICONTROL Actif]** : défini par défaut, le système présente immédiatement la notification, illumine l’écran et peut émettre un son. Les notifications ne passent pas en mode Thème.

      * **[!UICONTROL Passif]** : le système ajoute la notification à la liste de notifications sans allumer l’écran ni émettre de son. Les notifications ne passent pas en mode Thème.

      * **[!UICONTROL Sensible à l’heure]** : le système présente immédiatement la notification, allume l’écran, peut émettre un son et passer en mode Thème. Ce niveau ne nécessite pas d’autorisation spéciale de la part d’Apple.

      * **[!UICONTROL Critique]** : le système présente immédiatement la notification, allume l’écran et contourne le bouton de désactivation ou le mode de thème. Notez que ce niveau nécessite une autorisation spéciale de la part d’Apple.
   * **[!UICONTROL Score de pertinence]** : définissez un score de pertinence compris entre 0 et 100. Le système l’utilise pour trier les notifications dans le résumé de la notification.

   ![](assets/push_ios_7.png)

1. Une fois la notification renseignée, cliquez sur l&#39;onglet **[!UICONTROL Aperçu]** pour prévisualiser la notification.

   ![](assets/push-ios-preview.png)

### Envoi de notifications sur Android {#send-notifications-on-android}

1. Sélectionnez le modèle de diffusion **[!UICONTROL Diffuser sur Android (android)]**.

   ![](assets/push-template-android.png)

1. Pour définir la cible de la notification, cliquez sur le lien **[!UICONTROL Pour]**, puis sur **[!UICONTROL Ajouter]**.

   ![](assets/push-android-select-target.png)

1. Sélectionnez **[!UICONTROL Abonnés d&#39;une application mobile Android]**, choisissez le service correspondant à votre application mobile (Neotrips, dans notre exemple), puis sélectionnez la version Android de l&#39;application.

   ![](assets/push-android-subscribers.png)

1. Saisissez ensuite le contenu de la notification.

   ![](assets/push-android-content.png)

1. Cliquez sur l&#39;icône **[!UICONTROL Insérer une émoticône]** pour insérer des émoticônes dans votre notification push.

1. Dans le champ **[!UICONTROL Variables de l&#39;application]**, saisissez la valeur de chaque variable. Vous pouvez par exemple paramétrer un écran d&#39;application spécifique qui s&#39;affichera lorsque l&#39;utilisateur activera la notification.

1. Une fois la notification renseignée, cliquez sur l&#39;onglet **[!UICONTROL Aperçu]** pour prévisualiser la notification.

   <!--![](assets/push-android-preview.png)-->

## Test, envoi et surveillance de vos notifications push

L&#39;envoi du BAT et l&#39;envoi final de la notification s&#39;effectuent de la même manière que pour une diffusion par e-mail. Apprenez-en davantage en consultant la documentation de Campaign Classic v7 :

* Valider une diffusion et envoyer des BAT
   ![](../assets/do-not-localize/book.png) [En savoir plus sur les étapes clés de validation d’une diffusion](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=fr){target="_blank"}

* Confirmer et envoyer la diffusion
   ![](../assets/do-not-localize/book.png) [Découvrez les étapes clés pour envoyer une diffusion](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=fr){target="_blank"}.

Après l&#39;envoi des messages, vous pouvez surveiller et suivre vos diffusions. Apprenez-en davantage en consultant la documentation de Campaign Classic v7 :

* Quarantaines des notifications push

   ![](../assets/do-not-localize/book.png) [En savoir plus sur les quarantaines des notifications push](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-quarantine-management.html?lang=fr#push-notification-quarantines){target="_blank"}.

* Résolution des problèmes
   ![](../assets/do-not-localize/book.png) [Découvrez comment résoudre les problèmes liés aux notifications push](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/troubleshooting.html?lang=fr){target="_blank"}.
