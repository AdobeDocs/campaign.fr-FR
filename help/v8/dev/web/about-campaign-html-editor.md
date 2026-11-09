---
product: campaign
title: Prise en main de l‘éditeur HTML Campaign
description: Prise en main du DCE Campaign
feature: Web Apps, Web Forms, Landing Pages, Email Design
version: Campaign v8, Campaign Classic v7
exl-id: f5d65e89-6b18-482b-97d8-11ab94f6775e
TQID: 'https://experienceleague.adobe.com/X-hpH7G2DRGdimNZ-HRbRJpnhmP-QByWSIF5hSUQFG0'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
  - id: b631758a-142d-425f-b9aa-f756d85cb979
    internal-label: Campaign Email Designer
subfeature_v2:
  - id: f391046b-0cf3-4e76-bd3b-97fe06654506
    internal-label: Web Apps
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
  - id: d7be2b01-dc9c-40f7-aace-a151707504ed
    internal-label: Landing pages
  - id: c8da4fdd-eb94-4751-a43c-f82733fb2d6e
    internal-label: Email design
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 6db6c9152f6060b40596bd65a2ce705f916401be
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 84%
---
# Prise en main de l‘éditeur HTML Campaign{#about-campaign-html-editor}

>[!NOTE]
>
>Pour les cas d’utilisation les plus courants, créez vos pages de destination dans l’interface utilisateur web de Campaign où vous pouvez facilement les concevoir et les publier. Les landing pages créées dans la console cliente, comme décrit dans cette section, offrent plus de paramètres et couvrent des cas d’utilisation plus avancés.
>
>[En savoir plus sur les landing pages dans l&#39;interface utilisateur web de Campaign](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}



Le **Digital Content Editor (DCE)** est un éditeur de contenus HTML qui permet de créer ou modifier facilement des modèles ou du contenu au format HTML dans Adobe Campaign.

Avec le Digital Content Editor, vous pouvez insérer et mettre en forme des éléments de page, et mapper des champs de base de données à des éléments d‘une page HTML. Cet éditeur est disponible lors de la création d’une page pour une application web ou de la création de diffusions basées sur un modèle du DCE.

>[!NOTE]
>
>Si vous devez ajouter du code JavaScript côté serveur, utilisez des blocs de personnalisation. Consultez la [documentation de Campaign v8](https://experienceleague.adobe.com/fr/docs/campaign/campaign-v8/send/personalize/personalization-blocks.html?lang=fr){target="_blank"}.

>[!CAUTION]
>
>Toutes les ressources externes doivent être référencées avec une URL HTTPS.

## Étapes clés d‘utilisation du Digital Content Editor {#content-editor-general-operation}

Cette section présente les étapes clés de modification et de chargement du contenu modifié avec le DCE, dans le contexte d‘une application web et d‘une conception de diffusion.

Le fonctionnement général est le suivant :

![](assets/dce_schema.png)

Pour créer une **application web** simple, vous devez :

1. Créer une application web - [En savoir plus](creating-a-landing-page.md)
1. Sélectionner un contenu existant ou créer du contenu à partir d‘un modèle standard - [En savoir plus](template-management.md)
1. Modifier et configurer le contenu - [En savoir plus](editing-content.md)
1. Publier l‘application web - [En savoir plus](creating-a-landing-page.md#step-3---publishing-content)

>[!NOTE]
>
>Un exemple complet d’implémentation dans le contexte d’une application web est disponible dans [cette section](creating-a-landing-page.md).

Pour créer une **diffusion email**, vous devez :

1. Créer une diffusion à partir d‘un modèle du DCE - [En savoir plus](use-case-creating-an-email-delivery.md)
1. Sélectionner un contenu existant ou créer un contenu à partir d’un [modèle standard](template-management.md)
1. Modifier et configurer du contenu en ligne
1. Envoyer la diffusion - En savoir plus dans la [documentation de Campaign v8](https://experienceleague.adobe.com/docs/campaign/campaign-v8/send/create-message.html?lang=fr){target="_blank"}

>[!NOTE]
>
>Un exemple complet d’implémentation dans le contexte d’une diffusion par e-mail est disponible dans [ce cas d’utilisation](use-case-creating-an-email-delivery.md).
