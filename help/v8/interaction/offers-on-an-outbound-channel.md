---
product: campaign
title: Offres sur canal sortant
description: Offres sur canal sortant
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: case-study
exl-id: 77fee343-09d1-4d60-be43-efe02953a70c
TQID: 'https://experienceleague.adobe.com/WGoYaHNR13J47UVmKpHRSm9aw0T8ZrvHUl9zGXezQBU'
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
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 55%
---
# Offres sur canal sortant{#offers-on-an-outbound-channel}



## Diffusion d&#39;une offre par email {#email-offer-delivery}

Notre base de données comporte une catégorie d’offres de voyages en Afrique. L’éligibilité, les contextes et les représentations de chaque offre ont été configurés. Nous allons maintenant créer une campagne afin de présenter nos offres par e-mail.

1. Créez votre opération marketing et votre workflow de ciblage.

   ![Workflow de ciblage de la campagne Trips to Africa : activités de dossier, de diffusion, de déduplication et de mise à jour de deux listes](assets/offer_delivery_example_001.png)

1. Editez la diffusion email et cliquez sur l&#39;icône **[!UICONTROL Offres]**.

   ![Diffusion par e-mail avec l’icône Offres ouvrant la fenêtre Gestion des offres, les options de sélection des offres et le champ Emplacement](assets/offer_delivery_example_002.png)

1. Sélectionnez l&#39;emplacement Email de votre environnement d&#39;offres correspondant aux voyages.

   ![Fenêtre de gestion des offres avec la liste des Emplacements indiquant les emplacements disponibles, y compris les parcours Abonnés](assets/offer_delivery_example_003.png)

1. Choisissez la catégorie dans laquelle se trouvent les offres de voyages pour l&#39;Afrique.

   ![Fenêtre Gestion des offres avec l’arborescence des catégories développée sous Catalogue d’offres et Parcours, catégorie Afrique mise en surbrillance](assets/offer_delivery_example_004.png)

1. Choisissez de présenter deux offres dans votre diffusion.

   ![Fenêtre de gestion des offres avec la catégorie Afrique et le Nombre de propositions par message défini sur 2](assets/offer_delivery_example_005.png)

1. Fermez la fenêtre de gestion des offres et créez le contenu de votre diffusion.

   ![Éditeur de contenu HTML de diffusion par e-mail avec les vues d’inclusion par défaut, prêt pour les propositions d’offre](assets/offer_delivery_example_006.png)

1. Cliquez sur le champ de fusion pour insérer une première proposition d&#39;offre et choisissez la Fonction de rendu HTML.

   ![Menu de la barre d’outils de contenu d’HTML : propositions, puis proposition 1, fonction de rendu et rendu HTML](assets/offer_delivery_example_007.png)

