---
audience: end-user
title: Concevoir une diffusion de notification push enrichie
description: Découvrir comment concevoir une diffusion de notification push iOS enrichie avec Adobe Campaign Web
feature: Push
role: User
level: Beginner
exl-id: 75a57ddb-558e-4dd2-a684-e63e51545554
source-git-commit: fef2c829da637b43067147b51aff7030d25c9744
workflow-type: tm+mt
source-wordcount: '1260'
ht-degree: 100%

---

# Concevoir une diffusion de notification push iOS enrichie {#rich-push}

>[!IMPORTANT]
>
>Avant de concevoir une notification push enrichie, vous devez d’abord configurer votre connecteur V2. Consultez [cette page](https://experienceleague.adobe.com/fr/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application) pour accéder à la procédure détaillée.

## Définir le contenu d’une notification iOS {#push-message}

Une fois votre diffusion push créée, vous pouvez définir son contenu à l’aide d’un des modèles suivants :

* Le **modèle par défaut** vous permet d’envoyer des notifications avec une simple icône et une image associée.

* Le **modèle de base** peut inclure du texte, des images et des boutons dans vos notifications.

* Le **modèle de carrousel** vous permet d’envoyer des notifications avec du texte et plusieurs images que les utilisateurs et utilisatrices peuvent faire défiler.

Accédez aux onglets ci-dessous pour en savoir plus sur la personnalisation de ces modèles.

>[!BEGINTABS]

>[!TAB Par défaut]

1. Sélectionnez **[!UICONTROL Notification générale (alerte, son, pastille)]** comme **[!UICONTROL Type de notification]**.

1. Dans le menu déroulant **[!UICONTROL Type de notification]**, sélectionnez **[!UICONTROL Par défaut]**.

   ![](assets/rich_push_ios_default_1.png)

1. Dans le champ **[!UICONTROL Titre]**, saisissez le libellé du titre qui doit apparaître dans la liste des notifications disponibles depuis le centre de notifications.

   Ce champ vous permet de définir la valeur du paramètre **Titre** de la payload de notification iOS.

1. Vous pouvez éventuellement ajouter un **[!UICONTROL Sous-titre]**, qui correspond à la valeur du paramètre **sous-titre** du payload de notification iOS.

1. Saisissez le contenu du message dans la section **[!UICONTROL Contenu du message]** de l’assistant.

   ![](assets/rich_push_ios_default_2.png)

1. Accédez à l’onglet **[!UICONTROL Son et pastille]** pour personnaliser des paramètres supplémentaires tels que les options de son et de pastille pour vos notifications. [En savoir plus](#sound-badge)

   ![](assets/rich_push_ios_default_3.png)

1. Dans l’onglet **[!UICONTROL Variables de l’application]**, vos **[!UICONTROL variables d’application]** sont automatiquement ajoutées. Elles permettent de définir le comportement des notifications. Par exemple, vous pouvez configurer l’affichage d’un écran spécifique lorsque l’utilisateur active la notification.

1. Pour une personnalisation plus poussée, explorez les **[!UICONTROL options avancées]** disponibles pour vos notifications push. [En savoir plus](#push-advanced)

   ![](assets/rich_push_ios_default_4.png)

1. Une fois la notification configurée, cliquez sur l’onglet **[!UICONTROL Aperçu]** pour la prévisualiser.

>[!TAB De base]

1. Sélectionnez **[!UICONTROL Notification générale (alerte, son, pastille)]** comme **[!UICONTROL Type de notification]**.

1. Dans le menu déroulant **[!UICONTROL Type de notification]**, sélectionnez **[!UICONTROL De base]**.

   ![](assets/rich_push_ios_basic_1.png)

1. Pour composer votre message, saisissez votre texte dans les champs **[!UICONTROL Titre]**, **[!UICONTROL Message étendu]**, **[!UICONTROL Message]** et **[!UICONTROL Message étendu]**.

   Le texte **[!UICONTROL Message]** s’affiche dans la vue réduite, alors que le **[!UICONTROL Message étendu]** s’affiche lorsque la notification est développée.

   ![](assets/rich_push_ios_basic_2.png)

1. Vous pouvez éventuellement ajouter un **[!UICONTROL Sous-titre]**, qui correspond à la valeur du paramètre **sous-titre** du payload de notification iOS.

1. Accédez à l’onglet **[!UICONTROL Son et pastille]** pour personnaliser des paramètres supplémentaires tels que les options de son et de pastille pour vos notifications. [En savoir plus](#sound-badge)

1. Dans l’onglet **[!UICONTROL Variables de l’application]**, vos **[!UICONTROL variables d’application]** sont automatiquement ajoutées. Elles permettent de définir le comportement des notifications. Par exemple, vous pouvez configurer l’affichage d’un écran spécifique lorsque l’utilisateur active la notification.

1. Pour une personnalisation plus poussée, explorez les **[!UICONTROL options avancées]** disponibles pour vos notifications push. [En savoir plus](#push-advanced)

   ![](assets/rich_push_ios_default_4.png)

1. Dans le menu **[!UICONTROL Options des couleurs]**, saisissez les codes hexadécimaux des couleurs de votre **[!UICONTROL Titre]**, **[!UICONTROL Message]** et **[!UICONTROL Arrière-plan]**.

   ![](assets/rich_push_ios_basic_3.png)

Une fois que vous avez défini le contenu de votre message, vous pouvez utiliser des personnes abonnées de test pour prévisualiser et tester le message.

>[!TAB Carrousel]

1. Sélectionnez **[!UICONTROL Notification générale (alerte, son, pastille)]** comme **[!UICONTROL Type de notification]**.

1. Dans le menu déroulant **[!UICONTROL Type de notification]**, sélectionnez **[!UICONTROL Carrousel]**.

   ![](assets/rich_push_ios_carousel_1.png)

1. Pour composer votre message, saisissez votre texte dans les champs **[!UICONTROL Titre]**, **[!UICONTROL Message étendu]** et **[!UICONTROL Message]**.

   ![](assets/rich_push_ios_carousel_2.png)

1. Accédez à l’onglet **[!UICONTROL Son et pastille]** pour personnaliser des paramètres supplémentaires tels que les options de son et de pastille pour vos notifications. [En savoir plus](#sound-badge)

1. Dans l’onglet **[!UICONTROL Variables de l’application]**, vos **[!UICONTROL variables d’application]** sont automatiquement ajoutées. Elles permettent de définir le comportement des notifications. Par exemple, vous pouvez configurer l’affichage d’un écran spécifique lorsque l’utilisateur active la notification.

   ![](assets/rich_push_ios_carousel_4.png)

1. Pour une personnalisation plus poussée, explorez les **[!UICONTROL options avancées]** disponibles pour vos notifications push. [En savoir plus](#push-advanced)

1. Dans le menu **[!UICONTROL Options des couleurs]**, saisissez les codes hexadécimaux des couleurs de votre **[!UICONTROL Titre]**, **[!UICONTROL Message]** et **[!UICONTROL Arrière-plan]**.

1. Choisissez le fonctionnement du **[!UICONTROL carrousel]** dans l’onglet **[!UICONTROL Options de carrousel]** :

   * **[!UICONTROL Auto]** : fait automatiquement défiler les images sous forme de diapositives, selon des transitions à intervalles prédéfinis.
   * **[!UICONTROL Manuel]** : permet de passer manuellement d’une diapositive à l’autre pour naviguer dans les images.

1. Cliquez sur **[!UICONTROL Ajouter une image]** et saisissez l’**[!UICONTROL URL de l’image]**, le **[!UICONTROL texte]** et l’**[!UICONTROL URL de l’action]**.

   Veillez à inclure trois images minimum et cinq maximum.

   ![](assets/rich_push_ios_carousel_3.png)

Une fois que vous avez défini le contenu de votre message, vous pouvez utiliser des personnes abonnées de test pour prévisualiser et tester le message.

>[!TAB Retardateur]

1. Sélectionnez **[!UICONTROL Notification générale (alerte, son, pastille)]** comme **[!UICONTROL Type de notification]**.

1. Dans le menu déroulant **[!UICONTROL Type de notification]**, sélectionnez **[!UICONTROL Retardateur]**.

   ![](assets/rich_push_ios_timer_1.png)

1. Pour composer votre message, saisissez votre texte dans les champs **[!UICONTROL Titre]**, **[!UICONTROL Titre étendu]**, **[!UICONTROL Message]** et **[!UICONTROL Message étendu]**.

   Le texte **[!UICONTROL Message]** s’affiche dans la vue réduite, alors que le **[!UICONTROL Message étendu]** s’affiche lorsque la notification est développée.

   ![](assets/rich_push_ios_timer_2.png)

1. Vous pouvez éventuellement ajouter un **[!UICONTROL Sous-titre]**, qui correspond à la valeur du paramètre **sous-titre** du payload de notification iOS.

1. Accédez à l’onglet **[!UICONTROL Son et pastille]** pour personnaliser des paramètres supplémentaires tels que les options de son et de pastille pour vos notifications. [En savoir plus](#sound-badge)

1. Dans l’onglet **[!UICONTROL Variables de l’application]**, vos **[!UICONTROL variables d’application]** sont automatiquement ajoutées. Elles permettent de définir le comportement des notifications. Par exemple, vous pouvez configurer l’affichage d’un écran spécifique lorsque l’utilisateur active la notification.

1. Pour une personnalisation plus poussée, explorez les **[!UICONTROL options avancées]** disponibles pour vos notifications push. [En savoir plus](#push-advanced)

1. Dans le menu **[!UICONTROL Options des couleurs]**, saisissez les codes hexadécimaux des couleurs de votre **[!UICONTROL Titre]**, **[!UICONTROL Message]** et **[!UICONTROL Arrière-plan]**.

   ![](assets/rich_push_ios_timer_4.png)

1. Dans l’onglet **[!UICONTROL Retardateur]**, définissez la **[!UICONTROL durée du retardateur]** en secondes ou l’**[!UICONTROL horodatage de fin du retardateur]** sur un horodatage d’époque spécifique.

1. Saisissez le texte et l’image qui s’afficheront une fois le retardateur expiré dans les champs **[!UICONTROL Autre titre]**, **[!UICONTROL Autre message]** et **[!UICONTROL Autre image]**.

   ![](assets/rich_push_ios_timer_3.png)

Une fois que vous avez défini le contenu de votre message, vous pouvez utiliser des personnes abonnées de test pour prévisualiser et tester le message.

>[!ENDTABS]

## Paramètres avancés des notifications push {#push-advanced}

### Options de son et pastille {#sound-badge}

| Paramètre | Description |
|---------|---------|
| **[!UICONTROL Nettoyer la pastille]** | Activez cette option pour actualiser la valeur de la pastille. |
| **[!UICONTROL Valeur]** | Définissez un nombre qui sera utilisé pour afficher directement sur l’icône de l’application le nombre de nouvelles informations non lues. |
| **[!UICONTROL Mode d’alerte critique]** | Activez cette option pour ajouter du son à votre notification, même si le téléphone de la personne est en mode Concentration ou si l’iPhone est en mode silencieux. |
| **[!UICONTROL Nom]** | Sélectionnez le son que doit émettre le terminal mobile à la réception de la notification. |
| **[!UICONTROL Volume]** | Définissez le volume de votre son de 0 à 100. Les sons doivent être inclus dans l’application et définis lors de la création du service. |

### Options avancées {#notification-options}

| Paramètre | Description |
|---------|---------|
| **[!UICONTROL Contenu modifiable]** | Activez cette option pour permettre à l’application mobile de télécharger le contenu multimédia. |
| **[!UICONTROL Thread-id]** | Définissez l’identifiant utilisé pour regrouper les notifications associées. |
| **[!UICONTROL Catégorie]** | Définissez le nom de votre identifiant de catégorie qui affichera les boutons d’action. Ces notifications permettent à la personne d’effectuer plus rapidement différentes tâches en réponse à une notification, sans ouvrir l’application ou la parcourir. |
| **[!UICONTROL Identifiant du contenu Target]** | Définissez un identifiant utilisé pour cibler la fenêtre d’application à afficher au premier plan à l’ouverture de la notification. |
| **[!UICONTROL Image de Launch]** | Définissez le nom du fichier image de Launch à afficher. Si la personne choisit de lancer votre application, l’image sélectionnée s’affichera au lieu de l’écran de lancement de votre application. |
| **[!UICONTROL Action de clic]** | Définissez l’action associée à un clic d’un utilisateur ou d’une utilisatrice sur votre notification. |
| **[!UICONTROL Niveau d’interruption]** | <ul><li>Actif : défini par défaut, le système présente immédiatement la notification, illumine l’écran et peut émettre un son. Les notifications n’outrepassent pas le mode Concentration.</li><li>Passif : le système ajoute la notification à la liste de notifications sans allumer l’écran ni émettre de son. Les notifications n’outrepassent pas le mode Concentration.</li><li> Sensible à l’heure : le système présente immédiatement la notification, allume l’écran, peut émettre un son et outrepasser le mode Concentration. Ce niveau ne nécessite pas d’autorisation spéciale de la part d’Apple.</li><li>Critique : le système présente immédiatement la notification, allume l’écran et contourne le bouton de désactivation du son ou le mode Concentration. Notez que ce niveau nécessite une autorisation spéciale de la part d’Apple.</li></ul> |
| **[!UICONTROL Score de pertinence]** | Définissez un score de pertinence compris entre 0 et 100. Le système l’utilise pour trier les notifications dans le résumé de la notification. |
