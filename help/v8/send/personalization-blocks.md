---
title: Utiliser des blocs de personnalisation
description: Découvrez comment utiliser des blocs de personnalisation intégrés dans le contenu de votre message
feature: Personalization
role: User
level: Beginner
source-git-commit: badcbb83c4bd0cf509c156557f5ea6f7cf7ae771
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Utiliser des blocs de personnalisation{#personalization-blocks}

Les blocs de personnalisation sont un contenu dynamique qui contient un rendu spécifique que vous pouvez insérer dans vos diffusions. Vous pouvez par exemple ajouter un logo, un message de salutations ou un lien vers une page miroir.

Pour accéder aux blocs de contenu personnalisés, accédez au **[!UICONTROL Ressources > Campaign Management > Blocs de personnalisation]** de l’explorateur. Les blocs de personnalisation intégrés sont répertoriés dans [cette section](#ootb-personalization-blocks).

Vous pouvez également définir de nouveaux blocs pour optimiser la personnalisation de vos diffusions. [En savoir plus](#create-custom-personalization-blocks).

## Insertion de blocs de personnalisation {#insert-personalization-blocks}

Pour insérer un bloc de personnalisation dans un message, procédez comme suit :

1. Dans l&#39;éditeur de contenu de l&#39;assistant de diffusion, cliquez sur l&#39;icône de personnalisation et sélectionnez le **[!UICONTROL Inclure]** .
1. Sélectionnez un bloc de personnalisation dans la liste ou cliquez sur le bouton **[!UICONTROL Autre...]** pour accéder à la liste complète.

   ![](assets/perso-content-block.png)

1. Le bloc de personnalisation est alors inséré sous forme de script. Il sera automatiquement adapté au profil du destinataire lors de la génération de la personnalisation.
1. Accédez au **[!UICONTROL Aperçu]** et sélectionnez un destinataire afin de visualiser le contenu de ce bloc pour un destinataire spécifique.

Vous pouvez inclure le code source d&#39;un bloc de personnalisation dans le contenu de la diffusion. Pour cela, cochez l&#39;option **[!UICONTROL Inclure le code source HTML du bloc]** lorsque vous le sélectionnez.

## Blocs de personnalisation intégrés {#ootb-personalization-blocks}

Les blocs de personnalisation intégrés sont les suivants :

* **[!UICONTROL Enabled by Adobe Campaign]** : insère le logo « Enabled by Adobe Campaign ».
* **[!UICONTROL Fonction de formatage d’un nom propre]** : génère la fonction JavaScript **[!UICONTROL toSmartCase]** qui convertit la première lettre de chaque mot en majuscule.
* **[!UICONTROL Salutations]**: insère des salutations avec le nom complet du destinataire, suivies d&#39;une virgule. Exemple : &quot;Bonjour John Doe&quot;.
* **[!UICONTROL Insertion du logo]** : insère un logo défini dans les paramètres de l’instance.
* **[!UICONTROL Lien vers la page miroir]**[ : insère un lien vers la page miroir](mirror-page.md). Le format par défaut est : &quot;Si vous ne parvenez pas à afficher correctement ce message, cliquez ici&quot;.
* **[!UICONTROL URL de page miroir]** : insère l’URL de page miroir qui permet aux concepteurs et conceptrices de diffusion de vérifier le lien.
* **[!UICONTROL URL d’acceptation d’une offre en mode unitaire]** : insère une URL permettant de définir une offre comme étant **[!UICONTROL Acceptée]**. (Ce bloc est disponible si le module Interaction est activé)
* **[!UICONTROL Confirmation de votre inscription]** : insère un lien permettant de confirmer l’inscription.
* **[!UICONTROL Lien d’inscription]** : insère un lien d’inscription. Ce lien est défini dans les paramètres de l’instance. Le contenu par défaut est le suivant : « Pour vous inscrire, cliquez ici. ».
* **[!UICONTROL Lien d’inscription (avec parrain)]** : insère un lien d’inscription permettant d’identifier le visiteur ou la visiteuse et la diffusion. Ce lien est défini dans les paramètres de l’instance.
* **[!UICONTROL URL de la page d’inscription]** : insère une URL d’inscription
* **[!UICONTROL Style des emails de contenu]** et **[!UICONTROL Style de notification]**: générer du code qui formate un email avec des styles de HTML prédéfinis ;
* **[!UICONTROL Lien de désinscription]** : insère un lien permettant de se désabonner de toutes les diffusions (liste bloquée). Le contenu associé par défaut est : « Vous recevez ce message car vous avez été en contact avec ***nom de votre organisation*** ou une entité associée. Pour ne plus recevoir de messages de ***nom de votre organisation***, cliquez ici. »

## Création de blocs de personnalisation personnalisés {#create-custom-personalization-blocks}

Vous pouvez définir de nouveaux blocs de contenu personnalisés à insérer à partir de l&#39;icône de personnalisation.

Pour créer un bloc de personnalisation, procédez comme suit :

1. Accédez au **[!UICONTROL Ressources > Campaign Management > Blocs de personnalisation]** dossier de l&#39;explorateur Campaign.
1. Au-dessus de la liste des blocs intégrés, cliquez sur **[!UICONTROL Nouveau]**.

   ![](assets/perso-new-block.png)

1. Renseignez le paramétrage du bloc de personnalisation :

   ![](assets/perso-custom-block.png)

   * Saisissez le libellé du bloc. Ce libellé est affiché dans la fenêtre d&#39;insertion de champs de personnalisation.
   * Sélectionnez une **Diffusion** type de contenu.
   * Activez la variable **[!UICONTROL Visible dans les menus de personnalisation]** pour rendre ce bloc accessible à partir de l&#39;icône d&#39;insertion de champs de personnalisation.
   * Si nécessaire, activez l’option **[!UICONTROL Le contenu du bloc de personnalisation dépend du format.]** pour définir deux blocs distincts pour les emails HTML et Texte.
   * Saisissez le contenu (par HTML, texte, JavaScript, etc.) du bloc de personnalisation et cliquez sur **[!UICONTROL Enregistrer]**.

Une fois enregistré, le nouveau bloc de personnalisation est disponible dans l&#39;éditeur de diffusion.

## Tutoriel vidéo {#personalization-blocks-video}

Découvrez comment créer des blocs de contenu dynamique et comment les utiliser pour personnaliser le contenu de votre diffusion email dans la vidéo suivante.

>[!VIDEO](https://video.tv.adobe.com/v/342088?quality=12)


