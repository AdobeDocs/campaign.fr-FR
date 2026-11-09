---
product: campaign
title: Périmètre de la simulation
description: Périmètre de la simulation
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: simulating-offers
exl-id: 4f6b3de2-3fdf-441d-925d-476e20e75c6f
TQID: 'https://experienceleague.adobe.com/mZ618bV3lzbXS09MXBXJxM5RizvMWl6lEgw0Bwb2bGI'
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
source-git-commit: 936b7519d13ab54d94df9305ef05d4ceb6d6742d
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 100%
---
# Périmètre de la simulation{#simulation-scope}



## Définition du périmètre {#definition-of-the-scope}

Positionnez-vous dans l&#39;onglet **[!UICONTROL Périmètre]** pour choisir vos paramètres.

Vous devez définir obligatoirement :

* Un environnement ou une catégorie d&#39;offres.
* Un emplacement.
* Une date de contact. Les offres non éligibles à la date de contact spécifiée ne sont pas prises en compte.
* Une population cible.

  Si vous ne précisez pas de filtre sur votre cible, la totalité de la table des destinataires sera prise en compte dans la simulation.

* Le nombre de propositions à simuler par cible.

  La personne destinataire recevra autant de propositions que le nombre fixé. Par exemple, si le chiffre est 5, chaque personne ciblée recevra au plus 5 propositions d’offre.

  ![](assets/offer_simulation_009.png)

Pour affiner les offres à prendre en compte pour la simulation, vous pouvez ajouter un ou plusieurs thèmes (définis préalablement au niveau des catégories).

Vous pouvez également choisir d’effectuer la simulation sur toutes les offres ou seulement sur celles en ligne. Certains filtres vous permettent de modifier votre sélection si vous le souhaitez.

>[!NOTE]
>
>Vous devez renseigner une date de contact. Ceci permet au moteur d’interaction d’effectuer un premier tri parmi la totalité des offres contenues dans l’environnement ou la catégorie sélectionné(e). Si aucune date n’est configurée, la simulation génère une erreur.

## Ajout d&#39;axes de reporting {#adding-reporting-axes}

Vous pouvez enrichir l&#39;analyse de la simulation en ajoutant des axes de reporting sur la cible ou les offres elles-mêmes depuis l&#39;onglet **[!UICONTROL Calculs]**.

Pour ce faire, cliquez sur le bouton **[!UICONTROL Ajouter]** et sélectionnez les champs appropriés. Les axes seront utilisés pour le calcul de la simulation et apparaîtront dans le rapport d’analyse. Pour plus d&#39;informations, consultez la section [Suivi des simulations](simulation-tracking.md).

![](assets/offer_simulation_011.png)
