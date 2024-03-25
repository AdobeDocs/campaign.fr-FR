---
audience: end-user
title: Concevoir une diffusion de notification push enrichie
description: Découvrez comment concevoir une diffusion de notification push Android enrichie avec Adobe Campaign Web
feature: Push
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 771473620ea9b6d71be72871255d22b816c51b91
workflow-type: tm+mt
source-wordcount: '1234'
ht-degree: 32%

---

# Créer une diffusion push Android enrichie {#rich-push}

Firebase Cloud Messaging vous permet de choisir entre deux types de messages :

* Le **[!UICONTROL Message de données]** est géré par l’application cliente. Ces messages sont envoyés directement à l’application mobile, qui génère et affiche une notification Android sur l’appareil. Les messages de données contiennent uniquement vos variables d’application personnalisées.

* Le **[!UICONTROL Message de notification]**, géré automatiquement par le SDK FCM. FCM affiche automatiquement le message sur les appareils de vos utilisateurs et utilisatrices pour le compte de l&#39;application cliente. Les messages de notification contiennent un ensemble de paramètres et d’options prédéfini, mais peuvent encore être personnalisés avec des variables d’application personnalisées.

## Définir le contenu de la notification {#push-message}

Une fois votre diffusion de notification push créée, vous pouvez en définir le contenu. Trois modèles sont disponibles :

* **Modèle par défaut** vous permet d’envoyer des notifications avec une simple icône et une image associée.

* **Modèle de base** peuvent inclure du texte, des images et des boutons dans vos notifications.

* **Modèle de carrousel** vous permet d’envoyer des notifications avec du texte et plusieurs images que les utilisateurs peuvent parcourir.

Accédez aux onglets ci-dessous pour savoir comment composer votre message pour chaque modèle.

>[!BEGINTABS]

>[!TAB Modèle par défaut]

1. Dans la **[!UICONTROL Type de notification]** , sélectionnez **[!UICONTROL Par défaut]**.

   ![](assets/rich_push_default.png)

1. Pour composer votre message, saisissez votre texte dans le champ **[!UICONTROL Titre]** et **[!UICONTROL Message]** des champs.

   ![](assets/rich_push_default_2.png)

1. Utilisez des champs de personnalisation dynamiques pour définir le contenu, personnaliser les données et ajouter du contenu dynamique. [En savoir plus](../send/personalize.md)

