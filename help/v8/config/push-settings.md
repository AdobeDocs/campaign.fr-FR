---
title: Intégration du SDK AEP et de Campaign
description: Découvrez comment intégrer le SDK mobile Adobe Experience Platform à votre application
version: v8
feature: Push
role: Admin, Developer
level: Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: ff6990f3db1122670bff4919f417b9f9f04d3183
workflow-type: tm+mt
source-wordcount: '983'
ht-degree: 3%

---


# SDK AEP + Campaign : configurer le canal de notification push {#push-notification-configuration}

Avant de commencer à envoyer des notifications push avec Adobe Campaign, vous devez vous assurer que les configurations et les intégrations sont en place sur l’application mobile et pour les balises dans Adobe Experience Platform.

Le SDK Mobile Adobe Experience Platform fournit des API d’intégration côté client pour vos mobiles via les SDK compatibles Android et iOS.

Pour configurer votre application avec des SDK Adobe Experience Platform Mobile, procédez comme suit :

1. Vérifier [conditions préalables](#before-starting).
1. Configurez une [propriété de balise mobile](#launch-property) dans la collecte de données Adobe Experience Platform.
1. Obtention du SDK Mobile Adobe Experience Platform en tant que détaillé [dans cette page](https://developer.adobe.com/client-sdks/documentation/getting-started/get-the-sdk/){target="_blank"}.
1. (facultatif) Activez les mesures de journalisation et de cycle de vie, comme indiqué [dans cette page](https://developer.adobe.com/client-sdks/documentation/getting-started/enable-debug-logging/){target="_blank"}.
1. (facultatif) Ajouter [Adobe Experience Platform Assurance sur votre application](https://developer.adobe.com/client-sdks/documentation/getting-started/validate/){target="_blank"} to validate your implementation. Learn how to implement Adobe Experience Platform Assurance extension [in this page](https://developer.adobe.com/client-sdks/documentation/platform-assurance-sdk/){target="_blank"}.
1. Suivez [Documentation du SDK Mobile Adobe Experience Platform](https://developer.adobe.com/client-sdks/documentation/getting-started/){target="_blank"} pour obtenir une configuration avec les SDK mobiles Adobe Experience Platform dans votre application.
1. Installation et configuration [Extension Adobe Campaign](#configure-extension) dans votre propriété mobile.
1. Configurez vos services mobiles iOS et Android dans Adobe Campaign comme indiqué [dans cette page](../send/push.md#push-config).


## Conditions préalables {#before-starting}

### Configuration des autorisations {#setup-permissions}

Avant de créer une application mobile, vous devez vous assurer de disposer ou d’attribuer les autorisations utilisateur appropriées pour les balises dans Adobe Experience Platform. Les autorisations utilisateur des balises dans Adobe Experience Platform sont attribuées aux utilisateurs via Adobe Admin Console. En savoir plus dans [Documentation sur les balises](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/user-permissions.html){target="_blank"}.

>[!CAUTION]
>
>La configuration push doit être effectuée par un utilisateur expert. Selon votre modèle de mise en oeuvre et les personnes impliquées dans cette mise en oeuvre, vous devrez peut-être attribuer l’ensemble des autorisations à un profil de produit unique ou partager les autorisations entre le développeur de l’application et le **Adobe Campaign** administrateur.

Pour affecter **Propriété** et **Société** droits, procédez comme suit :

1. Accédez au **[!DNL Admin Console]**.
1. Dans la **[!UICONTROL Produits]** , sélectionnez la variable **[!UICONTROL Collecte de données Adobe Experience Platform]** carte.
1. Sélectionner un **[!UICONTROL Profil de produits]** ou créez-en un à l’aide de la fonction **[!UICONTROL Nouveau profil]** bouton . Découvrez comment créer une **[!UICONTROL Nouveau profil]** dans le [Documentation de la console d’administration](https://experienceleague.adobe.com/docs/experience-platform/access-control/ui/create-profile.html#ui){target="_blank"}.
1. Dans la **[!UICONTROL Autorisations]** onglet, sélectionnez **[!UICONTROL Droits de propriété]**.
1. Cliquez sur **[!UICONTROL Tout ajouter]**. Vous ajouterez ainsi les droits suivants à votre profil de produit :
   * **[!UICONTROL Approuver]**
   * **[!UICONTROL Développer]**
   * **[!UICONTROL Modifier la propriété]**
   * **[!UICONTROL Gestion des environnements]**
   * **[!UICONTROL Gestion des extensions]**
   * **[!UICONTROL Publier]**

   Ces autorisations sont requises pour installer et publier l’extension Adobe Campaign et publier la propriété de l’application dans **SDK Adobe Experience Platform Mobile**.

1. Sélectionnez ensuite **[!UICONTROL Droits d’entreprise]** dans le menu de gauche.
1. Ajoutez les droits suivants :

   * **[!UICONTROL Gestion des configurations d’application]**
   * **[!UICONTROL Gestion des propriétés]**

   Ces autorisations sont requises pour que le développeur d’applications mobiles configure les informations d’identification push dans **Collecte de données Adobe Experience Platform**.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

Pour affecter **[!UICONTROL Profil de produit]** pour les utilisateurs, procédez comme suit :

1. Accédez au **[!DNL Admin Console]**.
1. Dans la **[!UICONTROL Produits]** , sélectionnez la variable **[!UICONTROL Collecte de données Adobe Experience Platform]** carte.
1. Sélectionnez votre **[!UICONTROL Profil de produit]**.
1. Dans la **[!UICONTROL Utilisateurs]** , cliquez sur **[!UICONTROL Ajouter un utilisateur]**.
1. Saisissez le nom ou l’adresse électronique de votre utilisateur, puis sélectionnez-le. Cliquez ensuite sur **[!UICONTROL Enregistrer]**.

   >[!NOTE]
   >
   >Si l’utilisateur n’a pas été créé auparavant dans la console d’administration, reportez-vous à la section [Ajout de la documentation sur les utilisateurs](https://helpx.adobe.com/enterprise/using/manage-users-individually.html#add-users){target="_blank"}.

### Configuration de votre application {#configure-app}

La configuration technique implique une collaboration étroite entre le développeur de l’application et l’administrateur de l’entreprise. Avant de commencer à envoyer des notifications push avec [!DNL Adobe Campaign], vous devez définir les paramètres dans [!DNL Adobe Experience Platform Data Collection] et intégrer votre application mobile avec les SDK mobiles Adobe Experience Platform.

Suivez les étapes de mise en oeuvre présentées dans les liens ci-dessous :

* Pour **Apple iOS**: Découvrez comment enregistrer votre application avec des APNS dans [Documentation Apple](https://developer.apple.com/documentation/usernotifications/registering_your_app_with_apns){target="_blank"}
* Pour **Google Android**: Découvrez comment configurer une application cliente Firebase Cloud Messaging sur Android dans [Documentation Google](https://firebase.google.com/docs/cloud-messaging/android/client){target="_blank"}

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

## Configuration d’une propriété de balise mobile dans la collecte de données Adobe Experience Platform {#launch-property}

La configuration d’une propriété mobile permet au développeur d’applications mobiles ou au marketeur de configurer les SDK mobiles. En règle générale, vous créez une propriété mobile pour chaque application mobile que vous souhaitez gérer. Découvrez comment créer et configurer une propriété mobile dans [Documentation du SDK Mobile Adobe Experience Platform](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}.
<!--
To get the SDKs needed for push notification to work you will need the following SDK extensions, for both Android and iOS:

* **[!UICONTROL Mobile Core]** (installed automatically)
* **[!UICONTROL Profile]** (installed automatically)
* **[!UICONTROL Adobe Experience Platform Edge]**
* **[!UICONTROL Adobe Experience Platform Assurance]**, optional but recommended to debug the mobile implementation.
-->

En savoir plus sur [!DNL Adobe Experience Platform Data Collection] balises dans [Documentation Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/initial-configuration/configure-tags.html){target="_blank"}.

Une fois créée, ouvrez la nouvelle propriété de balise et créez une bibliothèque. Pour cela :

1. Accédez à **Flux de publication** dans le volet de navigation de gauche, puis sélectionnez **Ajouter une bibliothèque**.
1. Saisissez le nom de la bibliothèque et sélectionnez l’environnement.
1. Sélectionner **Ajouter toutes les ressources modifiées**, et **Enregistrement et création en vue du développement**.
1. Enfin, définissez cette bibliothèque comme votre bibliothèque de travail à partir de la **Sélectionner une bibliothèque de travail** bouton .


## Configuration de l’extension Adobe Campaign dans votre propriété mobile {#configure-extension}

Le **Extension Adobe Campaign Classic** Les SDK Adobe Experience Platform Mobile alimentent les notifications push pour vos applications mobiles et vous aident à collecter des jetons push utilisateur et à gérer la mesure des interactions avec les services Adobe Experience Platform.

Cette extension, qui s&#39;applique à la fois à Campaign Classic v7 et Campaign v8, est préinstallée sur votre environnement et doit être configurée. Pour configurer l’extension de votre propriété de balise mobile, procédez comme suit :

1. Ouvrez la propriété de balise que vous avez créée précédemment.
1. Dans le volet de navigation de gauche, accédez à **Extensions**, puis ouvrez le **Catalogue** . Utilisez le champ de recherche pour rechercher la variable **Adobe Campaign Classic** extension .
1. Dans la carte du Campaign Classic, cliquez sur le **Installer** bouton .
1. Saisissez les paramètres comme décrit dans la section [Documentation du SDK Mobile Adobe Experience Platform](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/){target="_blank"}.

Vous pouvez maintenant ajouter Campaign à votre application, comme indiqué dans la section  [Documentation du SDK Mobile Adobe Experience Platform](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#add-campaign-classic-to-your-app){target="_blank"}.

## Configuration de vos services mobiles dans Campaign{#push-service}

Une fois votre application mobile configurée dans [!DNL Adobe Experience Platform Data Collection], vous devez créer deux services (un pour les appareils iOS, un pour les appareils Android) pour pouvoir envoyer des notifications push depuis **[!DNL Adobe Campaign]**.

Découvrez comment créer et configurer un service pour les notifications push iOS et Android dans [cette section](../send/push.md#push-config).
