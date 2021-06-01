---
product: Adobe Campaign
title: Catalogue d'offres d'interaction Campaign
description: Découvrez comment créer un catalogue d’offres
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 13%

---

# Créer un catalogue d’offres

En tant que **Chargé d&#39;offres**, vous êtes responsable de la création du catalogue d&#39;offres.

Un catalogue d&#39;offres est associé à un seul environnement préexistant. Les offres de ce catalogue ne peuvent être associées qu&#39;aux espaces spécifiés dans le même environnement.

Avant de créer vos offres, vous devez d&#39;abord définir un [environnement](interaction-env.md) contenant toutes les caractéristiques (éligibilité, contraintes sur la cible, règles de présentation) d&#39;un ensemble d&#39;offres, classées par catégories, ainsi que la liste de leurs emplacements.

## Création de catégories d’offres{#creating-offer-categories}

Les offres sont organisées en catégories/sous-catégories. Les catégories sont créées dans l’environnement **[!UICONTROL Conception]** et déployées automatiquement dans l’environnement **[!UICONTROL Live]** (c’est-à-dire mises à disposition) lorsque les offres qu’elles contiennent sont validées. L’environnement **[!UICONTROL Conception]** contient une catégorie par défaut pour recevoir toutes les offres. Il est possible de créer des sous-catégories pour ajouter une hiérarchie aux offres du catalogue.

Pour chaque catégorie, vous pouvez définir des **dates d&#39;éligibilité**, c&#39;est-à-dire la période pendant laquelle les offres contenues dans la catégorie peuvent être présentées à leur cible. Vous pouvez également ajuster le poids d&#39;une catégorie pour donner la priorité à la présentation de l&#39;offre.

Pour créer une catégorie, procédez comme suit :

1. Navigateur vers le dossier **[!UICONTROL Catalogue d’offres]**.

   ![](assets/offer_cat_create_001.png)

1. Cliquez avec le bouton droit de la souris et sélectionner **[!UICONTROL Ajouter un dossier &quot;Catégorie d&#39;offres&quot;]** dans le menu contextuel.

   ![](assets/offer_cat_create_002.png)

1. Renommez la catégorie. Vous pourrez modifier le libellé ultérieurement via l&#39;onglet **[!UICONTROL Général]** de la catégorie.

   ![](assets/offer_cat_create_003.png)

   >[!NOTE]
   >
   >Répétez ces étapes pour créer autant de catégories que nécessaire.

   Par la suite, il vous est possible, selon vos besoins :

   * D&#39;attribuer des dates d&#39;éligibilité, depuis l&#39;onglet **[!UICONTROL Éligibilité]**.

      ![](assets/offer_cat_create_004.png)

   * **[!UICONTROL Editez]** la requête pour appliquer des filtres à la cible de l&#39;offre.

   * Un récapitulatif des règles d&#39;éligibilité. Pour les visualiser, cliquez sur le lien **[!UICONTROL Planning et règles d&#39;éligibilité de l&#39;offre]** .

## Ajouter une catégorie de secours

Afin de s&#39;assurer que tous les destinataires reçoivent une proposition d&#39;offre, il est possible d&#39;ajouter systématiquement une ou plusieurs catégories d&#39;offres dans les recommandations.

Ces offres de secours doivent avoir un poids faible (mais non nul), de sorte qu’elles ne soient prises en compte que si aucune offre de poids supérieur n’est éligible.

En outre, aucune règle de présentation ne doit être appliquée à ces offres pour s’assurer qu’elles sont toujours incluses dans les recommandations. Cela signifie que, lors d&#39;une proposition, si aucune offre de poids supérieur n&#39;est disponible, le destinataire recevra au moins une offre de cette catégorie.

Pour inclure une catégorie de secours dans les recommandations, procédez comme suit :

1. Accédez à votre catalogue d’offres.
1. Cliquez sur l&#39;onglet **[!UICONTROL Eligibilité]** et sélectionnez l&#39;option **[!UICONTROL Toujours inclure cette catégorie dans les recommandations]**.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

   ![](assets/offer_cat_default_001.png)

