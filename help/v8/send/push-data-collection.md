---
title: Envoi de notification push avec Adobe Campaign
description: Prise en main des notifications push dans Campaign
feature: Push
role: Data Engineer
level: Beginner
badge: label="Disponibilité limitée" type="Informatif"
source-git-commit: b71197027d9521fd648a0c2657b6b76a1aa7fc9a
workflow-type: tm+mt
source-wordcount: '1436'
ht-degree: 49%

---

# Configuration révisée des notifications push {#push-notifications-config}

>[!AVAILABILITY]
>
> Cette fonctionnalité est exclusivement accessible aux nouveaux clients à partir de la version 8.5 et progressivement déployée vers un ensemble de clients sélectionnés. Si votre environnement a été configuré avant juin 2023, vous devez suivre les procédures détaillées [dans cette page](push-settings.md).

Pour envoyer des notifications push dans Adobe Campaign, vous devez effectuer les opérations suivantes :

1. [Création d’une surface d’application dans la collecte de données Adobe Experience Platform](#create-app-surface)

1. [Configuration des paramètres de votre application dans Adobe Campaign](#push-config-campaign)

1. [Création et configuration d’une propriété mobile dans la collecte de données Adobe Experience Platform](#create-mobile-property)

1. [Ajout de l’extension Adobe Adobe Experience Platform Assurance](https://developer.adobe.com/client-sdks/documentation/platform-assurance-sdk/){target="_blank"}(recommandé)

1. [Ajouter un Campaign Classic à votre application mobile](#campaign-mobile-ap)

1. [Créez une diffusion pour iOS et Android](##push-create)

>[!NOTE]
>
> Les anciens FCM et APNS p12 ne sont pas pris en charge avec la collecte de données.

## Création d’une surface d’application dans la collecte de données Adobe Experience Platform {#create-app-surface}

Vous devez ajouter vos informations d’identification push d’application mobile dans [!DNL Adobe Experience Platform Data Collection].

L’enregistrement des informations d’identification push de l’application mobile est nécessaire pour autoriser Adobe à envoyer des notifications push en votre nom. Reportez-vous aux étapes détaillées ci-dessous :

1. De [!DNL Adobe Experience Platform Data Collection], sélectionnez la variable **[!UICONTROL Surfaces de l’application]** dans le panneau de gauche.

1. Cliquez sur **[!UICONTROL Créer une surface d’application]** pour créer une configuration.

   ![](assets/push-config-1.png)

1. Saisissez un **[!UICONTROL Nom]** pour la configuration.

1. De **[!UICONTROL Configuration des applications mobiles]**, sélectionnez Système opérationnel :

   * **Pour iOS**

     ![](assets/push-config-2.png)

      1. Saisie de l’application mobile **Bundle Id** dans le **[!UICONTROL ID d’application (ID de bundle iOS)]** champ .

         L’ID de bundle d’application se trouve dans la variable **Général** de la cible Principale dans **XCode** de votre compte de développeur Apple.

      1. Activer **[!UICONTROL Informations d’identification push]** pour ajouter vos informations d’identification.

      1. Faites glisser et déposez votre fichier de clé d’authentification de notification push Apple .p8.

         Cette clé peut être acquise à partir de la fonction **Certificats**, **Identificateurs** et **Profils** de votre compte de développeur Apple.

      1. Fournissez les **ID de clé**. Chaîne de 10 caractères attribuée lors de la création de la clé d’authentification p8.

         Il se trouve sous **Clés** dans **Certificats**, **Identificateurs** et **Profils** page de votre compte de développeur Apple.

      1. Fournissez les **Identifiant de l’équipe**. Il s’agit d’une valeur string qui se trouve sous la propriété **Abonnement** .

   * **Pour Android**

     ![](assets/push-config-3.png)

      1. Fournissez les **[!UICONTROL ID de l’application (nom du package Android)]**. En règle générale, le nom du module est l’ID d’application dans votre `build.gradle` fichier .

      1. Basculer **[!UICONTROL Informations d’identification push]** pour ajouter vos informations d’identification.

      1. Faites glisser et déposez les informations d’identification push FCM. Pour plus d’informations sur la manière d’obtenir les informations d’identification push, reportez-vous à la section [Documentation Google](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

1. Cliquez sur **[!UICONTROL Enregistrer]** pour créer la configuration de votre application.

## Configuration des paramètres de votre application dans Adobe Campaign{#push-config-campaign}

### Création d’un service {#create-service}

Avant d’envoyer des notifications push, vous devez définir les paramètres de vos applications iOS et Android dans Adobe Campaign.

Les notifications push sont envoyées aux utilisateurs et utilisatrices de votre application par le biais d’un service dédié. Lorsque les utilisateurs et utilisatrices installent votre application, ils s’abonnent à ce service : Adobe Campaign s’appuie sur ce service pour cibler uniquement les abonné(e)s de votre application. Dans ce service, vous devez ajouter vos applications iOS et Android à envoyer sur les appareils iOS et Android.

Pour créer un service destiné à envoyer des notifications push, procédez comme suit :

1. Accédez à l’onglet **[!UICONTROL Profils et cibles > Services et abonnements]**, puis cliquez sur **[!UICONTROL Créer]**.

   ![](assets/push-config-4.png){width="800" align="left"}

1. Saisissez un **[!UICONTROL Libellé]** et un **[!UICONTROL Nom interne]**, puis sélectionnez un type d’**[!UICONTROL Application mobile]**. 

   >[!NOTE]
   >
   >Le mapping de ciblage par défaut **[!UICONTROL Applications abonnées (nms:appSubscriptionRcp)]** est lié à la table des destinataires. Si vous souhaitez utiliser un autre mapping de ciblage, vous devez en créer un nouveau et le renseigner dans le champ **[!UICONTROL Mapping de ciblage]** du service. Pour plus d’informations sur les mappings de ciblage, consultez [cette page](../audiences/target-mappings.md).

1. Ensuite, utilisez l’icône **[!UICONTROL Ajouter]** sur la droite pour définir les applications mobiles qui utilisent ce service.

   ![](assets/push-config-5.png)

### Créer une application mobile {#create-sapp}

Après avoir créé votre service, vous devez maintenant définir les applications mobiles qui utiliseront ce service.

>[!BEGINTABS]

>[!TAB iOS]

Pour créer une application pour les appareils iOS, procédez comme suit :

1. Dans votre service, cliquez sur **[!UICONTROL Ajouter]** puis sélectionnez **[!UICONTROL Création d’une application iOS]**. Cliquez sur **[!UICONTROL Suivant]**.

   ![](assets/push-config-6.png)

1. Dans la **[!UICONTROL Lancement de la liste des configurations d’application]** , sélectionnez la surface de l&#39;application créée précédemment dans cette section. Cliquez sur **[!UICONTROL Suivant]**.

   ![](assets/push-config-7.png)

1. (facultatif) Vous pouvez enrichir le contenu d’un message push avec certaines **[!UICONTROL variables d’application]**. Elles sont entièrement personnalisables et font partie de la payload du message envoyé à l&#39;appareil mobile.

   Dans l’exemple ci-dessous, la variable **mediaURl** et **mediaExt** sont ajoutées pour créer une notification push enrichie, puis fournissent à l’application l’image à afficher dans la notification.

   ![](assets/push-config-8.png)

1. Accédez à l’onglet **[!UICONTROL Paramètres d’abonnement]** pour définir le mapping avec une extension du schéma **[!UICONTROL Applications abonnées (nms:appsubscriptionRcp)]**.

1. Accédez à l’onglet **[!UICONTROL Sons]** pour définir un son à lire. Cliquez sur **[!UICONTROL Ajouter]** et renseignez le champ **[!UICONTROL Nom interne]**. Il doit contenir le nom du fichier incorporé dans l’application ou le nom du son système.

1. Cliquez sur **[!UICONTROL Suivant]** pour passer à la configuration de l’application de développement.

1. Le **[!UICONTROL Clé d’intégration]** est spécifique à chaque application. Il relie l’application mobile à Adobe Campaign et sera utilisé lors de la configuration de l’extension Campaign.

   Assurez-vous que la même **[!UICONTROL clé d’intégration]** est définie dans Adobe Campaign et dans le code de l’application via le SDK.

   Pour en savoir plus, consultez la [documentation pour les développeurs et développeuses](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}.


   >[!NOTE]
   >
   > La **[!UICONTROL clé d&#39;intégration]** est entièrement personnalisable avec une valeur de chaîne, mais doit être exactement identique à celle spécifiée dans le SDK.
   >
   > Vous ne pouvez pas utiliser le même certificat pour la version de développement (sandbox) et la version de production de l’application.

   ![](assets/push-config-9.png)

1. Sélectionnez l’icône dans le champ **[!UICONTROL Icône de l’application]** pour personnaliser l’application mobile dans votre service.

1. Cliquez sur **[!UICONTROL Suivant]** pour passer à la configuration de l’application de production et procédez comme décrit ci-dessus. Notez que vous ne pouvez pas utiliser la même **[!UICONTROL Clé d’intégration]** pour la version de développement (sandbox) et la version de production de l’application.

1. Cliquez sur **[!UICONTROL Terminer]**.

Votre application iOS est maintenant prête à être utilisée dans Campaign.

>[!TAB Android]

Pour créer une application pour les appareils Android, procédez comme suit :

1. Dans votre service, cliquez sur **[!UICONTROL Ajouter]** puis sélectionnez **[!UICONTROL Création d’une application Android]**. Cliquez sur **[!UICONTROL Suivant]**.

   ![](assets/push-config-10.png)

1. Dans la **[!UICONTROL Lancement de la liste des configurations d’application]** , sélectionnez la surface de l’application créée dans cette section et cliquez sur **[!UICONTROL Suivant]**.

   ![](assets/push-config-11.png)

1. La clé d’intégration est spécifique à chaque application. Il relie l’application mobile à Adobe Campaign et sera utilisé lors de la configuration de l’extension Campaign.

   Assurez-vous que la même **[!UICONTROL clé d’intégration]** est définie dans Adobe Campaign et dans le code de l’application via le SDK.

   Pour en savoir plus, consultez la [documentation pour les développeurs et développeuses](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configuration-keys){target="_blank"}.

   >[!NOTE]
   >
   > La **[!UICONTROL clé d&#39;intégration]** est entièrement personnalisable avec une valeur de chaîne, mais doit être exactement identique à celle spécifiée dans le SDK.

   ![](assets/push-config-12.png)

1. Sélectionnez l’icône dans le champ **[!UICONTROL Icône de l’application]** pour personnaliser l’application mobile dans votre service.

1. (facultatif) Vous pouvez, si nécessaire, enrichir le contenu d&#39;un message push avec certaines **[!UICONTROL variables d’application]**. Elles sont entièrement personnalisables et font partie de la payload du message envoyé à l&#39;appareil mobile.

1. Accédez à l’onglet **[!UICONTROL Paramètres d’abonnement]** pour définir le mapping avec une extension du schéma **[!UICONTROL Applications abonnées (nms:appsubscriptionRcp)]**.

1. Cliquez sur **[!UICONTROL Terminer]**, puis sur **[!UICONTROL Enregistrer]**.

Votre application Android est maintenant prête à être utilisée dans Campaign.

>[!ENDTABS]

Vous trouverez ci-dessous les noms de payload FCM pour personnaliser davantage votre notification push :

| Type de message | Élément de message configurable (nom de payload FCM) | Options configurables (nom de payload FCM) |
|:-:|:-:|:-:|
| Message de données | N/A | validate_only |
| Message de notification | title, body, android_channel_id, icon, sound, tag, color, click_action, image, ticker, sticky, visibility, notification_priority, notification_count <br> | validate_only |

## Configuration d’une propriété mobile dans la collecte de données Adobe Experience Platform {#create-mobile-property}

1. Sur la page d’accueil de la collecte de données, accédez au menu Balises .

1. Cliquez sur **[!UICONTROL Nouvelle propriété]**.

   ![](assets/push-config-13.png)

1. Saisissez le nom de la propriété et sélectionnez **[!UICONTROL Mobile]** comme plateforme.

   ![](assets/push-config-14.png)

1. Cliquez sur **[!UICONTROL Enregistrer]** pour créer la propriété mobile.

1. Accédez à la propriété mobile que vous venez de créer.

1. Dans le tableau de bord de vos propriétés mobiles, accédez à la **[!UICONTROL Extensions]** puis le menu **[!UICONTROL Catalogue]** .

   ![](assets/push-config-15.png)

1. Installez le **[!DNL Adobe Campaign Classic]** extension . [En savoir plus sur l&#39;extension Campaign](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#configure-campaign-classic-extension)

   ![](assets/push-config-16.png)

1. Renseignez les détails de votre instance :

   * **[!UICONTROL Point de terminaison d’enregistrement]** ou **[!UICONTROL Point de terminaison de suivi]** Les URL se trouvent dans la variable **[!UICONTROL Outils]** > **[!UICONTROL Avancé]** > **[!UICONTROL Assistant de déploiement]** dans Campaign.
   * **[!UICONTROL Clés d’intégration]** se trouve dans l’application mobile configurée dans [cette section](#create-app).

   ![](assets/push-config-17.png)

1. Cliquez sur **[!UICONTROL Enregistrer]**.

1. Vous devez maintenant publier la configuration à partir du **[!UICONTROL Flux de publication]** . [En savoir plus](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/#publish-the-configuration).

Votre propriété mobile sera désormais automatiquement synchronisée avec la variable **[!UICONTROL Collecte de données Adobe Experience Platform]** workflow technique. [En savoir plus](../../automation/workflow/technical-workflows.md#list-technical-workflows).

## Ajouter un Campaign Classic à votre application mobile {#campaign-mobile-app}

Le SDK mobile Adobe Experience Platform permet d’optimiser les solutions et services Experience Cloud d’Adobe dans vos applications mobiles. La configuration des SDK s’effectue dans l’interface utilisateur de collecte de données, qui offre des options de configuration flexibles et des intégrations extensibles basées sur des règles.

[En savoir plus dans la documentation Adobe Developer](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#add-campaign-classic-to-your-app){target="_blank"}.

## Créer votre notification push{#push-create}

Une fois que vous avez correctement configuré votre application mobile dans la collecte de données, vous pouvez désormais créer et envoyer des notifications push dans Adobe Campaign.

Voir [cette page](push.md#push-create) pour les éléments détaillés spécifiques à la diffusion des notifications iOS et Android.
