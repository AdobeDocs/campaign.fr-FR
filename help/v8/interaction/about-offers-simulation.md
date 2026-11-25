---
product: campaign
title: À propos de la simulation des offres
description: À propos de la simulation des offres
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
exl-id: facaa88e-1fa2-4189-9d8f-348aaef3e235
TQID: 'https://experienceleague.adobe.com/034-CFbQIFVm9QiSpDyRHlVsIrF46NSqKMwp-Gm3-mc'
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
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 74%
---
# À propos de la simulation des offres{#about-offers-simulation}



Le module **Simulation** vous permet de tester la répartition des offres d&#39;une catégorie ou d&#39;un environnement avant de lancer votre proposition auprès de vos destinataires.

La simulation prend en compte les contextes et les règles d’éligibilité précédemment appliqués aux offres (consultez la section [Vue d’ensemble du catalogue d’offres](https://experienceleague.adobe.com/fr/docs/campaign/campaign-v8/offers/interaction-offer-catalog){target="_blank"} (documentation de Campaign v8)), ainsi que leurs règles de présentation (consultez la section [Gérer la présentation des offres](managing-offer-presentation.md)). Il est ainsi possible de tester et d&#39;affiner différentes versions de votre proposition sans utiliser effectivement une offre ou solliciter excessivement ou insuffisamment une cible. La simulation n&#39;a en effet aucun impact sur les destinataires ciblés.

Pour savoir comment simuler une offre, procédez comme suit.

![Lire la vidéo](assets/how-to-video.png) Vous pouvez également regarder cette [vidéo](https://helpx.adobe.com/campaign/classic/how-to/simulate-offer-in-acv6.html?playlist=/ccx/v1/collection/product/campaign/classic/segment/digital-marketers/explevel/intermediate/applaunch/introduction/collection.ccx.js&ref=helpx.adobe.com).

## Etapes principales pour créer une simulation {#main-steps-for-creating-a-simulation}

Pour effectuer une simulation de vos offres, procédez de la manière suivante :

1. Dans l’onglet **[!UICONTROL Profils et cibles]**, cliquez sur le lien **[!UICONTROL Simulations]**, puis sur le bouton **[!UICONTROL Créer]**.

   ![Liste des simulations avec le bouton Créer ouvrant la boîte de dialogue Nouvelle simulation d’offre avec le modèle, le libellé et le dossier](assets/offer_simulation_001.png)

1. Enregistrez puis éditez la simulation que vous venez de créer.
1. Dans l&#39;onglet **[!UICONTROL Edition]**, spécifiez les paramètres d&#39;exécution.

   Pour plus d&#39;informations, consultez la section [Paramètres d&#39;exécution](execution-settings.md).

   ![Onglet Général de la simulation, Paramètres d’exécution : planification de faible activité, journalisation SQL et liste de priorités](assets/offer_simulation_003.png)

   >[!NOTE]
   >
   >Les paramètres d&#39;exécution ne sont disponibles que si vous utilisez Interaction conjointement avec Campaign.

1. Déterminez le périmètre de la simulation.

   Pour plus d&#39;informations, consultez la section [Définition du périmètre](simulation-scope.md#definition-of-the-scope).

   ![Onglet Périmètre de la simulation avec l&#39;environnement, l&#39;emplacement, la date de contact, les propositions et le dossier cible Grands voyageurs](assets/offer_simulation_004.png)

1. Ajoutez des axes de reporting pour enrichir le rapport **[!UICONTROL Répartition des offres par rang]** (étape optionnelle).

   Pour plus d&#39;informations, consultez la section [Ajout d&#39;axes de reporting](simulation-scope.md#adding-reporting-axes).

   ![Onglet Calculs de simulation avec des axes de reporting sur la cible et sur les offres, et le bouton Ajouter](assets/offer_simulation_005.png)

1. Cliquez sur **[!UICONTROL Enregistrer]** pour sauvegarder les paramètres de la simulation.
1. Lancez la simulation depuis le tableau de bord.

   ![Tableau de bord de simulation avec le bouton Démarrer la simulation en surbrillance](assets/offer_simulation_006.png)

1. Consultez le résultat de votre simulation et affichez le rapport d&#39;analyse de la simulation.

   Pour plus d&#39;informations, consultez la section [Suivi des simulations](simulation-tracking.md).

   ![Onglet Résultats et rapport Répartition des offres par rang avec tableau de classement des offres et graphique circulaire](assets/offer_simulation_007.png)
