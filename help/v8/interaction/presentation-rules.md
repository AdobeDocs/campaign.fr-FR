---
product: campaign
title: Règles de présentation
description: Règles de présentation
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: case-study
exl-id: f9dd9ad6-48da-4a80-9405-109a433a1ed5
TQID: 'https://experienceleague.adobe.com/s2QV1BGLtUfyWg1BfYuryciF9STRK3HpIXNc6oQ0ATY'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b6fcaf36-3bc4-4604-94f3-81b5d3f41ecf
    internal-label: Offer Management
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 63%
---
# Règles de présentation{#presentation-rules}



## Création d&#39;une règle de présentation {#creating-a-presentation-rule}

Notre base de données contient plusieurs offres de voyages pour l’Europe, l’Afrique, les États-Unis et le Canada. Nous voulons envoyer des offres pour un voyage au Canada, mais si le destinataire refuse ce type d&#39;offre, nous ne voulons pas la lui envoyer de nouveau.

Vous allez donc paramétrer votre règle de façon à ne proposer de voyages au Canada qu&#39;une seule fois à un destinataire et à ne pas lui reproposer s&#39;il l&#39;a déjà refusé.

1. Dans l&#39;arborescence Adobe Campaign, positionnez-vous au niveau du noeud **[!UICONTROL Administration]** > **[!UICONTROL Gestion de campagnes]** > **[!UICONTROL Gestion des typologies]** > **[!UICONTROL Règles de typologie]**.
1. Créez une nouvelle règle de type **[!UICONTROL Présentation des offres]**.

   ![Formulaire de création de règle de typologie avec la liste Type de règle ouverte et Présentation des offres sélectionnée](assets/offer_typology_example_001.png)

