---
product: Adobe Campaign
title: Offre de Campaign Interaction
description: Découvrez comment créer une offre
feature: Vue d'ensemble
role: Data Engineer
level: Beginner
source-git-commit: 9cb1b38456601bce21d458fea42a5c112d9fafb4
workflow-type: tm+mt
source-wordcount: '953'
ht-degree: 100%

---

# Création d&#39;une offre

Pour créer une offre, procédez comme suit :

1. Accédez à l&#39;onglet **[!UICONTROL Campagnes]** et cliquez sur le lien **[!UICONTROL Offres]**.

1. Cliquez sur le bouton **[!UICONTROL Créer]**.

1. Modifiez le libellé et sélectionnez la catégorie à laquelle doit appartenir l&#39;offre.

1. Cliquez sur **[!UICONTROL Enregistrer]** pour créer l&#39;offre.

   L&#39;offre est disponible dans la plateforme et son contenu peut être paramétré.

## Paramètres d&#39;éligibilité

Vous pouvez désormais utiliser l&#39;onglet **[!UICONTROL Éligibilité]** pour définir :

* La période d&#39;éligibilité de l&#39;offre. [En savoir plus](#eligibility-period)
* Les filtres sur la population cible de l&#39;offre. [En savoir plus](#filters-on-the-target)
* Le poids d&#39;offre. [En savoir plus](#offer-weight)

### La période d&#39;éligibilité de l&#39;offre{#eligibility-period}

Dans l&#39;onglet **[!UICONTROL Éligibilité]** de l&#39;offre, définissez la période d&#39;éligibilité. Utilisez les listes déroulantes pour sélectionner une date de début et une date de fin dans le calendrier.

![](assets/offer_eligibility_create_002.png)

En dehors de cette période, l&#39;offre ne sera pas sélectionnée. Si vous avez également paramétré des dates d&#39;éligibilité pour la catégorie d&#39;offre, la période la plus restrictive s&#39;applique.

### Ajouter des filtres sur la cible {#filters-on-the-target}

Dans l&#39;onglet **[!UICONTROL Éligibilité]** de l&#39;offre, appliquez des filtres à la cible de l&#39;offre.

Pour cela, cliquez sur le lien **[!UICONTROL Édition de la requête]** et sélectionnez le filtre que vous souhaitez appliquer.

![](assets/offer_eligibility_create_003.png)

Si des filtres prédéfinis ont déjà été créés, vous pouvez les sélectionner dans la liste des filtres utilisateur. [En savoir plus](interaction-predefined-filters.md)

![](assets/offer_eligibility_create_004.png)

### Définissez le poids de l&#39;offre {#offer-weight}

Pour permettre au moteur d&#39;arbitrer entre plusieurs offres auxquelles la personne ciblée serait éligible, vous devez attribuer un ou plusieurs poids à l&#39;offre. Vous pouvez également appliquer des filtres sur la cible si nécessaire ou restreindre l&#39;emplacement auquel doit s&#39;appliquer le poids. Une offre dont le poids est plus important sera préférée à une offre avec un poids moindre.

Vous pouvez paramétrer plusieurs poids pour une même offre, notamment en fonction d&#39;une période, d&#39;une cible ou encore d&#39;un emplacement.

Par exemple, une offre peut avoir un poids A pour les contacts âgés de 18 à 25 ans et un poids B pour les contacts plus âgés. Ou, si une offre est éligible tout l&#39;été, elle peut avoir un poids A au mois de juillet, et un poids B au mois d&#39;août.

>[!NOTE]
>
>Le poids affecté peut être temporairement modifié en fonction des paramètres de la catégorie de l&#39;offre. [En savoir plus](interaction-offer-catalog.md#creating-offer-categories)

Pour créer un poids dans une offre, procédez comme suit :

1. Dans l&#39;onglet **[!UICONTROL Éligibilité]** de l&#39;offre, cliquez sur **[!UICONTROL Ajouter]**.

   ![](assets/offer_weight_create_001.png)

1. Modifiez le libellé et attribuez un poids. La valeur par défaut est 1.

   ![](assets/offer_weight_create_006.png)

   >[!CAUTION]
   >
   >Si aucun poids n&#39;est renseigné (0), la cible est considérée comme inéligible à l&#39;offre.

1. Définissez des dates d&#39;éligibilité si vous souhaitez que le poids ne s&#39;applique que pendant une période donnée.

   ![](assets/offer_weight_create_002.png)

1. Si besoin est, choisissez un emplacement auquel se limitera le poids.

   ![](assets/offer_weight_create_003.png)

1. Appliquez un filtre sur la cible.

   ![](assets/offer_weight_create_004.png)

1. Cliquez sur **[!UICONTROL OK]** pour enregistrer le poids.

   ![](assets/offer_weight_create_005.png)

   >[!NOTE]
   >
   >Si un contact est éligible à plusieurs poids pour une offre sélectionnée, le moteur garde le meilleur poids (le plus grand). Lors d&#39;un appel au moteur, une offre ne sort qu&#39;une seule fois maximum par contact.

### Résumé des règles d&#39;éligibilité d&#39;une offre {#a-summary-of-offer-eligibility-rules}

Une fois le paramétrage terminé, un résumé des règles d&#39;éligibilité est disponible dans le tableau de bord de l&#39;offre.

