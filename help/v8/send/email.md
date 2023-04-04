---
title: Envoyer des e-mails avec Adobe Campaign
description: Commencez à utiliser les e-mails dans Adobe Campaign. Envoyez des e-mails personnalisés à une population cible.
feature: Email
role: User
level: Beginner
exl-id: 97dcd0e0-db5b-45a4-96af-817e49f6cb64
source-git-commit: 1baeb8827a0eab4f9487bb5e5afe4d779e00efe4
workflow-type: ht
source-wordcount: '479'
ht-degree: 100%

---

# Concevoir et envoyer des e-mails

Les diffusions e-mail permettent d’envoyer des e-mails personnalisés à la population cible. [En savoir plus](../send/send.md).

## Création de votre première diffusion e-mail

Créez des e-mails personnalisés et pertinents qui sont également conformes au reste de l&#39;expérience client.

![](assets/new-email-content.png)


Dans l&#39;exemple suivant, vous découvrirez les étapes de conception d&#39;une diffusion e-mail dans Adobe Campaign contenant des données personnalisées, des liens vers une URL externe et un lien vers la page miroir.

1. **Création de la diffusion**

   Pour créer une nouvelle diffusion, accédez à l&#39;onglet **Campagnes**, cliquez sur **Diffusions** et cliquez sur le bouton **Créer** au-dessus de la liste des diffusions existantes.

   ![](assets/delivery_step_1.png)

1. **Sélection du modèle**

   Sélectionnez un modèle de diffusion, puis nommez votre diffusion. Ce nom sera visible uniquement par les utilisateurs de la console Adobe Campaign et non par vos destinataires mais cet intitulé s&#39;affichera dans la liste de vos diffusions. Cliquez sur **[!UICONTROL Continuer]**.

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

      En savoir plus sur les options de personnalisation dans [cette section](personalize.md).

   * Insertion d&#39;un lien tracké

      Pour amener les destinataires d&#39;une diffusion vers une adresse externe via une image ou un texte, sélectionnez-la et cliquez sur l&#39;icône **[!UICONTROL Ajouter un lien]** dans la barre d&#39;outils.

      Saisissez l&#39;URL pour le lien dans le champ **URL** à l&#39;aide du format suivant **https://www.monURL.com**, puis confirmez.

      ![](assets/add-a-link.png)

   * Ajouter une page miroir

      Pour permettre à vos destinataires d’accéder au contenu de votre diffusion dans un navigateur web, ajoutez un lien vers la [page miroir](../send/mirror-page.md) de votre message.

      Placez le curseur à l&#39;endroit où vous souhaitez insérer ce lien, cliquez sur la dernière icône de la barre d&#39;outils, puis sur **[!UICONTROL Inclure]** et sélectionnez **[!UICONTROL Lien vers la page miroir]**.
   Une fois le contenu prêt, cliquez sur **Enregistrer** : elle s&#39;affiche désormais dans votre liste de diffusions, sous l&#39;onglet **[!UICONTROL Campagnes > Diffusions]**. Votre première diffusion e-mail est prête. Vous devez maintenant définir l&#39;audience, valider la diffusion et l&#39;envoyer.


Découvrez comment importer un contenu d’e-mail dans ce [cas d’utilisation](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/load-delivery-content.html?lang=fr).

En savoir plus dans les sections suivantes :

* [Concevoir un e-mail dans Campaign](../send/email.md)
* [Créer et utiliser un modèle d’e-mail](../send/create-templates.md)
* [Sélectionner l’audience de votre e-mail](../audiences/gs-audiences.md)
* [Valider une diffusion et envoyer des BAT](../send/preview-and-proof.md)

## Tester et valider vos e-mails

Campaign propose plusieurs méthodes permettant de tester et valider vos e-mails avant de les envoyer à vos audiences. Découvrez comment prévisualiser et tester le contenu de votre e-mail sur [cette page](../send/preview-and-proof.md).

Vous pouvez ainsi :

* Vérifier les logs d&#39;analyses de diffusion
* Envoi de BAT
* Ajouter des adresses de contrôle

[En savoir plus](../send/delivery-analysis.md)
