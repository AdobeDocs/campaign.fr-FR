---
title: Envoi de notification push avec Adobe Campaign
description: Prise en main des notifications push dans Campaign
feature: Push
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: f04c6e0c-f2b9-496a-9697-04ef4c3411ee
TQID: 'https://experienceleague.adobe.com/p2PfMRhMJi7WEDptyTEzpSp6u6WVFjqSvaC9g8Qaq9g'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: a4657621-810c-498b-8a27-7ced9c176dda
    internal-label: Push notifications
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: c4f3ffbf421621fa15b1b4d56480bd0ff9304254
workflow-type: tm+mt
source-wordcount: '1237'
ht-degree: 76%
---
# Créer et envoyer des notifications push{#push-notifications-create}

Les diffusions d’applications mobiles vous permettent d’envoyer des notifications aux appareils iOS et Android.

Avant de commencer à envoyer des notifications push avec Adobe Campaign, vous devez vous assurer que les configurations et les intégrations sont en place sur l’application mobile et pour les balises dans Adobe Experience Platform. [En savoir plus sur la configuration des notifications push](push-settings.md).

>[!CAUTION]
>
>Certaines modifications importantes apportées au service Android FCM (Firebase Cloud Messaging) seront publiées en 2024 et pourront avoir une incidence sur votre mise en œuvre d’Adobe Campaign. Il se peut que la configuration de vos services d’abonnement pour les messages push Android doive être mise à jour pour prendre en charge cette modification. Vous pouvez déjà vérifier et agir.

## Création de votre première notification push {#push-create}

Cette section présente les éléments spécifiques à la diffusion de notifications iOS et Android.

>[!IMPORTANT]
>
>Dans le contexte d’un [Déploiement Enterprise (FFDA)](../architecture/enterprise-deployment.md), l’enregistrement mobile est désormais **asynchrone**. [En savoir plus](../architecture/staging.md)


Pour créer une nouvelle diffusion, accédez à l&#39;onglet **[!UICONTROL Campagnes]**, cliquez sur **[!UICONTROL Diffusions]**, puis sur le bouton **[!UICONTROL Créer]** au-dessus de la liste des diffusions existantes.

