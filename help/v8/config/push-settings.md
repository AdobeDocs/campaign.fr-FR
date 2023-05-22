---
title: Intégrer le SDK AEP et Campaign
description: Découvrez comment intégrer le SDK mobile Adobe Experience Platform à votre application.
version: v8
feature: Push
role: Admin, Developer
level: Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: ff6990f3db1122670bff4919f417b9f9f04d3183
workflow-type: ht
source-wordcount: '983'
ht-degree: 100%

---


# SDK AEP + Campaign : configurer le canal de notification push {#push-notification-configuration}

Avant de commencer à envoyer des notifications push avec Adobe Campaign, vous devez vous assurer que les configurations et les intégrations sont en place sur l’application mobile et pour les balises dans Adobe Experience Platform.

Le SDK mobile Adobe Experience Platform fournit des API d’intégration côté client pour vos mobiles via les SDK compatibles Android et iOS.

Pour configurer votre application avec des SDK mobiles Adobe Experience Platform, procédez comme suit :

1. Vérifiez les [conditions préalables](#before-starting).
1. Configurez une [propriété de balise mobile](#launch-property) dans la collecte de données Adobe Experience Platform.
1. Obtenez le SDK mobile Adobe Experience Platform, comme expliqué [sur cette page](https://developer.adobe.com/client-sdks/documentation/getting-started/get-the-sdk/){target="_blank"}.
1. (facultatif) Activez la journalisation et les mesures de cycle de vie, comme expliqué [sur cette page](https://developer.adobe.com/client-sdks/documentation/getting-started/enable-debug-logging/){target="_blank"}.
1. (facultatif) Ajoutez [Adobe Experience Platform Assurance dans votre application](https://developer.adobe.com/client-sdks/documentation/getting-started/validate/){target="_blank"} to validate your implementation. Learn how to implement Adobe Experience Platform Assurance extension [in this page](https://developer.adobe.com/client-sdks/documentation/platform-assurance-sdk/){target="_blank"}.
1. Suivez la [documentation du SDK mobile Adobe Experience Platform](https://developer.adobe.com/client-sdks/documentation/getting-started/){target="_blank"} pour obtenir une configuration avec les SDK mobiles Adobe Experience Platform dans votre application.
1. Installez et configurez l’[extension Adobe Campaign](#configure-extension) dans votre propriété mobile.
1. Configurez vos services mobiles iOS et Android dans Adobe Campaign, comme expliqué [sur cette page](../send/push.md#push-config).


## Conditions préalables {#before-starting}

### Configurer les autorisations {#setup-permissions}

Avant de créer une application mobile, vous devez vous assurer que vous disposez ou attribuez des autorisations utilisateur/utilisatrice appropriées pour les balises dans Adobe Experience Platform. Les autorisations utilisateur/utilisatrice pour les balises dans Adobe Experience Platform sont attribuées aux utilisateurs et utilisatrices via Adobe Admin Console. Pour en savoir plus, consultez la [documentation sur les balises](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/user-permissions.html?lang=fr){target="_blank"}.

>[!CAUTION]
>
>La configuration des notifications push doit être effectuée par un utilisateur ou une utilisatrice expert(e). Selon votre modèle de mise en œuvre et les personnes impliquées dans celle-ci, vous devrez peut-être attribuer l’ensemble des autorisations à un profil de produit unique ou partager les autorisations entre le développeur/la développeuse de l’application et l’administrateur ou l’administratrice **Adobe Campaign**.

Pour attribuer des droits **Propriété** et **Entreprise**, procédez comme suit :

1. Accédez à l’**[!DNL Admin Console]**.
1. Dans l’onglet **[!UICONTROL Produits]**, sélectionnez la vignette **[!UICONTROL Collecte de données Adobe Experience Platform]**.
1. Sélectionnez un **[!UICONTROL Profil de produit]** ou créez-en un à l’aide du bouton **[!UICONTROL Nouveau profil]**. Découvrez comment créer un **[!UICONTROL Nouveau profil]** dans la [documentation d’Admin Console](https://experienceleague.adobe.com/docs/experience-platform/access-control/ui/create-profile.html?lang=fr#ui){target="_blank"}.
1. Dans l’onglet **[!UICONTROL Autorisations]**, sélectionnez **[!UICONTROL Droits de propriété]**.
1. Cliquez sur **[!UICONTROL Tout ajouter]**. Vous ajouterez ainsi les droits suivants à votre profil de produit :
   * **[!UICONTROL Approuver]**
   * **[!UICONTROL Développer]**
   * **[!UICONTROL Modifier la propriété]**
   * **[!UICONTROL Gérer les environnements]**
   * **[!UICONTROL Gérer les extensions]**
   * **[!UICONTROL Publier]**

   Ces autorisations sont requises pour installer et publier l’extension Adobe Campaign et publier la propriété de l’application dans le **SDK mobile Adobe Experience Platform**.

1. Sélectionnez ensuite **[!UICONTROL Droits d’entreprise]** dans le menu de gauche.
1. Ajoutez les droits suivants :

   * **[!UICONTROL Gérer les configurations d’application]**
   * **[!UICONTROL Gérer les propriétés]**

   Ces autorisations sont requises pour que le développeur/la développeuse d’applications mobiles configure les informations d’identification des notifications push dans **Collecte de données Adobe Experience Platform**.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

Pour affecter un **[!UICONTROL Profil de produit]** aux utilisateurs et utilisatrices, procédez comme suit :

1. Accédez à l’**[!DNL Admin Console]**.
1. Dans l’onglet **[!UICONTROL Produits]**, sélectionnez la vignette **[!UICONTROL Collecte de données Adobe Experience Platform]**.
1. Sélectionnez le **[!UICONTROL profil de produit]** précédemment configuré.
1. Dans l’onglet **[!UICONTROL Utilisateurs]**, cliquez sur **[!UICONTROL Ajouter un utilisateur]**.
1. Saisissez le nom ou l’adresse e-mail de la personne, puis sélectionnez-la. Cliquez ensuite sur **[!UICONTROL Enregistrer]**.

   >[!NOTE]
   >
   >Si la personne n’a pas été créée auparavant dans l’Admin Console, reportez-vous à la documentation [Ajouter des utilisateurs](https://helpx.adobe.com/fr/enterprise/using/manage-users-individually.html#add-users){target="_blank"}.

### Configurer votre application {#configure-app}

La configuration technique implique une collaboration étroite entre le développeur/la développeuse de l’application et l’administrateur/l’administratrice de l’entreprise. Avant de commencer à envoyer des notifications push avec [!DNL Adobe Campaign], vous devez définir les paramètres dans [!DNL Adobe Experience Platform Data Collection] et intégrer votre application mobile aux SDK mobiles Adobe Experience Platform.

Suivez les étapes de mise en œuvre présentées dans les liens ci-dessous :

* Pour **Apple iOS** : découvrez comment enregistrer votre application avec des APNS dans la [documentation Apple](https://developer.apple.com/documentation/usernotifications/registering_your_app_with_apns){target="_blank"}.
* Pour **Google Android** : découvrez comment configurer une application cliente Firebase Cloud Messaging sur Android dans la [documentation Google](https://firebase.google.com/docs/cloud-messaging/android/client){target="_blank"}.

<!--
## Add your app push credentials in Adobe Experience Platform Data Collection {#push-credentials}

After granting the correct user permissions, you now need to add your mobile application push credentials in Adobe Experience Platform Data Collection. 

The mobile app push credential registration is required to authorize Adobe to send push notifications on your behalf. Refer to the steps detailed below:

1. From [!DNL Adobe Experience Platform Data Collection], browse to **[!UICONTROL App Surfaces]** in the left rail.

1. Click **[!UICONTROL Create App Surface]** to create a new configuration.

1. Enter a **[!UICONTROL Name]** for the configuration.

1. From **[!UICONTROL Mobile Application Configuration]**, select the system and enter settings.

    * **For iOS**

        1. Enter the mobile app **Bundle Id** in the **[!UICONTROL App ID (iOS Bundle ID)]** field. The app Bundle ID can be found in the **General** tab of the primary target in **XCode**.
        
        1. Switched on the **[!UICONTROL Push Credentials]** button to add your credentials.
        
        1. Drag and drop your .p8 Apple Push Notification Authentication Key file. This key can be acquired from the **Certificates**, **Identifiers** and **Profiles** page.

        1. Provide the **Key ID**. This is a 10 character string assigned during the creation of p8 auth key. It can be found under **Keys** tab in **Certificates**, **Identifiers** and **Profiles** page.
        
        1. Provide the **Team ID**. This is a string value which can be found under the Membership tab.

    * **For Android**

        1. Provide the **[!UICONTROL App ID (Android package name)]**: usually the package name is the app id in your `build.gradle` file.

        1. Switched on the **[!UICONTROL Push Credentials]** button to add your credentials.

        1. Drag and drop the FCM push credentials. For more details on how to get the push credentials refer to [Google Documentation](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.
    

1. Click **[!UICONTROL Save]** to create your app configuration.
-->

## Configurer une propriété de balise mobile dans la collecte de données Adobe Experience Platform {#launch-property}

La configuration d’une propriété mobile permet aux développeurs et développeuses d’applications mobiles ou aux spécialistes du marketing de configurer les SDK mobiles. En règle générale, vous créez une propriété mobile pour chaque application mobile que vous souhaitez gérer. Découvrez comment créer et configurer une propriété mobile dans la [documentation du SDK mobile Adobe Experience Platform](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}.
<!--
To get the SDKs needed for push notification to work you will need the following SDK extensions, for both Android and iOS:

* **[!UICONTROL Mobile Core]** (installed automatically)
* **[!UICONTROL Profile]** (installed automatically)
* **[!UICONTROL Adobe Experience Platform Edge]**
* **[!UICONTROL Adobe Experience Platform Assurance]**, optional but recommended to debug the mobile implementation.
-->

Pour en savoir plus sur les balises [!DNL Adobe Experience Platform Data Collection], consultez la [documentation Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/initial-configuration/configure-tags.html?lang=fr){target="_blank"}.

Une fois créée, ouvrez la nouvelle propriété de balise et créez une bibliothèque. Pour cela :

1. Accédez à **Flux de publication** dans le volet de navigation de gauche, puis sélectionnez **Ajouter une bibliothèque**.
1. Saisissez le nom de la bibliothèque et sélectionnez l’environnement.
1. Sélectionnez **Ajouter toutes les ressources modifiées**, puis **Enregistrement et création en vue du développement**.
1. Enfin, définissez cette bibliothèque comme votre bibliothèque de travail en cliquant sur le bouton **Sélectionner une bibliothèque de travail**.


## Configurer l’extension Adobe Campaign dans votre propriété mobile {#configure-extension}

L’**Extension Adobe Campaign Classic** pour les SDK mobiles Adobe Experience Platform alimente les notifications push de vos applications mobiles. Elle vous aide à collecter des jetons push utilisateur et à gérer la mesure des interactions avec les services Adobe Experience Platform.

Cette extension, qui s’applique à la fois à Campaign Classic v7 et Campaign v8, est préinstallée sur votre environnement et doit être configurée. Pour configurer l’extension de votre propriété de balise mobile, procédez comme suit :

1. Ouvrez la propriété de balise que vous avez créée précédemment.
1. Dans le volet de navigation de gauche, accédez à **Extensions**, puis ouvrez l’onglet **Catalogue**. Utilisez le champ de recherche pour rechercher l’extension **Adobe Campaign Classic**.
1. Dans la vignette Campaign Classic, cliquez sur le bouton **Installer**.
1. Saisissez les paramètres comme décrit dans la [documentation du SDK mobile Adobe Experience Platform](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/){target="_blank"}.

Vous pouvez maintenant ajouter Campaign à votre application, comme indiqué dans la [documentation du SDK mobile Adobe Experience Platform](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#add-campaign-classic-to-your-app){target="_blank"}.

## Configurer vos services mobiles dans Campaign{#push-service}

Une fois votre application mobile configurée dans [!DNL Adobe Experience Platform Data Collection], vous devez créer deux services (un pour les appareils iOS et un pour les appareils Android) pour pouvoir envoyer des notifications push depuis **[!DNL Adobe Campaign]**.

Découvrez comment créer et configurer un service pour les notifications push iOS et Android dans [cette section](../send/push.md#push-config).
