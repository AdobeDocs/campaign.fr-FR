---
title: Intégration du SDK AEP et de Campaign
description: Découvrez comment intégrer le SDK mobile Adobe Experience Platform à votre application
version: v8
feature: Push
role: Admin, Developer
level: Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: e3ea361cc486096fe6c19ac469e8a71b636371ac
workflow-type: tm+mt
source-wordcount: '1263'
ht-degree: 3%

---


# SDK AEP + Campaign : configurer le canal de notification push {#push-notification-configuration}

Avant de commencer à envoyer des notifications push avec Adobe Campaign, vous devez vous assurer que les configurations et les intégrations sont en place sur l’application mobile et pour les balises dans Adobe Experience Platform.... .... ....


## Avant de commencer {#before-starting}

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

### Intégration de votre application mobile avec le SDK Adobe Experience Platform {#integrate-mobile-app}

Le SDK Mobile Adobe Experience Platform fournit des API d’intégration côté client pour vos mobiles via les SDK compatibles Android et iOS. Suivez [Documentation du SDK Mobile Adobe Experience Platform](https://developer.adobe.com/client-sdks/documentation/getting-started/){target="_blank"} pour obtenir une configuration avec les SDK mobiles Adobe Experience Platform dans votre application.

À la fin de cette période, vous devez également avoir créé et configuré une propriété mobile dans [!DNL Adobe Experience Platform Data Collection]. En règle générale, vous créez une propriété mobile pour chaque application mobile que vous souhaitez gérer. Découvrez comment créer et configurer une propriété mobile dans [Documentation du SDK Mobile Adobe Experience Platform](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}.


## Étape 1 : Ajout des informations d’identification push de votre application dans la collecte de données Adobe Experience Platform {#push-credentials}

Après avoir accordé les autorisations utilisateur appropriées, vous devez maintenant ajouter les informations d’identification push de votre application mobile dans la collecte de données Adobe Experience Platform.

L’enregistrement des informations d’identification push de l’application mobile est nécessaire pour autoriser Adobe à envoyer des notifications push en votre nom. Reportez-vous aux étapes détaillées ci-dessous :

1. De [!DNL Adobe Experience Platform Data Collection], accédez à **[!UICONTROL Surfaces de l’application]** dans le rail de gauche.

1. Cliquez sur **[!UICONTROL Créer une surface d’application]** pour créer une configuration.

1. Saisissez un **[!UICONTROL Nom]** pour la configuration.

1. De **[!UICONTROL Configuration des applications mobiles]**, sélectionnez Système opérationnel :

   * **Pour iOS**

      1. Saisie de l’application mobile **Bundle Id** dans le **[!UICONTROL ID d’application (ID de bundle iOS)]** champ . L’ID de bundle d’application se trouve dans la variable **Général** de la cible Principale dans **XCode**.

      1. Activé **[!UICONTROL Informations d’identification push]** pour ajouter vos informations d’identification.

      1. Faites glisser et déposez votre fichier de clé d’authentification de notification push Apple .p8. Cette clé peut être acquise à partir de la fonction **Certificats**, **Identificateurs** et **Profils** page.

      1. Fournissez les **ID de clé**. Chaîne de 10 caractères attribuée lors de la création de la clé d’authentification p8. Il se trouve sous **Clés** dans **Certificats**, **Identificateurs** et **Profils** page.

      1. Fournissez les **Identifiant de l’équipe**. Il s’agit d’une valeur de chaîne qui se trouve sous l’onglet Appartenance .
   * **Pour Android**

      1. Fournissez les **[!UICONTROL ID de l’application (nom du package Android)]**: généralement, le nom du module correspond à l’ID d’application dans votre `build.gradle` fichier .

      1. Activé **[!UICONTROL Informations d’identification push]** pour ajouter vos informations d’identification.

      1. Faites glisser et déposez les informations d’identification push FCM. Pour plus d’informations sur la manière d’obtenir les informations d’identification push, reportez-vous à la section [Documentation Google](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.



1. Cliquez sur **[!UICONTROL Enregistrer]** pour créer la configuration de votre application.


## Étape 2 : Configuration d’une propriété de balise mobile dans la collecte de données Adobe Experience Platform {#launch-property}

La configuration d’une propriété mobile permet au développeur d’applications mobiles ou au marketeur de configurer les attributs des SDK mobiles, tels que les délais d’expiration de session, la variable [!DNL Adobe Experience Platform] environnement de test à cibler et la variable **[!UICONTROL Jeux de données Adobe Experience Platform]** à utiliser pour que le SDK mobile envoie des données.

Pour plus de détails et de procédures sur la configuration d’un **propriété mobile** , reportez-vous aux étapes détaillées dans la section [Documentation du SDK Mobile Adobe Experience Platform](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/){target="_blank"}.

Pour que les SDK nécessaires pour que la notification push fonctionne, vous aurez besoin des extensions SDK suivantes, pour Android et iOS :

* **[!UICONTROL Mobile Core]** (installé automatiquement)
* **[!UICONTROL Profil]** (installé automatiquement)
* **[!UICONTROL Adobe Experience Platform Edge]**
* **[!UICONTROL Adobe Experience Platform Assurance]**, facultatif mais recommandé pour déboguer l’implémentation mobile.

En savoir plus sur [!DNL Adobe Experience Platform Data Collection] balises dans [Documentation Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/initial-configuration/configure-tags.html){target="_blank"}.

Une fois créée, ouvrez la nouvelle propriété de balise et créez une bibliothèque. Pour cela :

1. Accédez à **Flux de publication** dans le volet de navigation de gauche, puis sélectionnez **Ajouter une bibliothèque**.
1. Saisissez le nom de la bibliothèque et sélectionnez l’environnement.
1. Sélectionner **Ajouter toutes les ressources modifiées**, et **Enregistrement et création en vue du développement**.
1. Enfin, définissez cette bibliothèque comme votre bibliothèque de travail à partir de la **Sélectionner une bibliothèque de travail** bouton .


## Étape 3 : Configuration de l’extension Adobe Campaign dans votre propriété mobile {#configure-extension}

Le **Extension Adobe Campaign Classic** Les SDK Adobe Experience Platform Mobile alimentent les notifications push pour vos applications mobiles et vous aident à collecter des jetons push utilisateur et à gérer la mesure des interactions avec les services Adobe Experience Platform.

Cette extension est préinstallée sur votre environnement et doit être configurée. Pour configurer l’extension de votre propriété de balise mobile, procédez comme suit :

1. Ouvrez la propriété de balise que vous avez créée précédemment.
1. Dans le volet de navigation de gauche, accédez à **Extensions**, puis ouvrez le **Catalogue** . Utilisez le champ de recherche pour rechercher la variable **Adobe Campaign Classic** extension .
1. Dans la carte du Campaign Classic, cliquez sur le **Installer** bouton .
1. Saisissez les paramètres comme décrit dans la section [Documentation du SDK Mobile Adobe Experience Platform](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/){target="_blank"}.

Vous pouvez maintenant ajouter Campaign à votre application, comme indiqué dans la section  [Documentation du SDK Mobile Adobe Experience Platform](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-classic/#add-campaign-classic-to-your-app){target="_blank"}.

## Étape 4 : Configuration de vos services mobiles dans Campaign{#push-service}

Une fois votre application mobile configurée dans [!DNL Adobe Experience Platform Data Collection], vous devez créer deux services (un pour les appareils iOS, un pour les appareils Android) pour pouvoir envoyer des notifications push depuis **[!DNL Adobe Campaign]**.

Découvrez comment créer et configurer un service pour les notifications push iOS et Android dans [cette section](../send/push.md#push-config).
