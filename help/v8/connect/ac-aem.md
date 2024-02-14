---
title: Utilisation de Campaign et Adobe Experience Manager
description: Découvrez comment utiliser Campaign et Adobe Experience Manager
feature: Experience Manager Integration
role: Admin, User
level: Beginner
exl-id: e83893f7-a8be-48a3-a7a6-aced7b4d4f69
source-git-commit: 92fe7c41047aafd26cca70a547025a3eff73e398
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 19%

---

# Utilisation de Campaign et Adobe Experience Manager {#ac-aem}

L&#39;intégration entre Adobe Campaign et Adobe Experience Manager vous permet de gérer le contenu de vos diffusions email, ainsi que vos formulaires directement dans Adobe Experience Manager. Vous avez la possibilité d’importer **Adobe Experience Manager** contenu dans Campaign ou connectez-vous à **Adobe Experience Manager as a Cloud Service** , ce qui vous permet de modifier votre contenu directement dans l’interface Web.

![](../assets/do-not-localize/book.png) [Découvrez comment modifier votre contenu Adobe Experience Manager en tant que Cloud Service dans l’interface web de Campaign](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/content/integrations/aem-content.html?lang=en)

![](../assets/do-not-localize/book.png) [En savoir plus sur Adobe Experience Manager dans ce document](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignonpremise.html?lang=fr#aem-and-adobe-campaign-integration-workflow)

## Création avec Adobe Experience Manager {#integrating-with-aem}

![](../assets/do-not-localize/speech.png)  En tant qu’utilisateur Managed Cloud Services, [contactez Adobe](../start/campaign-faq.md#support) pour intégrer Adobe Experience Manager à Campaign.

Cette intégration peut être utilisée, par exemple, pour créer une newsletter dans Adobe Experience Manager, qui sera ensuite utilisée dans le cadre d’une campagne e-mail dans Adobe Campaign.

**Depuis Adobe Experience Manager :**

1. Accédez à [!DNL Adobe Experience Manager] instance de création et cliquez sur Adobe l’expérience dans le coin supérieur gauche de la page. Choisir **[!UICONTROL Sites]** dans le menu.

   ![](assets/aem_authoring_1.png)

1. Accès **[!UICONTROL Campagnes > Nom de votre marque (We.Shopping, dans le cas présent) > Zone principale > Email]**.

1. Cliquez sur **[!UICONTROL Créer]** et sélectionnez **[!UICONTROL Page]** dans le menu déroulant.

   ![](assets/aem_authoring_2.png)

1. Sélectionnez la variable **[!UICONTROL Adobe Campaign Email]** modèle et nommez votre newsletter.

1. Après avoir créé votre page, accédez à la **[!UICONTROL Informations sur la page]** et cliquez sur **[!UICONTROL Ouvrir les propriétés]**.

   ![](assets/aem_authoring_3.png)

1. Personnalisez votre contenu d&#39;email en ajoutant des composants, tels que des champs de personnalisation d&#39;Adobe Campaign. [En savoir plus](https://experienceleague.adobe.com/docs/experience-manager-65/content/sites/authoring/aem-adobe-campaign/campaign.html?lang=en#editing-email-content)

1. Une fois que votre email est prêt, accédez au **[!UICONTROL Informations sur la page]** et cliquez sur **[!UICONTROL Démarrer le workflow]**.

   ![](assets/aem_authoring_4.png)

1. Dans la première liste déroulante, sélectionnez **[!UICONTROL Approuver Adobe Campaign]** en tant que modèle de processus et cliquez sur **[!UICONTROL Démarrer le workflow]**.

   ![](assets/aem_authoring_5.png)

1. Une clause de non-responsabilité s’affiche en haut de la page et indique : `This page is subject to the workflow Approve for Adobe Campaign`. Cliquez sur **[!UICONTROL Terminer]** en regard de la clause de non-responsabilité pour confirmer la révision, puis cliquez sur **[!UICONTROL Ok]**.

1. Cliquez sur **[!UICONTROL Terminer]** puis sélectionnez **[!UICONTROL Validation de newsletter]** dans le **[!UICONTROL Étape suivante]** menu déroulant.

   ![](assets/aem_authoring_6.png)

Votre newsletter est maintenant prête et synchronisée dans Adobe Campaign.

**Depuis Adobe Campaign :**

1. Dans l&#39;onglet **[!UICONTROL Campagnes]**, cliquez sur **[!UICONTROL Diffusions]** et sur **[!UICONTROL Créer]**.

1. Choisissez la **[!UICONTROL Diffusion email avec contenu AEM (mailAEMContent)]** du modèle **[!UICONTROL Modèle de diffusion]** menu déroulant.

   ![](assets/aem_authoring_7.png)

1. Ajoutez un **[!UICONTROL Libellé]** à votre diffusion, puis cliquez sur **[!UICONTROL Continuer]**.

1. Cliquez sur **[!UICONTROL Synchroniser]** pour accéder à vos diffusions AEM.

   Si le bouton n’est pas visible dans votre interface, accédez à la **[!UICONTROL Propriétés]** et accéder au **[!UICONTROL Avancé]** . Assurez-vous que la variable **[!UICONTROL Mode d&#39;édition du contenu]** est configuré sur **[!UICONTROL AEM]** et saisissez les détails de votre instance AEM dans la variable **[!UICONTROL Compte AEM]** champ .

   ![](assets/aem_authoring_8.png)

1. Sélectionnez la diffusion AEM précédemment créée dans [!DNL Adobe Experience Manager] et confirmer en cliquant sur **[!UICONTROL Ok]**.

1. Assurez-vous de cliquer sur le bouton **[!UICONTROL Actualiser le contenu]** chaque fois que des modifications sont apportées à votre diffusion AEM.

Votre email est maintenant prêt à être envoyé à votre audience.

## Importation de ressources à partir de la bibliothèque Adobe Experience Manager Assets {#assets-library}

Vous pouvez également insérer directement des ressources à partir de votre [!DNL Adobe Experience Manager Assets Library] lors de l&#39;édition d&#39;un email ou d&#39;une landing page dans Adobe Campaign. Cette fonctionnalité est présentée dans la section [Documentation Adobe Experience Manager Assets](https://experienceleague.adobe.com/docs/experience-manager-65/content/assets/managing/manage-assets.html?lang=en).

1. Chargement de vos ressources dans **Bibliothèque Adobe Experience Manager Assets**. [En savoir plus](https://experienceleague.adobe.com/docs/experience-manager-65/content/assets/managing/manage-assets.html?lang=en#uploading-assets)

1. Dans Adobe Campaign, créez une diffusion en accédant à la **Campagnes** , cliquez sur **Diffusions** et cliquez sur le bouton **Créer** au-dessus de la liste des diffusions existantes.

1. Sélectionnez une **Modèle de diffusion**, puis attribuez un nom à votre diffusion.

1. Définissez et personnalisez le contenu du message. [En savoir plus](../send/email.md)

1. Pour utiliser **Bibliothèque Adobe Experience Manager Assets**, accédez au **[!UICONTROL Propriétés]** de votre diffusion AEM et sélectionnez la variable **[!UICONTROL Avancé]** . Activez la variable **[!UICONTROL Utilisation au-dessus de l’instance AEM en tant que bibliothèque de ressources partagées]** .

   ![](assets/aem_authoring_9.png)

1. Dans la **Image** , accédez au **[!UICONTROL Sélectionner une ressource partagée]** .

   ![](assets/aem_authoring_10.png)

1. Dans la fenêtre de sélection, sélectionnez une image parmi les **Bibliothèque Adobe Experience Manager Assets**, puis confirmez.

Votre diffusion email est prête. Vous pouvez maintenant spécifier l&#39;audience cible, confirmer la diffusion et poursuivre l&#39;envoi.
