---
product: campaign
title: 'Cas d’utilisation : créer une diffusion e-mail'
description: 'Cas d’utilisation : créer une diffusion e-mail'
feature: Web Apps, Web Forms, Landing Pages, Email Design
version: Campaign v8, Campaign Classic v7
exl-id: e2679f12-459b-466d-9c82-60a28363b104
TQID: 'https://experienceleague.adobe.com/5j2bwBpCx4WAyHD4jyypi5EMhw3NS-11-HkoTQ9AnU4'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
  - id: b631758a-142d-425f-b9aa-f756d85cb979
    internal-label: Campaign Email Designer
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: f391046b-0cf3-4e76-bd3b-97fe06654506
    internal-label: Web Apps
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
  - id: d7be2b01-dc9c-40f7-aace-a151707504ed
    internal-label: Landing pages
  - id: e739ee2b-6228-412e-878f-45de0791417d
    internal-label: Use cases
  - id: c8da4fdd-eb94-4751-a43c-f82733fb2d6e
    internal-label: Email design
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: d3b34546c1b08190772154efe6f818b98cc1094c
workflow-type: tm+mt
source-wordcount: '915'
ht-degree: 79%
---
# Cas d’utilisation : création d’une diffusion email{#use-case-creating-an-email-delivery}



Dans ce cas d’utilisation, vous apprendrez les étapes de conception d’une diffusion e-mail à l’aide du Digital Content Editor (DCE) d’Adobe Campaign.

Notre objectif final est d&#39;obtenir une diffusion partant d&#39;un modèle personnalisé contenant :

* une adresse directe au destinataire (utilisant ses nom et prénom),
* deux types de liens vers une URL externe,
* une page miroir,
* un lien vers une application web.

>[!NOTE]
>
>Avant de commencer, vous devez avoir en votre possession au moins un **modèle HTML** prêt à héberger le contenu de vos futures diffusions.
>
>Dans les **[!UICONTROL Propriétés]** de diffusion, vérifiez que le **[!UICONTROL Mode d’édition du contenu]** (dans l’onglet **[!UICONTROL Avancé]**) est défini sur **[!UICONTROL DCE]**. Pour garantir le fonctionnement optimal de l’éditeur, consultez les [Bonnes pratiques relatives à l’édition de contenu](content-editing-best-practices.md).

## Etape 1 - Créer une diffusion {#step-1---creating-a-delivery}

