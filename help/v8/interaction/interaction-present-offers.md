---
product: campaign
title: Présenter une offre (interaction entrante)
description: Découvrez comment présenter la meilleure offre à lʼaide du module Interaction de Campaign.
exl-id: d0137fa7-3d04-4205-b49c-46973e45a5b8
source-git-commit: c19ac91fe7b4b825f75ec096320efabc3e78328c
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 100%

---

# Présentation de la meilleure offre{#interaction-present-offers}

Les offres peuvent être présentées à divers emplacements utilisant [un canal entrant ou sortant](interaction-architecture.md#interaction-types). Ce chapitre traite des spécificités des canaux entrants.

![](assets/inbound-interactions.png)

Pour quʼune offre puisse être sélectionnée par le moteur dʼoffres, elle doit avoir été validée et être disponible dans un environnement en ligne.

![](../assets/do-not-localize/book.png) Pour en savoir plus à ce sujet, consultez la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html?lang=fr#approving-offer-content).

Lorsquʼil sʼagit dʼun contact entrant, lʼutilisateur qui navigue sur la page peut être identifié ou non par le site web. Le moteur dʼoffres présente des offres différentes selon quʼil sʼagit de profils identifiés ou de profils anonymes.

Avant de pouvoir proposer des offres sur un canal entrant, vous devez paramétrer lʼappel au moteur dʼoffres à lʼendroit où vous souhaitez que les offres soient présentées. Le cas le plus courant dans le cadre dʼune interaction entrante est la page web.

>[!NOTE]
>
>Dans le cas dʼinteractions entrantes, il est nécessaire de paramétrer spécifiquement le moteur dʼoffres pour proposer et mettre à jour une ou plusieurs offres.
>
>Vous devez également autoriser le mode unitaire sur vos emplacements. Pour plus dʼinformations, consultez [cette page](interaction-offer-spaces.md).
