---
product: Adobe Campaign
title: Envoi d’e-mails avec Adobe Campaign
description: Prise en main des e-mails dans Campaign
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
source-git-commit: d1e96b1311d9de24ceb918230186cd3cad609ab2
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 76%

---

# Conception et envoi d’e-mails

Les diffusions e-mail permettent d’envoyer des e-mails personnalisés à la population cible.

[!DNL :arrow_upper_right:] Pour en savoir plus, consultez la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/about-email-channel.html?lang=fr).

## Création de votre première diffusion e-mail

Créez des e-mails personnalisés et pertinents qui sont également conformes au reste de l’expérience client.

![](assets/new-email-content.png)

[!DNL :arrow_upper_right:] [Découvrez comment créer une diffusion email dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/editing-html-content/use-case--creating-an-email-delivery.html?lang=fr)


Dans l&#39;exemple suivant, vous découvrirez les étapes de conception d&#39;une diffusion email dans Adobe Campaign contenant des données personnalisées, des liens vers une URL externe, un lien vers la page miroir et un lien vers un formulaire web.

1. Créer la diffusion

   Pour créer une nouvelle diffusion, accédez à l&#39;onglet **Campagnes**, cliquez sur **Diffusions** et cliquez sur le bouton **Créer** au-dessus de la liste des diffusions existantes.

   ![](assets/delivery_step_1.png)

1. Sélectionner le modèle

   Sélectionnez un modèle de diffusion, puis nommez votre diffusion. Ce nom sera visible uniquement par les utilisateurs de la console Adobe Campaign et non par vos destinataires mais cet intitulé s&#39;affichera dans la liste de vos diffusions. Cliquez sur **[!UICONTROL Continuer]**.

   ![](assets/dce_delivery_model.png)

1. Importez votre contenu

   Cliquez sur l’onglet **Source** pour coller votre contenu HTML.

   ![](assets/paste-content.png)


1. Personnaliser votre message


   * Afficher les nom et prénom de vos destinataires

      Pour qu&#39;un champ texte de votre diffusion contienne les noms et prénoms de vos destinataires, cliquez sur le champ texte de votre choix, puis positionnez le curseur à l&#39;endroit exact où vous souhaitez les afficher. Cliquez sur la première icône de la barre d&#39;outils contextuelle, puis sur **[!UICONTROL Bloc de personnalisation]**. Sélectionnez **[!UICONTROL Salutations]**, puis cliquez sur **[!UICONTROL OK]**.

   * Insérer un lien sur une image

      Afin de permettre aux destinataires de vos diffusions de se rendre sur une adresse externe depuis une image, cliquez sur l&#39;image concernée afin d&#39;afficher la barre d&#39;outils contextuelle, positionnez le curseur sur la première icône, puis cliquez sur **[!UICONTROL Lien vers une URL externe]**.

      Saisissez l&#39;URL pour le lien dans le champ **URL** à l&#39;aide du format suivant **https://www.monURL.com**, puis confirmez.

      L&#39;adresse du lien est modifiable à tout moment dans la partie droite de la fenêtre.

   * Insérer un lien sur du texte

      Afin d&#39;intégrer au texte de votre diffusion un lien vers une URL externe, sélectionnez du texte ou un bloc de texte, puis cliquez sur la première icône de la barre d&#39;outils contextuelle. Cliquez sur **[!UICONTROL Lien vers une URL externe]**, saisissez l’adresse de destination du lien dans le champs **[!UICONTROL URL]**.

      L&#39;adresse du lien est modifiable à tout moment dans la partie droite de la fenêtre.

   * Ajouter une page miroir

      Pour permettre à vos destinataires d&#39;accéder au contenu de votre diffusion sur un navigateur Web, il vous est possible d&#39;intégrer à votre diffusion un lien vers une page Web miroir.

      Cliquez sur le champ texte dans lequel vous souhaitez voir figurer le lien vers la page miroir. Cliquez sur la première icône de la barre d&#39;outils contextuelle, sélectionnez **[!UICONTROL Bloc de personnalisation]**, puis **[!UICONTROL Lien vers la page miroir (MirrorPage)]**. Validez en cliquant sur **[!UICONTROL Enregistrer]**.

   * Intégrer un lien vers une application Web

      Le Digital Content Editor vous permet d&#39;intégrer des liens vers les applications Web de votre console Adobe Campaign, telles qu&#39;une landing page ou une page de formulaire. Voir à ce sujet la section [Lien vers une application web](../../web/using/editing-content.md#link-to-a-web-application).

      Sélectionnez un champ texte dans lequel figurera votre lien vers l&#39;application Web, puis cliquez sur la première icône. Choisissez **[!UICONTROL Lien vers une application Web]**, puis sélectionnez l&#39;application souhaitée en cliquant sur l&#39;icône située à la fin du champ **Application Web**.

1. Envoyer les messages

   Une fois le contenu intégré, enregistrez la diffusion en cliquant sur **Enregistrer**. Elle s’affichera désormais dans votre liste de diffusions, sous l’onglet **[!UICONTROL Campagnes > Diffusions]**.


## Créer du contenu et sélectionner l&#39;audience

Vous pouvez la créer directement dans Campaign ou importer votre audience ainsi que votre contenu e-mail. Suivez les liens ci-dessous pour découvrir comment :

* Concevoir un email dans Campaign
   [!DNL :arrow_upper_right:] [Découvrez comment concevoir un email](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/defining-the-email-content.html?lang=fr)
* Importation d’un contenu d’email
   [!DNL :arrow_upper_right:] [Cas pratique : Créer un workflow pour charger un contenu de diffusion](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/loading-delivery-content.html?lang=fr)
* Créer et utiliser un modèle d&#39;email
   [!DNL :arrow_upper_right:] [En savoir plus sur les modèles d&#39;email](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=fr)
* Sélectionner l&#39;audience de votre email
   [!DNL :arrow_upper_right:] [Découvrez comment définir la population cible](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html?lang=fr)
* Valider une diffusion et envoyer des BAT
   [!DNL :arrow_upper_right:] [Découvrez les étapes clés de validation d&#39;une diffusion](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=fr)
* Ajout [d’adresses de contrôle](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html?lang=fr)

## Test et validation de vos e-mails

Campaign propose plusieurs méthodes permettant de tester et valider vos e-mails avant de les envoyer à vos audiences.

[!DNL :arrow_upper_right:] [Appliquer les bonnes pratiques répertoriées dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/check-before-sending.html?lang=fr)

Vous pouvez ainsi :

* Vérifier les logs d’analyses de diffusion
* Envoi de BAT
* Ajouter des adresses de contrôle
* Utiliser des populations témoins
* Vérifier le rendu des e-mails

[!DNL :arrow_upper_right:] [En savoir plus dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html)

## Surveillance de vos e-mails

Une fois les messages envoyés, vérifiez l’état de votre diffusion dans le tableau de bord des diffusions et accédez aux logs de diffusion et aux rapports pour confirmer que vos messages ont été correctement envoyés.

[!DNL :arrow_upper_right:] [En savoir plus dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html?lang=fr)