Pour créer une diffusion, placez le curseur dans l’onglet **Campagnes** et cliquez sur **Diffusions**. Cliquez ensuite sur le bouton **Créer** au-dessus de la liste des diffusions existantes. Pour plus d’informations sur la création de diffusions, consultez [cette page](https://experienceleague.adobe.com/fr/docs/campaign-classic/using/sending-messages/about-email-channel){target="_blank"}.

![Liste des diffusions dans l&#39;onglet Campagnes avec le bouton Créer utilisé pour démarrer une nouvelle diffusion.](assets/delivery_step_1.png)

## Etape 2 - Sélectionner un modèle {#step-2---selecting-a-template}

Sélectionnez un modèle de diffusion et nommez votre diffusion. Ce nom sera visible uniquement par les utilisateurs de la console Adobe Campaign et non par vos destinataires ; toutefois, cet en-tête s&#39;affichera dans votre liste de diffusions. Cliquez sur **[!UICONTROL Continuer]**.

![Boîte de dialogue de création de diffusion avec le modèle de diffusion E-mail, un champ Libellé et le bouton Continuer.](assets/dce_delivery_model.png)

## Etape 3 - Sélection du contenu {#step-3---selecting-a-content}

Le Digital Content Editor est livré avec plusieurs modèles d&#39;usine aux structures variables (colonnes, zones de textes, etc.).

Sélectionnez le modèle de contenu qui vous convient, puis cliquez sur le bouton **[!UICONTROL Commencer avec le contenu sélectionné]** afin d’afficher le modèle dans la diffusion créée.

![Étape de contenu de la diffusion répertoriant les modèles de contenu avec le bouton Commencer par le contenu sélectionné.](assets/dce_select_model.png)

Vous pouvez également importer du contenu HTML créé en dehors d’Adobe Campaign en sélectionnant **[!UICONTROL À partir d’un fichier]**.

![Modèles de contenu disponibles avec l’option À partir d’un fichier mise en surbrillance.](assets/dce_select_from_file_template.png)

Vous pouvez enregistrer ce contenu en tant que modèle pour une réutilisation ultérieure. Lorsqu’un modèle de contenu personnalisé est créé, son aperçu figure dans la liste des modèles. Voir à ce sujet la section [Gestion des modèles](template-management.md).

>[!CAUTION]
>
>Si vous utilisez l&#39;**interface web d&#39;Adobe Campaign**, vous devez importer un fichier .zip comportant le contenu HTML et les images associées.

## Etape 4 - Concevoir le message {#step-4---designing-the-message}

* Afficher les nom et prénom de vos destinataires

  Pour qu’un champ texte de votre diffusion contienne les noms et prénoms de vos destinataires, cliquez sur le champ texte de votre choix, puis positionnez le curseur à l’endroit exact où vous souhaitez les afficher. Cliquez sur la première icône de la barre d’outils pop-up, puis sur **[!UICONTROL Bloc de personnalisation]**. Sélectionnez **[!UICONTROL Salutations]**, puis cliquez sur **[!UICONTROL OK]**.

  ![Insérez une boîte de dialogue d&#39;élément avec le bloc de personnalisation Salutations sélectionné, ouvert à partir du menu de la barre d&#39;outils.](assets/dce_personalizationblock_greetings.png)

* Insérer un lien sur une image

  Afin de permettre aux destinataires de vos diffusions de se rendre sur une adresse externe depuis une image, cliquez sur l’image concernée afin d’afficher la barre d’outils pop-up, positionnez le curseur sur la première icône, puis cliquez sur **[!UICONTROL Lien vers une URL externe]**. Voir à ce sujet la section [Ajouter un lien](editing-content.md#adding-a-link).

  ![Menu de la barre d&#39;outils Image avec l&#39;option Lier vers une URL externe sélectionnée.](assets/dce_externalpage.png)

  Saisissez l&#39;URL pour le lien dans le champ **URL** à l&#39;aide du format suivant **https://www.monURL.com**, puis confirmez.

  L&#39;adresse du lien est modifiable à tout moment dans la partie droite de la fenêtre.

* Insérer un lien sur du texte

  Afin d’intégrer au texte de votre diffusion un lien vers une URL externe, sélectionnez du texte ou un bloc de texte, puis cliquez sur la première icône de la barre d’outils pop-up. Cliquez sur **[!UICONTROL Lien vers une URL externe]**, saisissez l’adresse de destination du lien dans le champs **[!UICONTROL URL]**. Pour plus d’informations, voir [Ajout d’un lien](editing-content.md#adding-a-link).

  L&#39;adresse du lien est modifiable à tout moment dans la partie droite de la fenêtre.

  >[!CAUTION]
  >
  >Le texte saisi dans le champ **[!UICONTROL Libellé]** remplace le texte initial.

* Ajouter une page miroir

  Pour permettre à vos destinataires d&#39;accéder au contenu de votre diffusion sur un navigateur Web, il vous est possible d&#39;intégrer à votre diffusion un lien vers une page Web miroir.

  Cliquez sur le champ texte dans lequel vous souhaitez voir figurer le lien vers la page miroir. Cliquez sur la première icône de la barre d’outils pop-up, sélectionnez **[!UICONTROL Bloc de personnalisation]**, puis **[!UICONTROL Lien vers la page miroir (MirrorPage)]**. Cliquez sur **[!UICONTROL Enregistrer]** pour confirmer.

  ![Menu de la barre d&#39;outils dans l&#39;éditeur de texte avec l&#39;option du bloc Personalization sélectionnée.](assets/dce_mirrorpage.png)

  >[!CAUTION]
  >
  >Le libellé du bloc de personnalisation remplace automatiquement le texte intial inscrit dans votre diffusion.

* Intégrer un lien vers une application Web

  Le Digital Content Editor vous permet d&#39;intégrer des liens vers les applications Web de votre console Adobe Campaign, telles qu&#39;une landing page ou une page de formulaire. Voir à ce sujet la section [Lien vers une application web](editing-content.md#link-to-a-web-application).

  Sélectionnez un champ texte dans lequel figurera votre lien vers l&#39;application Web, puis cliquez sur la première icône. Choisissez **[!UICONTROL Lien vers une application Web]**, puis sélectionnez l&#39;application souhaitée en cliquant sur l&#39;icône située à la fin du champ **Application Web**.

  ![Insérez une boîte de dialogue de lien avec les champs Libellé et Application web, ainsi qu&#39;un bouton OK.](assets/dce_webapp.png)

  Cliquez sur **Enregistrer** pour valider.

  >[!NOTE]
  >
  >Cette étape nécessite l&#39;enregistrement préalable d&#39;au moins une application web. Vous trouverez ces informations dans l’onglet **[!UICONTROL Campagnes > Applications web]** de votre console.

## Etape 5 - Enregistrer la diffusion {#step-5---saving-the-delivery}

Une fois le contenu intégré, enregistrez la diffusion en cliquant sur **Enregistrer**. Elle s’affichera désormais dans votre liste de diffusions, sous l’onglet **[!UICONTROL Campagnes > Diffusions]**.