1. Insérez la deuxième proposition d&#39;offre.

   ![Le contenu d&#39;email HTML avec les deux propositions inclut des lignes en utilisant la vue de rendu/html, avant le lien de désinscription](assets/offer_delivery_example_008.png)

1. Cliquez sur **[!UICONTROL Aperçu]** pour prévisualiser vos offres dans la diffusion puis sélectionnez un destinataire afin de visualiser les offres telles qu&#39;il les recevra.

   ![Onglet Aperçu de la diffusion affichant l’e-mail avec le titre, le texte et l’image de l’offre Traverser le Sahara pour un destinataire sélectionné](assets/offer_delivery_example_009.png)

1. Enregistrez votre diffusion et lancez le workflow de ciblage.
1. Ouvrez votre diffusion et cliquez sur l&#39;onglet **[!UICONTROL Suivi]** : vous pouvez constater que le moteur d&#39;offre a déterminé les propositions à faire entre les différentes offres existant dans la catégorie.

   ![Onglet Audit de la diffusion Log répertoriant les propositions générées par offre, telles que les offres Pyramids et Sahara](assets/offer_delivery_example_010.png)

## Effectuer une simulation d&#39;offres {#perform-an-offer-simulation}

1. Dans l’onglet **[!UICONTROL Profils et cibles]**, cliquez sur le lien **[!UICONTROL Simulations]**, puis sur le bouton **[!UICONTROL Créer]**.

   ![Liste des simulations avec le bouton Créer ouvrant la boîte de dialogue Nouvelle simulation d’offre avec le modèle, le libellé et le dossier](assets/offer_simulation_001.png)

1. Choisissez un libellé et spécifiez des paramètres d&#39;exécution si besoin est.

   ![Nouvelle boîte de dialogue de simulation de l&#39;offre avec le libellé Abonnés de 1 an, le dossier Simulations et les paramètres d&#39;exécution](assets/offer_simulation_example_002.png)

1. Enregistrez la simulation. Celle-ci s’ouvre alors dans un nouvel onglet.

   ![Tableau de bord de simulation de 1 an pour les abonnés avec l&#39;onglet Modifier et un bouton Démarrer la simulation](assets/offer_simulation_example_003.png)

1. Cliquez sur l&#39;onglet **[!UICONTROL Edition]**, puis sur **[!UICONTROL Périmètre]**.

   ![Onglet Modification de la simulation, section Portée, avec environnement ou catégorie, emplacement, thèmes, date de contact et propositions](assets/offer_simulation_example_004.png)

1. Sélectionnez la catégorie sur laquelle vous souhaitez simuler vos offres.

   ![Liste des environnements ou des catégories développée sous Offres - conception et catalogue d&#39;offres, avec la catégorie Voyage sélectionnée](assets/offer_simulation_example_005.png)

1. Sélectionnez l&#39;emplacement sur lequel doit porter la simulation.

   ![Liste des emplacements dans la catégorie Voyage proposant Courrier et e-mail (Environnement - Destinataire)](assets/offer_simulation_example_006.png)

1. Saisissez les dates de validité. Vous devez au moins saisir une date de début. Ceci permet au moteur d’offres de filtrer les offres et de choisir celles qui sont valides à une date donnée.
1. Si nécessaire, spécifiez un ou plusieurs thèmes pour limiter le nombre d&#39;offres à celles ayant ce mot-clé dans leurs paramètres.

   Dans notre exemple, la catégorie **Produits financiers** contient deux sous-catégories ayant chacune un thème distinct. La simulation portera seulement sur les offres de la catégorie dont le thème d&#39;application est **Clients &lt; 1 an**.

   ![Section Portée avec le thème Client > 1 an saisi dans le champ Thèmes pour la catégorie Voyage](assets/offer_simulation_example_007.png)

1. Sélectionnez les destinataires à cibler.

   ![Assistant de filtrage de la sélection de la cible sélectionnant Une liste de destinataires, puis la liste des voyageurs fréquents](assets/offer_simulation_example_008.png)

1. Paramétrez le nombre d&#39;offres que vous souhaitez proposer à chaque destinataire.

   Dans notre exemple, le moteur d&#39;offres va sélectionner pour chaque destinataire les 3 offres dont le poids est le plus élevé.

   ![Section Portée avec nombre de propositions défini sur 3 et requête cible sur la liste de diffusion des offres spéciales](assets/offer_simulation_example_009.png)

1. Enregistrez vos paramètres puis cliquez sur **[!UICONTROL Démarrer la simulation]**, sur l&#39;onglet **[!UICONTROL Tableau de bord]**, pour lancer la simulation.

   ![Boîte de dialogue Démarrer la simulation du tableau de bord demandant confirmation, avec le bouton OK en surbrillance](assets/offer_simulation_example_010.png)

1. Lorsque la simulation est terminée, consultez les **[!UICONTROL Résultats]** pour connaître la répartition des propositions par offres.

   Dans notre exemple, le moteur d&#39;offres a bien basé la répartition des offres sur une base de 3 propositions.

   ![Onglet Résultats de la simulation avec Répartition des propositions par offres : taille de la population 30, nombre de propositions 30](assets/offer_simulation_example_011.png)

1. Affichez le rapport **[!UICONTROL Répartition des offres par rang]** pour voir le classement des offres sélectionnées par le moteur d&#39;offres.

   ![Rapport de répartition des offres par rang avec tableau de classement des offres pour les voyages aux États-Unis et en France, et graphique circulaire](assets/offer_simulation_example_012.png)

1. Si besoin est, modifiez les éléments du périmètre autant de fois que nécessaire et relancez la simulation en cliquant sur **[!UICONTROL Démarrer la simulation]**.

   ![Boîte de dialogue Démarrer la simulation du tableau de bord demandant confirmation, avec le bouton OK en surbrillance](assets/offer_simulation_example_010.png)

1. Pour conserver les données des simulations, utilisez les fonctions d&#39;historisation ou d&#39;export disponibles dans le rapport.

   ![Répartition des offres par rapport de classement avec le menu Exporter et l&#39;icône d&#39;enregistrement en surbrillance](assets/offer_simulation_example_013.png)
