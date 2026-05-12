---
product: campaign
title: Présenter une offre (interaction entrante)
description: Découvrez comment présenter la meilleure offre à l'aide du module Interaction de Campaign.
feature: Interaction, Offers
role: User, Admin
exl-id: d0137fa7-3d04-4205-b49c-46973e45a5b8
TQID: https://experienceleague.adobe.com/aC-hN1JwwFkuGc6ZNV0M3uHpM7LcXTHpyC9wCbxKziQ
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 209
ht-degree: 70%

---

# Présentation de la meilleure offre{#interaction-present-offers}

Les offres peuvent être présentées à divers emplacements utilisant [un canal entrant ou sortant](interaction-architecture.md#interaction-types). Ce chapitre présente certaines fonctionnalités spécifiques aux canaux entrants.

![](assets/inbound-interactions.png)

Pour qu&#39;une offre puisse être sélectionnée par le moteur d&#39;offres, elle doit avoir été validée et être disponible dans un environnement en ligne.

Pour en savoir plus à ce sujet, consultez la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html?lang=fr#approving-offer-content){target="_blank"}.

Lorsqu&#39;il s&#39;agit d&#39;un contact entrant, l&#39;utilisateur qui navigue sur la page peut être identifié ou non par le site web. Le moteur d&#39;offres présente des offres différentes selon qu&#39;il s&#39;agit de profils identifiés ou de profils anonymes.

Avant de pouvoir proposer des offres sur un canal entrant, vous devez configurer l’appel au moteur d’offres à l’endroit où vous souhaitez que les offres soient présentées. Dans la plupart des cas, pour une interaction entrante, il s’agit de la page web.

>[!NOTE]
>
>Dans le cas d’interactions entrantes, il est nécessaire de paramétrer spécifiquement le moteur d’offres pour proposer et mettre à jour une ou plusieurs offres.
>
>Vous devez également activer le mode unitaire sur vos emplacements. Pour plus d’informations, consultez [cette page](interaction-offer-spaces.md).