1. Modifiez son libellé et sa description si nécessaire.

   ![Onglet Général de la règle de typologie avec un libellé, le type de présentation de l&#39;offre, le canal E-mail et une description saisis](assets/offer_typology_example_002.png)

1. Sélectionnez l&#39;option **[!UICONTROL Tous les canaux]** afin que la règle ne se limite pas à un seul canal.

   ![Liste des canaux de la règle de typologie avec Tous les canaux sélectionnés](assets/offer_typology_example_003.png)

1. Cliquez sur le lien **[!UICONTROL Critères d&#39;application de la règle]** et choisissez le noeud **[!UICONTROL Catégorie]** comme expression.

   ![Fenêtre de requête avec la boîte de dialogue Sélectionner une expression ouverte pour choisir le champ Catégorie](assets/offer_typology_example_004.png)

1. Sélectionnez la catégorie correspondant à vos offres de voyage pour le Canada puis cliquez sur **[!UICONTROL OK]** pour fermer la fenêtre de requête.

   ![Requête sur une catégorie égale à Canada, avec le dossier Canada sélectionné dans l&#39;arborescence des catégories d&#39;offres de voyage](assets/offer_typology_example_005.png)

1. Dans l&#39;onglet **[!UICONTROL Présentation des offres]**, sélectionnez les mêmes dimensions que celles paramétrées au niveau de l&#39;environnement.

   ![Onglet Présentation des offres affichant la dimension de ciblage et la dimension de stockage, qui correspondent à l’environnement](assets/offer_typology_example_006.png)

1. Indiquez la période pendant laquelle la règle doit s&#39;appliquer.

   ![Onglet Présentation des offres avec la Période glissante, le champ Période prise en compte est défini sur 10j](assets/offer_typology_example_007.png)

1. Limitez la proposition à une occurrence afin que les destinataires qui ont déjà refusé un voyage au Canada ne reçoivent pas à nouveau une proposition similaire.

   ![Onglet Présentation des offres avec le champ Quantité maximale de propositions défini sur 1](assets/offer_typology_example_008.png)

1. Sélectionnez le filtre **[!UICONTROL Les offres de la même catégorie]** afin d&#39;exclure toute offre provenant de la catégorie **Canada**.

   ![Liste déroulante Offres dans Propositions à comptabiliser avec les Offres de la même catégorie sélectionnées](assets/offer_typology_example_020.png)

1. Sélectionnez le filtre **[!UICONTROL Propositions refusées]** afin de ne prendre en compte que les propositions refusées par le destinataire.

   ![Liste déroulante Statut des propositions dans Propositions à comptabiliser avec les propositions rejetées sélectionnées](assets/offer_typology_example_021.png)

1. Choisissez les destinataires pour lesquels la règle doit s&#39;appliquer.

   Dans notre exemple, nous choisissons les destinataires **Grands voyageurs**.

   ![Assistant Modifier la requête de filtrage sélectionnant le dossier de destinataires Grands voyageurs comme cible de la règle](assets/offer_typology_example_009.png)

1. Référencez votre règle dans une typologie propre aux offres.

   ![Onglet Typologies de la règle avec la boîte de dialogue Ajouter des typologies répertoriant la typologie Offres sélectionnée](assets/offer_typology_example_013.png)

1. Positionnez-vous au niveau de votre environnement d&#39;offres, soit **Environnement - Destinataire** dans notre exemple, et référencez la typologie que vous venez de créer à l&#39;aide de la liste déroulante de l&#39;onglet **[!UICONTROL Eligibilité]**.

   ![Onglet Éligibilité de l&#39;environnement d&#39;offres avec la liste Typologie de présentation des offres affichant les offres](assets/offer_typology_example_014.png)

## Application de la règle de présentation {#applying-the-presentation-rule}

Voici un exemple d&#39;application de la règle de typologie créée précédemment.

Nous voulons envoyer une première proposition d’offre appartenant à la catégorie Canada. Si l’offre est rejetée par une des personnes destinataires une première fois, elle ne lui est pas proposée à nouveau.

1. Dans le dossier de destinataires **Grands voyageurs**, sélectionnez un des profils pour vérifier les offres auxquelles il est éligible : cliquez sur l&#39;onglet **[!UICONTROL Propositions]**, puis le sous-onglet **[!UICONTROL Prévisualisation]**.

   Dans notre exemple, le destinataire **Nicolas Lumos** est éligible à une offre qui fait partie de la catégorie **Canada**.

   ![Onglet Propositions des destinataires, sous-onglet Aperçu, répertoriant l&#39;offre éligible pour la catégorie Amériques](assets/offer_typology_example_015.png)

1. Créez une première diffusion email destinée à cibler vos destinataires **Grands voyageurs** avec des offres.
1. Choisissez les paramètres d&#39;appels au moteur d&#39;offres.

   Dans notre exemple la catégorie **Amériques** est choisie, sachant qu&#39;elle contient les sous-catégories **Canada** et **Etats-Unis**.

   ![Boîte de dialogue de gestion des offres d’une diffusion e-mail avec la catégorie Amériques et 2 propositions par message](assets/offer_typology_example_016.png)

1. Insérez vos offres dans le corps du message et envoyez la diffusion. Pour en savoir plus à ce sujet, consultez la section [À propos des canaux sortants](https://experienceleague.adobe.com/fr/docs/campaign/campaign-v8/offers/interaction-send-offers){target="_blank"} (documentation de Campaign v8).

   Votre destinataire a bien reçu l&#39;offre pour laquelle il est éligible.

1. Le destinataire a refusé l&#39;offre pour le Canada, comme indiqué dans l&#39;historique de ses propositions.

   ![Historique des propositions de destinataire avec l&#39;offre de motoneige Canada en statut Rejeté](assets/offer_typology_example_018.png)

1. Vérifiez les offres auxquelles il est désormais éligible.

   Vous constatez qu&#39;aucune offre sur le Canada n&#39;est retenue.

   ![Onglet Aperçu du destinataire affichant les offres éligibles New-York et Grand Canyon, sans offre Canada](assets/offer_typology_example_019.png)