![Liste des diffusions dans l&#39;onglet Campagnes avec le lien Diffusions en surbrillance et une flèche sur le bouton Créer](assets/delivery_step_1.png)


Par défaut, Adobe Campaign est livré avec deux modèles de diffusion : un pour iOS, un autre pour Android. Vous pouvez les dupliquer pour définir vos propres paramètres. Les étapes de configuration d’une diffusion push basée sur ces modèles sont présentées ci-dessous.

>[!BEGINTABS]

>[!TAB iOS]

Pour envoyer des notifications sur les appareils iOS, procédez comme suit :

1. Sélectionnez le modèle de diffusion **[!UICONTROL Diffuser sur iOS]**.

   ![Liste des modèles de diffusion avec Diffuser sur iOS (ios) sélectionnée avant de cliquer sur Continuer](assets/push_ios_1.png)

1. Pour définir la cible de la notification, cliquez sur le lien **[!UICONTROL Pour]**, puis sur **[!UICONTROL Ajouter]**.

   ![Boîte de dialogue Sélectionner la cible avec le mapping Applications abonnées et le bouton Ajouter dans la population cible de la diffusion](assets/push_ios_2.png)

1. Sélectionnez **[!UICONTROL Abonnés d&#39;une application mobile iOS (iPhone, iPad)]**, choisissez le service correspondant à votre application mobile, puis sélectionnez la version iOS de l&#39;application.

   ![Étape de type Target avec Abonnés d&#39;une application mobile iOS (iPhone, iPad) sélectionnée](assets/push_ios_3.png)

1. Choisissez votre **[!UICONTROL Type de notification]** entre **[!UICONTROL Notification générale (alerte, son, pastille)]** ou **[!UICONTROL Notification silencieuse]**.

   ![Onglet Général avec le type de notification : notification générale (alerte, son, pastille) ou notification silencieuse](assets/push_ios_4.png)

   >[!NOTE]
   >
   >Le mode **Notification silencieuse** permet d&#39;envoyer une notification &quot;silencieuse&quot; à une application mobile. L&#39;utilisateur n&#39;est pas averti de l&#39;arrivée de la notification. Elle est directement transférée à l&#39;application.

1. Dans le champ **[!UICONTROL Titre]**, saisissez le libellé du titre qui doit apparaître dans la liste des notifications disponibles depuis le centre de notifications.

   Ce champ vous permet de définir la valeur du paramètre **Titre** de la payload de notification iOS.

1. Vous pouvez ajouter un **[!UICONTROL Sous-titre]**, valeur du paramètre **sous-titre** de la payload de notification iOS.

1. Saisissez le contenu du message dans la section **[!UICONTROL Contenu du message]** de l’assistant.

1. Dans l’onglet **[!UICONTROL Son et pastille]** vous pouvez modifier les options suivantes :

   * **[!UICONTROL Nettoyer la pastille]** : activez cette option pour actualiser la valeur de la pastille.

   * **[!UICONTROL Valeur]** : définissez un nombre qui sera utilisé pour afficher directement sur l’icône de l’application le nombre de nouvelles informations non lues.

   * **[!UICONTROL Mode d’alerte critique]** : activez cette option pour ajouter du son à votre notification même si le téléphone de l’utilisateur est en mode thème ou si l’iPhone est en mode silencieux.

   * **[!UICONTROL Nom]** : sélectionnez le son que doit émettre le terminal mobile à la réception de la notification.

   * **[!UICONTROL Volume]** : volume de votre son de 0 à 100.

     >[!NOTE]
     > 
     >Les sons doivent être inclus dans l’application et définis lors de la création du service.
     >

   ![Onglet Son et pastille avec valeur pastille, pastille propre, mode d&#39;alerte critique et paramètres de nom du son](assets/push_ios_5.png)

1. Dans l’onglet **[!UICONTROL Variables de l’application]**, vos **[!UICONTROL variables d’application]** sont automatiquement ajoutées. Elles permettent de définir le comportement des notifications. Par exemple, vous pouvez configurer l’affichage d’un écran spécifique lorsque l’utilisateur active la notification.

1. Dans l’onglet **[!UICONTROL Avancé]**, vous pouvez modifier les options générales suivantes :

   * **[!UICONTROL Contenu mutable]** : activez cette option pour permettre à l’application mobile de télécharger le contenu multimédia.

   * **[!UICONTROL Thread-id]** : identifiant utilisé pour regrouper les notifications associées.

   * **[!UICONTROL Catégorie]** : nom de votre identifiant de catégorie qui affichera les boutons d’action. Ces notifications permettent à l&#39;utilisateur d&#39;effectuer plus rapidement différentes tâches en réponse à celles-ci, sans ouvrir l&#39;application ou la parcourir.

   ![Onglet avancé avec contenu modifiable, champs Thread-id et Catégorie mis en surbrillance](assets/push_ios_6.png)

1. Pour une notification sensible à l’heure, vous pouvez spécifier les options suivantes :

   * **[!UICONTROL Identifiant du contenu Target]** : identifiant utilisé pour cibler la fenêtre d&#39;application à afficher au premier plan à l&#39;ouverture de la notification.

   * **[!UICONTROL Image de Launch]** : nom du fichier image de Launch à afficher. Si l’utilisateur choisit de lancer votre application, l’image sélectionnée s’affichera au lieu de l’écran de lancement de votre application.

   * **[!UICONTROL Niveau d&#39;interruption]**:

     * **[!UICONTROL Actif]** : défini par défaut, le système présente immédiatement la notification, illumine l’écran et peut émettre un son. Les notifications ne passent pas en mode Thème.

     * **[!UICONTROL Passif]** : le système ajoute la notification à la liste de notifications sans allumer l’écran ni émettre de son. Les notifications ne passent pas en mode Thème.

     * **[!UICONTROL Sensible à l’heure]** : le système présente immédiatement la notification, allume l’écran, peut émettre un son et passer en mode Thème. Ce niveau ne nécessite pas d’autorisation spéciale de la part d’Apple.

     * **[!UICONTROL Critique]** : le système présente immédiatement la notification, allume l’écran et contourne le bouton de désactivation ou le mode de thème. Notez que ce niveau nécessite une autorisation spéciale de la part d’Apple.

   * **[!UICONTROL Score de pertinence]** : définissez un score de pertinence compris entre 0 et 100. Le système l’utilise pour trier les notifications dans le résumé de la notification.

   ![Onglet Avancé avec ID de contenu Target, image de lancement, niveau d&#39;interruption et score de pertinence renseigné](assets/push_ios_7.png)

1. Une fois la notification configurée, cliquez sur l&#39;onglet **[!UICONTROL Aperçu]** pour la prévisualiser.

   ![Onglet Aperçu affichant le titre et le message de la notification push iOS dans une maquette de téléphone](assets/push-ios-preview.png)


>[!TAB Android]

Pour envoyer des notifications sur les appareils Android, procédez comme suit :

1. Sélectionnez le modèle de diffusion **[!UICONTROL Diffuser sur Android (android)]**.

   ![Liste des modèles de diffusion avec Diffuser sur Android (android) sélectionnée avant de cliquer sur Continuer](assets/push-template-android.png)

   >[!NOTE]
   > 
   >Avec les dernières API FCM (HTTP v1), vous devez mettre à jour votre **modèles de diffusion** pour les notifications push Android afin d’augmenter le nombre de messages par lot. Pour ce faire, accédez aux propriétés de votre modèle de diffusion Android puis, dans l’onglet **Diffusion**, définissez [Nombre de lots de messages](../../v8/send/configure-and-send.md#delivery-batch-quantity) sur **256**. Appliquez cette modification à tous les modèles de diffusion utilisés pour vos diffusions Android, ainsi qu’à toutes vos diffusions Android existantes.


1. Pour définir la cible de la notification, cliquez sur le lien **[!UICONTROL Pour]**, puis sur **[!UICONTROL Ajouter]**.

   ![Sélectionnez la boîte de dialogue cible avec le mappage Applications abonnées et le bouton Ajouter pour la diffusion Android](assets/push-android-select-target.png)

1. Sélectionnez **[!UICONTROL Abonnés d&#39;une application mobile Android]**, choisissez le service correspondant à votre application mobile (Neotrips, dans notre exemple), puis sélectionnez la version Android de l&#39;application.

   ![Étape de type Target avec sélection des abonnés d&#39;une application mobile Android](assets/push-android-subscribers.png)

1. Saisissez ensuite le contenu de la notification.

   ![Onglet Contenu de la diffusion Android avec les options Type de message, texte du message et tableau Variables de l&#39;application](assets/push-android-content.png)

1. Cliquez sur l&#39;icône **[!UICONTROL Insérer une émoticône]** pour insérer des émoticônes dans votre notification push.

1. Dans le champ **[!UICONTROL Variables de l&#39;application]**, saisissez la valeur de chaque variable. Vous pouvez par exemple paramétrer un écran d&#39;application spécifique qui s&#39;affichera lorsque l&#39;utilisateur activera la notification.

1. Une fois la notification configurée, cliquez sur l&#39;onglet **[!UICONTROL Aperçu]** pour la prévisualiser.

   <!--![](assets/push-android-preview.png)-->

>[!ENDTABS]


## Test, envoi et surveillance de vos notifications push {#push-test}

L’envoi du BAT et l’envoi final de la diffusion s’effectuent de la même manière que pour les autres diffusions.

Découvrez comment valider une diffusion dans [Prévisualiser et tester votre e-mail](preview-and-proof.md).

Découvrez comment confirmer et envoyer la diffusion dans [Envoyer et surveiller vos e-mails](send.md)

Après l&#39;envoi des messages, vous pouvez surveiller et suivre vos diffusions. Découvrez les raisons de l’échec de la diffusion des notifications push dans [Types d’erreur des notifications push](delivery-failures.md#push-error-types).

