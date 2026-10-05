---
product: campaign
title: Présenter une offre (interaction entrante)
description: Découvrez comment présenter la meilleure offre à l'aide du module Interaction de Campaign.
feature: Interaction, Offers
role: User, Admin
exl-id: d0137fa7-3d04-4205-b49c-46973e45a5b8
TQID: 'https://experienceleague.adobe.com/aC-hN1JwwFkuGc6ZNV0M3uHpM7LcXTHpyC9wCbxKziQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 80%
---
# Présentation de la meilleure offre{#interaction-present-offers}

Les offres peuvent être présentées à divers emplacements utilisant [un canal entrant ou sortant](interaction-architecture.md#interaction-types). Ce chapitre présente certaines fonctionnalités spécifiques aux canaux entrants.

![](assets/inbound-interactions.png)

Pour qu&#39;une offre puisse être sélectionnée par le moteur d&#39;offres, elle doit avoir été validée et être disponible dans un environnement en ligne.

Pour en savoir plus à ce sujet, consultez la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html?lang=fr#approving-offer-content){target="_blank"}.

Lorsqu&#39;il s&#39;agit d&#39;un contact entrant, l&#39;utilisateur qui navigue sur la page peut être identifié ou non par le site web. Le moteur d&#39;offres présente des offres différentes selon qu&#39;il s&#39;agit de profils identifiés ou de profils anonymes.

Avant de pouvoir proposer des offres sur un canal entrant, vous devez configurer l’appel au moteur d’offres à l’endroit où vous souhaitez que les offres soient présentées. Le cas le plus courant dans le cadre d’une interaction entrante est la page web.

>[!NOTE]
>
>Dans le cas d’interactions entrantes, il est nécessaire de paramétrer spécifiquement le moteur d’offres pour proposer et mettre à jour une ou plusieurs offres.
>
>Vous devez également activer le mode unitaire sur vos emplacements. Pour plus d’informations, consultez [cette page](interaction-offer-spaces.md).