Pour le visualiser, cliquez sur le lien **[!UICONTROL Planning et règles d&#39;éligibilités de l&#39;offre]**.

![](assets/offer_eligibility_create_005.png)

## Créer le contenu de l&#39;offre {#creating-the-offer-content}

Utilisez l&#39;onglet **[!UICONTROL Contenu]** pour définir le contenu de l&#39;offre.

![](assets/offer_content_create_001.png)

1. Définissez les différents paramètres du contenu de l&#39;offre.

   * **[!UICONTROL Titre]** : indiquez le titre que vous souhaitez faire apparaître dans votre offre. Attention, il ne s&#39;agit pas du libellé de l&#39;offre défini dans l&#39;onglet **[!UICONTROL Général]**.
   * **[!UICONTROL URL de destination]** : indiquez l&#39;URL de votre offre. Elle doit débuter par &quot;http://&quot; ou &quot;https://&quot;.
   * **[!UICONTROL URL de l&#39;image]** : indiquez une URL ou un chemin d&#39;accès vers l&#39;image de votre offre.
   * **[!UICONTROL Contenu HTML]** / **[!UICONTROL Contenu texte]** : saisissez le corps de votre offre dans l&#39;onglet de votre souhait. Pour générer le tracking, le **[!UICONTROL contenu HTML]** doit être constitué d&#39;éléments HTML intégrables dans un élément de type `<div>`. Par exemple, le résultat d&#39;un élément `<table>` dans la page HTML sera le suivant :

   ```
      <div> 
       <table>
        <tr>
         <th>Month</th>
         <th>Savings</th>   
        </tr>   
        <tr>    
         <td>January</td>
         <td>$100</td>   
        </tr> 
       </table> 
      </div>
   ```

   Découvrez comment définir l&#39;URL d&#39;acceptation dans [cette section](interaction-offer-spaces.md#configuring-the-status-when-the-proposition-is-accepted).

   ![](assets/offer_content_create_002.png)

   Pour retrouver les champs requis tels qu&#39;ils ont été définis lors du paramétrage des emplacements, cliquez sur le lien **[!UICONTROL Définitions du contenu]** pour afficher la liste. [En savoir plus](interaction-offer-spaces.md)

   ![](assets/offer_content_create_003.png)

   Dans notre exemple, l&#39;offre doit être constituée d&#39;un titre, d&#39;une image, d&#39;un contenu en HTML et d&#39;une URL de destination.

## Prévisualiser l&#39;offre {#previewing-the-offer}

Une fois le contenu de l&#39;offre paramétré, vous pouvez prévisualiser l&#39;offre telle qu&#39;elle apparaîtra pour son destinataire.

Pour cela :

1. Cliquez sur l&#39;onglet **[!UICONTROL Aperçu]**.

   ![](assets/offer_preview_create_001.png)

1. Sélectionnez la représentation de l&#39;offre que vous souhaitez voir.

   ![](assets/offer_preview_create_002.png)

1. Si vous avez personnalisé le contenu de l&#39;offre, sélectionnez la cible de l&#39;offre afin de visualiser la personnalisation.

<!--

## Create a hypothesis on an offer {#creating-a-hypothesis-on-an-offer}

You can create hypotheses on your offer propositions. This lets you determine the impact of your offers on purchases carried out for the product concerned.

>[!NOTE]
>
>These hypotheses are carried out via Response Manager. Please check your license agreement.

Hypotheses carried out on an offer proposition are referenced in their **[!UICONTROL Measure]** tab.

Creating hypotheses is detailed in [this page](../../campaign/using/about-response-manager.md).

-->

## Validation et activation d’une offre{#approve-offers}

Vous pouvez maintenant valider et activer l&#39;offre pour la rendre disponible dans l&#39;environnement **En ligne**.

[!DNL :arrow_upper_right:] Pour en savoir plus à ce sujet, consultez la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html?lang=fr#approving-offer-content)

## Gestion de la présentation des offres{#offer-presentation}

Campaign vous permet de contrôler le flux des propositions d&#39;offres à l&#39;aide des règles de présentation. Ces règles, spécifiques à Campaign Interaction, sont des **règles de typologie**. Elles permettent d&#39;exclure les offres en fonction de l&#39;historique des propositions déjà faites à un destinataire. Elles sont référencées dans l&#39;environnement.

[!DNL :arrow_upper_right:] Pour en savoir plus à ce sujet, consultez la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/managing-offer-presentation.html?lang=fr#managing-offers)

## Simulation de l&#39;offre

Le module Simulation vous permet de tester la répartition des offres d&#39;une catégorie ou d&#39;un environnement avant d&#39;envoyer votre proposition aux destinataires.

La simulation prend en compte les contextes et les règles d&#39;éligibilité précédemment appliqués aux offres ainsi que leurs règles de présentation. Il est ainsi possible de tester et d&#39;affiner différentes versions de votre proposition sans utiliser réellement une offre ou solliciter trop ou trop peu une cible, puisque la simulation n&#39;a aucun impact sur les destinataires ciblés.

[!DNL :arrow_upper_right:] Pour plus d&#39;informations sur la simulation de l&#39;offre, consultez la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/simulating-offers/about-offers-simulation.html?lang=fr)
