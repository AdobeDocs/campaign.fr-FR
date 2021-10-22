---
title: Envoi d'e-mails avec Adobe Campaign
description: Prise en main des e-mails dans Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 97dcd0e0-db5b-45a4-96af-817e49f6cb64
source-git-commit: 9e07353859e63b71abb61526f40675f18837bc59
workflow-type: ht
source-wordcount: '617'
ht-degree: 100%

---

# Conception et envoi d&#39;e-mails

Les diffusions e-mail permettent d&#39;envoyer des e-mails personnalisés à la population cible.

![](../assets/do-not-localize/book.png) Apprenez-en davantage en consultant la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/about-email-channel.html?lang=fr).

## Création de votre première diffusion e-mail

Créez des e-mails personnalisés et pertinents qui sont également conformes au reste de l&#39;expérience client.

![](assets/new-email-content.png)


Dans l&#39;exemple suivant, vous découvrirez les étapes de conception d&#39;une diffusion e-mail dans Adobe Campaign contenant des données personnalisées, des liens vers une URL externe et un lien vers la page miroir.

1. **Création de la diffusion**

   Pour créer une nouvelle diffusion, accédez à l&#39;onglet **Campagnes**, cliquez sur **Diffusions** et cliquez sur le bouton **Créer** au-dessus de la liste des diffusions existantes.

   ![](assets/delivery_step_1.png)

1. **Sélection du modèle**

   Sélectionnez un modèle de diffusion, puis nommez votre diffusion. Ce nom sera visible uniquement par les utilisateurs de la console Adobe Campaign et non par vos destinataires mais cet intitulé s&#39;affichera dans la liste de vos diffusions. Cliquez sur **[!UICONTROL Continuer]**.

   ![](assets/dce_delivery_model.png)

1. **Importation de votre contenu**

   Cliquez sur l&#39;onglet **Source** pour coller votre contenu HTML.

   ![](assets/paste-content.png)


1. **Personnalisation de votre message**


   * Ajoutez les nom et prénom de vos destinataires

      Pour insérer les noms et prénoms des profils ciblés dans le contenu du message, placez le curseur à l&#39;endroit où vous souhaitez les insérer, cliquez sur la dernière icône de la barre d&#39;outils, puis cliquez sur **[!UICONTROL Inclure]** et sélectionnez **[!UICONTROL Salutations]**.

      ![](assets/include-greetings.png)

      Accédez à l&#39;onglet Aperçu pour vérifier la personnalisation en sélectionnant un destinataire.

      ![](assets/perso-check.png)

   * Insertion d&#39;un lien tracké

      Pour amener les destinataires d&#39;une diffusion vers une adresse externe via une image ou un texte, sélectionnez-la et cliquez sur l&#39;icône **[!UICONTROL Ajouter un lien]** dans la barre d&#39;outils.

      Saisissez l&#39;URL pour le lien dans le champ **URL** à l&#39;aide du format suivant **https://www.monURL.com**, puis confirmez.

      ![](assets/add-a-link.png)

   * Ajouter une page miroir

      Pour permettre à vos destinataires d&#39;accéder au contenu de votre diffusion dans un navigateur web, ajoutez un lien vers la page miroir de votre message.

      Placez le curseur à l&#39;endroit où vous souhaitez insérer ce lien, cliquez sur la dernière icône de la barre d&#39;outils, puis sur **[!UICONTROL Inclure]** et sélectionnez **[!UICONTROL Lien vers la page miroir]**.
   Une fois le contenu prêt, cliquez sur **Enregistrer** : elle s&#39;affiche désormais dans votre liste de diffusions, sous l&#39;onglet **[!UICONTROL Campagnes > Diffusions]**. Votre première diffusion e-mail est prête. Vous devez maintenant définir l&#39;audience, valider la diffusion et l&#39;envoyer.


Pour en savoir plus, consultez ces sections de la documentation de Campaign Classic v7 :

* Concevoir un e-mail dans Campaign
   ![](../assets/do-not-localize/book.png) [Découvrez comment concevoir un e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/defining-the-email-content.html?lang=fr)
* Importation d&#39;un contenu d&#39;e-mail
   ![](../assets/do-not-localize/book.png) [Cas pratique : créer un workflow pour charger un contenu de diffusion](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/loading-delivery-content.html?lang=fr)
* Créer et utiliser un modèle d&#39;e-mail
   ![](../assets/do-not-localize/book.png) [En savoir plus sur les modèles d&#39;e-mails](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=fr)
* Sélectionner l&#39;audience de votre e-mail
   ![](../assets/do-not-localize/book.png) [En savoir plus sur la définition de la population cible](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html?lang=fr)
* Valider une diffusion et envoyer des BAT
   ![](../assets/do-not-localize/book.png) [En savoir plus sur les étapes clés de validation d&#39;une diffusion](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=fr)
* Ajout [d&#39;adresses de contrôle](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html?lang=fr)

## Test et validation de vos e-mails

Campaign propose plusieurs méthodes permettant de tester et valider vos e-mails avant de les envoyer à vos audiences.

[ ![](../assets/do-not-localize/book.png)Appliquer les bonnes pratiques répertoriées dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/check-before-sending.html?lang=fr)

Vous pouvez ainsi :

* Vérifier les logs d&#39;analyses de diffusion
* Envoi de BAT
* Ajouter des adresses de contrôle
* Utiliser des populations témoins
* Vérifier le rendu des e-mails

![](../assets/do-not-localize/book.png) [Apprenez-en davantage en consultant la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=fr).

## Surveillance de vos e-mails

Une fois les messages envoyés, vérifiez l&#39;état de votre diffusion dans le tableau de bord des diffusions et accédez aux logs de diffusion et aux rapports pour confirmer que vos messages ont été correctement envoyés.

![](../assets/do-not-localize/book.png) [Apprenez-en davantage en consultant la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html?lang=fr).
