---
product: campaign
title: Présentation d'offres aux profils anonymes (interaction entrante)
description: Découvrez comment présenter des offres aux profils anonymes
feature: Interaction, Offers
role: User, Admin
exl-id: b7a04360-f8c6-4c69-9594-2b44d3f819b7
TQID: https://experienceleague.adobe.com/rl7SIcS-OkMmLnxvPiEfjs51xouGSSyLJV4in-vsoCE
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 435
ht-degree: 82%

---

# Interactions anonymes {#anonymous-interactions}

## Environnement pour les interactions anonymes {#environment-for-anonymous-interactions}

Par défaut, le module **Interaction** de Campaign comprend un environnement préconfiguré pour cibler la table des destinataires intégrée (offres identifiées). Si vous devez cibler une autre table, par exemple, une table des visiteurs pour les offres anonymes ou une table des destinataires personnalisée, vous devez utiliser l&#39;assistant de mapping de ciblage pour créer l&#39;environnement. [En savoir plus sur les environnements](interaction-env.md).

Lorsque vous créez l&#39;environnement anonyme via l&#39;assistant de création de mapping, la case **[!UICONTROL Environnement dédié aux interactions anonymes entrantes]** est automatiquement cochée dans l&#39;onglet **[!UICONTROL Général]** de l&#39;environnement.

La **[!UICONTROL dimension de ciblage]** est automatiquement renseignée. Par défaut, il est lié au tableau des visiteurs.

Le champ **[!UICONTROL Dossier des visiteurs]** s&#39;affiche. Il est automatiquement prérempli pour pointer sur le dossier **[!UICONTROL Visiteurs]**. Ce champ permet de spécifier l&#39;endroit où sont stockés les profils des visiteurs.

![](assets/anonymous_environment_option.png)

>[!NOTE]
>
>Si vous souhaitez trier plusieurs types de visiteurs, par exemple dans le cas d&#39;offres anonymes proposées pour plusieurs marques, vous devez créer un environnement pour chaque marque puis un dossier de type **[!UICONTROL Visiteurs]** pour chaque environnement.

## Catalogue d&#39;offres pour interactions anonymes {#offer-catalog-for-anonymous-interactions}

Tout comme les interactions sortantes, les interactions entrantes sont organisées au sein d&#39;un catalogue d&#39;offres composé de catégories et d&#39;offres.

Pour créer les catégories et emplacements, procédez de la même manière que dans le cas de visiteurs identifiés. Consultez les sections [Création d&#39;une catégorie d&#39;offres](interaction-offer-catalog.md#creating-offer-categories) et [Création d&#39;un environnement d&#39;offres](interaction-env.md#creating-an-offer-environment).

## Les visiteurs anonymes {#anonymous-visitors}

Les visiteurs anonymes peuvent être soumis à un processus d’identification par cookies lorsqu’ils se connectent. Cette reconnaissance implicite s’effectue à partir de l’historique de navigation du visiteur.

Ce processus consiste à comparer les données récupérées par les cookies avec celles de votre base de données. Dans certains cas, les visiteurs sont reconnus (ils sont alors identifiés implicitement) ; dans d&#39;autres cas, ils ne le sont pas (et restent donc anonymes).

Afin d&#39;effectuer cette analyse, au niveau de l&#39;emplacement, cochez la case **[!UICONTROL Identifier implicitement l&#39;individu à partir de son historique de navigation]**.

![](assets/identification_anonymous_visitors.png)

## Traitement des visiteurs anonymes non identifiés {#processing-unidentified-anonymous-visitors}

Après analyse, si un visiteur anonyme n’est pas identifié, vous pouvez stocker ses données dans un emplacement donné. Vous pouvez ainsi proposer des offres destinées spécifiquement à ce type de visiteur et correspondant aux règles de typologie spécifiées.

En cas d&#39;absence d&#39;élément permettant d&#39;identifier un contact ou si vous ne souhaitez pas proposer d&#39;offre identifiée à un contact pouvant être identifié implicitement, vous pouvez choisir d&#39;effectuer un basculement vers un environnement anonyme.

Pour cela, cochez la case **[!UICONTROL Basculer sur un emplacement anonyme si aucun individu n&#39;a été identifié]**, puis spécifiez l&#39;environnement dédié à ces visiteurs non identifiés dans la zone **[!UICONTROL Emplacement anonyme associé]** de la définition d&#39;un emplacement.

![](assets/anonymous_to_anonymous_environment.png)
