---
product: campaign
title: Présenter une offre (interaction entrante)
description: Découvrez comment présenter la meilleure offre à l'aide du module Interaction de Campaign
source-git-commit: 9712d72dd08291673490b42967fd469353fca67a
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 20%

---

# Présenter la meilleure offre{#interaction-present-offers}

Les offres peuvent être présentées sur différents emplacements à l’aide de [un canal entrant ou sortant](interaction-architecture.md#interaction-types). Ce chapitre présente certaines fonctionnalités spécifiques aux canaux entrants.

![](assets/inbound-interactions.png)

Pour qu&#39;une offre puisse être sélectionnée par le moteur d&#39;offres, elle doit être validée et disponible dans un environnement en ligne.

![](../assets/do-not-localize/book.png) Pour en savoir plus à ce sujet, consultez la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/managing-an-offer-catalog/approving-and-activating-an-offer.html?lang=fr#approving-offer-content)

Dans le cadre d&#39;un contact entrant, l&#39;utilisateur qui navigue sur la page peut être identifié par le site web ou non. Le moteur d&#39;offres présente différentes offres pour les profils identifiés et pour les profils anonymes.

Avant de pouvoir présenter des offres sur un canal entrant, vous devez configurer l&#39;appel au moteur d&#39;offres à l&#39;endroit où vous souhaitez que les offres soient présentées. Dans la plupart des cas, il s&#39;agit de la page Web d&#39;une interaction entrante.

>[!NOTE]
>
>Pour les interactions entrantes, vous devez paramétrer spécifiquement le moteur d&#39;offres afin de proposer et mettre à jour une ou plusieurs offres.
>
>Vous devez également autoriser le mode unitaire sur vos emplacements. Pour plus d’informations, consultez [cette page](interaction-offer-spaces.md).