1. Pour personnaliser davantage votre notification push, configurez la variable **[!UICONTROL Options de notification]** et **[!UICONTROL Options supplémentaires HTTPv1]** de votre notification push. [En savoir plus](#push-advanced)

   ![](assets/rich_push_default_3.png)

Une fois que vous avez défini le contenu de votre message, vous pouvez utiliser des abonnés au test pour prévisualiser et tester le message.

>[!TAB Modèle de base]

1. Dans la **[!UICONTROL Type de notification]** , sélectionnez **[!UICONTROL De base]**.

   ![](assets/rich_push_basic.png)

1. Pour composer votre message, saisissez votre texte dans le champ **[!UICONTROL Titre]**, **[!UICONTROL Message]** et **[!UICONTROL Message étendu]** des champs.

   La variable **[!UICONTROL Message]** Le texte apparaît dans la vue réduite pendant que la fonction **[!UICONTROL Message étendu]** s’affiche lorsque la notification est développée.

   ![](assets/rich_push_basic_2.png)

1. Utilisez des champs de personnalisation dynamiques pour définir le contenu, personnaliser les données et ajouter du contenu dynamique. [En savoir plus](../send/personalize.md)

1. Sous , **[!UICONTROL Options des couleurs]** , saisissez les codes couleur hexadécimaux pour votre **[!UICONTROL Titre]**, **[!UICONTROL Message]** et **[!UICONTROL Contexte]**.

1. Ajouter un **[!UICONTROL Bouton Rappel plus tard]** si nécessaire. Saisissez votre **[!UICONTROL Texte de rappel]** et **Date** dans les champs correspondants.

   La variable **[!UICONTROL Date de rappel]** attend une valeur représentant une époque en secondes.

1. Cliquez sur **[!UICONTROL Bouton Ajouter]** et renseignez les champs suivants :

   * **[!UICONTROL Libellé]**: texte affiché sur le bouton.
   * **[!UICONTROL Link URI]**: spécifiez l’URI à exécuter lorsque vous cliquez sur le bouton.

   Vous avez la possibilité d&#39;inclure jusqu&#39;à trois boutons dans votre notification push. Si vous optez pour la variable **[!UICONTROL Bouton Rappel plus tard]**, vous ne pouvez inclure que deux boutons au maximum.

1. Sélectionnez la variable **[!UICONTROL Type de lien]** de l’URL liée à votre bouton :

   * **[!UICONTROL URL web]**: les URL web orientent les utilisateurs vers du contenu en ligne. En cliquant, ils invitent le navigateur web par défaut de l’appareil à s’ouvrir et à accéder à l’URL désignée.

   * **[!UICONTROL Deeplink]**: les liens profonds sont des URL qui orientent les utilisateurs vers des sections spécifiques d’une application, même si celle-ci est fermée. Lorsque vous cliquez dessus, une boîte de dialogue s’affiche, permettant aux utilisateurs de choisir parmi différentes applications capables de gérer le lien.

   * **[!UICONTROL Ouvrir l’application]**: les URL d’ouverture de l’application vous permettent de vous connecter directement au contenu d’une application. Elle permet à votre application de se définir comme gestionnaire par défaut pour un type spécifique de lien, en contournant la boîte de dialogue de clarification.

   Pour plus d’informations sur la gestion des liens d’application Android, reportez-vous à la section [Documentation pour les développeurs Android](https://developer.android.com/training/app-links).

   ![](assets/rich_push_basic_3.png)

1. Pour personnaliser davantage votre notification push, configurez la variable **[!UICONTROL Options de notification]** et **[!UICONTROL Options supplémentaires HTTPv1]** de votre notification push. [En savoir plus](#push-advanced)

   ![](assets/rich_push_basic_4.png)

Une fois que vous avez défini le contenu de votre message, vous pouvez utiliser des abonnés au test pour prévisualiser et tester le message.

>[!TAB Modèle de carrousel]

1. Dans la **[!UICONTROL Type de notification]** , sélectionnez **[!UICONTROL Carrousel]**.

   ![](assets/rich_push_carousel.png)

1. Pour composer votre message, saisissez votre texte dans le champ **[!UICONTROL Titre]**, **[!UICONTROL Message]** et **[!UICONTROL Message étendu]** des champs.

   La variable **[!UICONTROL Message]** Le texte apparaît dans la vue réduite pendant que la fonction **[!UICONTROL Message étendu]** s’affiche lorsque la notification est développée.

   ![](assets/rich_push_carousel_1.png)

1. Utilisez l&#39;éditeur d&#39;expression pour définir le contenu, personnaliser les données et ajouter du contenu dynamique. [En savoir plus](../send/personalize.md)

1. Sous , **[!UICONTROL Options des couleurs]** , saisissez les codes couleur hexadécimaux pour votre **[!UICONTROL Titre]**, **[!UICONTROL Message]** et **[!UICONTROL Contexte]**.

1. Choisissez la méthode **[!UICONTROL Carrousel]** est utilisé :

   * **[!UICONTROL Auto]**: effectue automatiquement un cycle à travers les images sous forme de diapositives, en transition à des intervalles prédéfinis.
   * **[!UICONTROL Manuel]**: permet aux utilisateurs de passer manuellement d’une diapositive à l’autre pour naviguer dans les images.

1. Dans la **[!UICONTROL Disposition]** , sélectionnez **[!UICONTROL Filmstrip]** pour inclure des aperçus des images précédente et suivante à côté de la diapositive principale.

1. Cliquez sur **[!UICONTROL Ajouter une image]** et saisissez l’URL de l’image, le texte et l’URL de l’action.

   Veillez à inclure trois images au minimum et cinq images au maximum.

   ![](assets/rich_push_carousel_2.png)

1. Pour personnaliser davantage votre notification push, configurez la variable **[!UICONTROL Options de notification]** et **[!UICONTROL Options supplémentaires HTTPv1]** de votre notification push. [En savoir plus](#push-advanced)

   ![](assets/rich_push_carousel_3.png)

Une fois que vous avez défini le contenu de votre message, vous pouvez utiliser des abonnés au test pour prévisualiser et tester le message.

>[!ENDTABS]

## Paramètres avancés des notifications push {#push-advanced}

### Options de notification {#notification-options}

| Paramètre | Description |
|---------|---------|
| **[!UICONTROL Identifiant du canal]** | Définissez l’identifiant de canal de votre notification. L’application doit créer un canal avec cet identifiant de canal avant la réception d’une notification avec cet identifiant de canal. |
| **[!UICONTROL Icône]** | Définissez l&#39;icône de la notification à afficher sur les appareils de vos profils. |
| **[!UICONTROL Son]** | Définissez le son à émettre lorsque l’appareil reçoit votre notification. |
| **[!UICONTROL Balise]** | Définissez l’identifiant utilisé pour remplacer les notifications existantes dans le tiroir de notifications. Vous éviterez ainsi l’accumulation de plusieurs notifications et vous assurerez que seule la dernière notification pertinente est affichée. |
| **[!UICONTROL Couleur]** | Définissez la couleur de l&#39;icône de votre notification avec le code couleur hexadécimal. |
| **[!UICONTROL Action de clic]** | Définissez l&#39;action associée à un clic de l&#39;utilisateur sur votre notification. |
| **[!UICONTROL Couleur d’arrière-plan des notifications]** | Définissez la couleur de votre arrière-plan de notification avec vos codes couleur hexadécimaux. |
| **[!UICONTROL Type de lien]** | <ul><li>URL web : les URL web orientent les utilisateurs vers du contenu en ligne. En cliquant, ils invitent le navigateur web par défaut de l’appareil à s’ouvrir et à accéder à l’URL désignée.</li><li>Lien profond : les liens profonds sont des URL qui orientent les utilisateurs vers des sections spécifiques d’une application, même si celle-ci est fermée. Lorsque vous cliquez dessus, une boîte de dialogue s’affiche, permettant aux utilisateurs de choisir parmi différentes applications capables de gérer le lien.</li><li> Ouvrir l’application : les URL de l’application ouvertes vous permettent de vous connecter directement au contenu d’une application. Elle permet à votre application de se définir comme gestionnaire par défaut pour un type spécifique de lien, en contournant la boîte de dialogue de clarification.</li></ul> |

### Options supplémentaires HTTPv1 {#additional-options}

| Paramètre | Description |
|---------|---------|
| **[!UICONTROL Ticker]** | Définissez le texte de la coche de votre notification. Uniquement disponible pour les appareils configurés sur Android 5.0 Lollipop. |
| **[!UICONTROL Épinglé]** | Lorsqu’elle est activée, la notification reste visible si l’utilisateur ou l’utilisatrice clique dessus. <br>Si cette option est désactivée, la notification est automatiquement ignorée lorsque la personne interagit avec celle-ci. Le comportement en « pense-bête » permet à des notifications importantes de persister pendant de plus longues périodes à l’écran. |
| **[!UICONTROL Image]** | Définissez l&#39;URL de l&#39;image à afficher dans votre notification. |
| **[!UICONTROL Priorité des notifications]** | Définissez le niveau de priorité de votre notification, qui peut être par défaut, minimale, faible ou élevée. Le niveau de priorité détermine l’importance et l’urgence de la notification. Il influence son affichage et la possibilité ou non qu’elle puisse contourner certains paramètres système. Pour plus d’informations à ce propos, consultez la [documentation FCM](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#notificationpriority). |
| **[!UICONTROL Nombre de notifications]** | Définissez le nombre de nouvelles informations non lues à afficher directement sur l’icône de l’application. Cela permet à l’utilisateur ou à l’utilisatrice de voir rapidement le nombre de notifications en attente. |
| **[!UICONTROL Visibilité]** | Définissez le niveau de visibilité de votre notification, qui peut être publique, privée ou secrète. Le niveau de visibilité détermine dans quelle mesure le contenu de la notification s’affiche sur l’écran de verrouillage et dans d’autres zones sensibles. Pour plus d’informations, consultez la [documentation FCM](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#visibility). |
| **[!UICONTROL Variables de l’application]** | Permet de définir le comportement des notifications. Ces variables sont entièrement personnalisables et font partie de la payload du message envoyée à l’appareil mobile. |
