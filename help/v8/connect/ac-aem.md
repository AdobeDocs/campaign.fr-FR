---
title: Utiliser Campaign et Adobe Experience Manager
description: Découvrez comment utiliser Campaign et Adobe Experience Manager
feature: Experience Manager Integration
role: Admin, User
level: Beginner
exl-id: e83893f7-a8be-48a3-a7a6-aced7b4d4f69
TQID: 'https://experienceleague.adobe.com/LM635Kjl7bucy1SMcEPuhCElUI7MNrO4B3fwo9fpyFQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: df0d6518-6f49-46e2-b46e-3bcc513f553f
    internal-label: Experience Manager integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: df8d8e17c486122e23a6db0e44263f9f9632a204
workflow-type: tm+mt
source-wordcount: '928'
ht-degree: 77%
---
# Utiliser Campaign et Adobe Experience Manager {#ac-aem}

L&#39;intégration entre Adobe Campaign et Adobe Experience Manager vous permet de gérer le contenu de vos diffusions email, ainsi que vos formulaires directement dans Adobe Experience Manager.

[Découvrez comment modifier votre contenu Adobe Experience Manager as a Cloud Service dans l’interface de Campaign Web](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-content.html?lang=fr){target="_blank"}.

[En savoir plus sur Adobe Experience Manager dans ce document](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignonpremise.html?lang=fr#aem-and-adobe-campaign-integration-workflow){target="_blank"}.


>[!NOTE]
>
>En tant qu’utilisateur ou utilisatrice Managed Cloud Services, [contactez Adobe](../start/campaign-faq-comprehensive.md#support) pour intégrer Adobe Experience Manager à Campaign.

## Importer le contenu à partir d’Adobe Experience Manager {#integrating-with-aem}

Cette intégration peut être utilisée, par exemple, pour créer une newsletter dans Adobe Experience Manager, qui sera ensuite utilisée dans le cadre d’une campagne e-mail dans Adobe Campaign.

**Depuis Adobe Experience Manager :**

1. Accédez à l’instance de création [!DNL Adobe Experience Manager] et cliquez sur Adobe Experience dans le coin supérieur gauche de la page. Sélectionnez **[!UICONTROL Sites]** dans le menu.

   ![Menu de navigation de Adobe Experience Manager avec l’option Sites mise en surbrillance](assets/aem_authoring_1.png)

1. Accédez à **[!UICONTROL Campagnes > Nom de votre marque (we.Shopping, dans le cas présent) > Zone principale > E-mail]**.

1. Cliquez sur **[!UICONTROL Créer]** et sélectionnez **[!UICONTROL Page]** dans le menu déroulant.

   ![Dossier d’e-mail AEM Sites avec le menu Créer ouvert et Page sélectionnée](assets/aem_authoring_2.png)

1. Sélectionnez le modèle **[!UICONTROL E-mail Adobe Campaign]** et nommez votre newsletter.

1. Une fois votre page créée, accédez au menu **[!UICONTROL Informations sur la page]**, puis cliquez sur **[!UICONTROL Ouvrir les propriétés]**.

   ![Éditeur de page de newsletter avec le menu Informations sur la page ouvert et Ouvrir les propriétés mis en surbrillance](assets/aem_authoring_3.png)

1. Personnalisez le contenu de votre e-mail en ajoutant des composants, comme des champs de personnalisation depuis Adobe Campaign. En savoir plus dans la [documentation d’Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-65/content/sites/authoring/aem-adobe-campaign/campaign.html?lang=fr#editing-email-content){target="_blank"}.

1. Lorsque votre e-mail est prêt, accédez au menu **[!UICONTROL Informations sur la page]**, puis cliquez sur **[!UICONTROL Démarrer le workflow]**.

   ![Éditeur de page de newsletter avec le menu Informations sur la page ouvert et le workflow Démarrer mis en surbrillance](assets/aem_authoring_4.png)

1. Dans la première liste déroulante, sélectionnez **[!UICONTROL Approuver Adobe Campaign]** en tant que modèle de workflow, puis cliquez sur **[!UICONTROL Démarrer le workflow]**.

   ![Démarrer la boîte de dialogue Workflow avec Approuver pour Adobe Campaign sélectionnée comme modèle de workflow](assets/aem_authoring_5.png)

1. Une clause de non-responsabilité s’affiche en haut de la page et indique : `This page is subject to the workflow Approve for Adobe Campaign`. Cliquez sur **[!UICONTROL Terminer]** en regard de la clause de non-responsabilité pour confirmer son examen, puis sélectionnez **[!UICONTROL OK]**.

1. Cliquez à nouveau sur **[!UICONTROL Terminé]**, puis sélectionnez **[!UICONTROL Approbation de la newsletter]** dans la liste déroulante **[!UICONTROL Étape suivante]**.

   ![Boîte de dialogue Terminer l’élément de travail avec l’approbation de la newsletter sélectionnée dans la liste Étape suivante et bouton OK](assets/aem_authoring_6.png)

Votre newsletter est maintenant prête et synchronisée dans Adobe Campaign.

**Depuis Adobe Campaign :**

1. Dans l&#39;onglet **[!UICONTROL Campagnes]**, cliquez sur **[!UICONTROL Diffusions]** et sur **[!UICONTROL Créer]**.

1. Choisissez le modèle **[!UICONTROL Diffusion e-mail avec contenu AEM (mailAEMContent)]** dans le menu déroulant **[!UICONTROL Modèle de diffusion]**.

   ![Liste de modèles de diffusion Campaign avec diffusion par e-mail avec contenu AEM (mailAEMContent) sélectionné](assets/aem_authoring_7.png)

1. Ajoutez un **[!UICONTROL Libellé]** à votre diffusion, puis cliquez sur **[!UICONTROL Continuer]**.

1. Cliquez sur **[!UICONTROL Synchroniser]** pour accéder à vos diffusions AEM.

   Si le bouton n’est pas visible dans votre interface, accédez au bouton **[!UICONTROL Propriétés]** et sélectionnez l’onglet **[!UICONTROL Avancé]**. Assurez-vous que le champ **[!UICONTROL Mode de modification du contenu]** est configuré sur **[!UICONTROL AEM]** et saisissez les détails de votre instance AEM dans le champ **[!UICONTROL Compte AEM]**.

   ![Barre d&#39;outils de diffusion e-mail de Campaign avec le bouton Synchroniser mis en surbrillance](assets/aem_authoring_8.png)

1. Sélectionnez la diffusion AEM précédemment créée dans [!DNL Adobe Experience Manager] et confirmez en cliquant sur **[!UICONTROL Ok]**.

   ![La boîte de dialogue Synchroniser avec du contenu AEM répertorie les e-mails AEM approuvés avec la ligne Newsletter sélectionnée](assets/aem_authoring_11.png)

1. Assurez-vous de cliquer sur le bouton **[!UICONTROL Actualiser le contenu]** chaque fois que des modifications sont apportées à votre diffusion AEM.

   ![Diffusion e-mail synchronisée avec le bouton Actualiser le contenu en surbrillance et le bouton Désynchroniser](assets/aem_authoring_12.png)

1. Pour supprimer la connexion entre Experience Manager et Campaign, cliquez sur **[!UICONTROL Désynchroniser]**.

Votre e-mail est maintenant prêt à être envoyé à votre audience.

## Importer des ressources à partir de la bibliothèque Adobe Experience Manager Assets {#assets-library}

En outre, vous pouvez directement insérer des ressources provenant de votre [!DNL Adobe Experience Manager Assets Library] tout en modifiant un e-mail ou une page de destination dans Adobe Campaign. Cette fonctionnalité est présentée dans la [documentation d’Adobe Experience Manager Assets](https://experienceleague.adobe.com/docs/experience-manager-65/content/assets/managing/manage-assets.html?lang=fr){target="_blank"}.

**Depuis Adobe Experience Manager :**

1. Accédez à l’instance de création [!DNL Adobe Experience Manager] et cliquez sur Adobe Experience dans le coin supérieur gauche de la page. Sélectionnez **[!UICONTROL Ressources]** `>` **[!UICONTROL Fichiers]** dans le menu.

   ![Menu de navigation d’AEM Assets avec l’option Fichiers mise en surbrillance](assets/aem_assets_1.png)

1. Cliquez sur **Créer**, puis sur **Fichiers** pour importer votre ressource dans la **Bibliothèque Adobe Experience Manager Assets**. En savoir plus dans la [documentation d’Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-65/content/assets/managing/manage-assets.html?lang=fr#uploading-assets){target="_blank"}.

   Vue ![Fichiers AEM Assets avec le menu Créer ouvert et Fichiers sélectionnés pour charger une ressource](assets/aem_assets_2.png)

1. Si nécessaire, renommez votre ressource en sélectionnant **Charger**.

Votre ressource est maintenant chargée dans votre **bibliothèque Adobe Experience Manager Assets**.

**Depuis Adobe Campaign :**

1. Dans Adobe Campaign, créez une nouvelle diffusion en accédant à l’onglet **Campagnes**, cliquez sur **Diffusions**, puis sur le bouton **Créer** au-dessus de la liste des diffusions existantes.

   ![Liste des diffusions de campagne dans l&#39;onglet Campagnes avec le bouton Créer en surbrillance](assets/aem_assets_3.png)

1. Sélectionnez un **modèle de diffusion** et nommez votre diffusion.

1. Définissez et personnalisez le contenu du message. [En savoir plus](../send/email.md)

1. Pour utiliser la **bibliothèque Adobe Experience Manager Assets**, accédez aux **[!UICONTROL Propriétés]** de votre diffusion AEM et sélectionnez l’onglet **[!UICONTROL Avancé]**.

   Choisissez votre **compte AEM** et activez l’option **[!UICONTROL Utiliser l’instance AEM ci-dessus en tant que bibliothèque de ressources partagées]**.

   ![Onglet Avancé des propriétés de diffusion avec l’option de définition de compte AEM et de bibliothèque de ressources partagées activée](assets/aem_authoring_9.png)

1. Dans l’icône **Image**, accédez au menu **[!UICONTROL Sélectionner une ressource partagée]**.

   ![Menu d’image de l’éditeur d’e-mail de Campaign avec Sélectionner une ressource partagée en surbrillance](assets/aem_assets_4.png)

1. Dans la fenêtre de sélection, sélectionnez une image dans votre **bibliothèque Adobe Experience Manager Assets**, puis choisissez **Sélectionner**.

   ![Sélectionnez une fenêtre de ressource partagée répertoriant les fichiers de bibliothèque AEM Assets avec jogging-newsletter.jpg sélectionné](assets/aem_assets_5.png)

Votre ressource est maintenant chargée dans votre diffusion par e-mail. Vous pouvez maintenant spécifier l’audience cible, confirmer la diffusion et poursuivre l’envoi.
