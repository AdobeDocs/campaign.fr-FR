---
product: Adobe Campaign
title: Envoi d’e-mails avec Adobe Campaign
description: Prise en main des e-mails dans Campaign
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
source-git-commit: e65750c4e9ebd0367f0430455cac2cc6502ade7e
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 38%

---

# Conception et envoi d’e-mails

Les diffusions e-mail permettent d’envoyer des e-mails personnalisés à la population cible.

[!DNL :arrow_upper_right:] Pour en savoir plus, consultez la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/about-email-channel.html?lang=fr).

## Création de votre première diffusion e-mail

Créez des e-mails personnalisés et pertinents qui sont également conformes au reste de l’expérience client.

![](assets/new-email-content.png)


Dans l&#39;exemple suivant, vous découvrirez les étapes de conception d&#39;une diffusion email dans Adobe Campaign contenant des données personnalisées, des liens vers une URL externe et un lien vers la page miroir.

1. **Créer la diffusion**

   Pour créer une nouvelle diffusion, accédez à l&#39;onglet **Campagnes**, cliquez sur **Diffusions** et cliquez sur le bouton **Créer** au-dessus de la liste des diffusions existantes.

   ![](assets/delivery_step_1.png)

1. **Sélectionner le modèle**

   Sélectionnez un modèle de diffusion, puis nommez votre diffusion. Ce nom sera visible uniquement par les utilisateurs de la console Adobe Campaign et non par vos destinataires mais cet intitulé s&#39;affichera dans la liste de vos diffusions. Cliquez sur **[!UICONTROL Continuer]**.

   ![](assets/dce_delivery_model.png)

1. **Importez votre contenu**

   Cliquez sur l’onglet **Source** pour coller votre contenu HTML.

   ![](assets/paste-content.png)


1. **Personnaliser votre message**


   * Ajouter les prénoms et les noms de vos destinataires

      Pour insérer les prénoms et noms des profils ciblés dans le contenu du message, placez le curseur à l’endroit où vous souhaitez les insérer, cliquez sur la dernière icône de la barre d’outils, puis cliquez sur **[!UICONTROL Inclure]** et sélectionnez **[!UICONTROL Salutations]**.

      ![](assets/include-greetings.png)

      Accédez à l&#39;onglet Aperçu pour vérifier la personnalisation en sélectionnant un destinataire.

      ![](assets/perso-check.png)

   * Insérer un lien tracké

      Pour amener les destinataires d&#39;une diffusion vers une adresse externe via une image ou un texte, sélectionnez-la et cliquez sur l&#39;icône **[!UICONTROL Ajouter un lien]** dans la barre d&#39;outils.

      Saisissez l&#39;URL pour le lien dans le champ **URL** à l&#39;aide du format suivant **https://www.monURL.com**, puis confirmez.

      ![](assets/add-a-link.png)

   * Ajouter une page miroir

      Pour permettre à vos destinataires de visualiser le contenu de votre diffusion dans un navigateur web, ajoutez un lien vers la page miroir de votre message.

      Placez le curseur à l’endroit où vous souhaitez insérer ce lien, cliquez sur la dernière icône de la barre d’outils, puis sur **[!UICONTROL Inclure]** et sélectionnez **[!UICONTROL lien vers la page miroir]**.
   Une fois le contenu prêt, cliquez sur **Enregistrer** : elle s&#39;affiche désormais dans votre liste de diffusions, sous l&#39;onglet **[!UICONTROL Campagnes > Diffusions]**. Votre première diffusion email est prête. Vous devez maintenant définir l&#39;audience, valider la diffusion et l&#39;envoyer.


Pour en savoir plus, consultez ces sections de la documentation de Campaign Classic v7 :

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

Une fois l&#39;envoi effectué, vérifiez le statut de la diffusion dans le tableau de bord de la diffusion et accédez aux logs et aux rapports de diffusion pour confirmer l&#39;envoi correct des messages.

[!DNL :arrow_upper_right:] [En savoir plus dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html?lang=fr)

