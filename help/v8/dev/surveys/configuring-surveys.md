---
product: campaign
title: Configurer des questionnaires en ligne
description: Découvrez comment configurer des questionnaires en ligne
feature: Surveys
version: Campaign v8, Campaign Classic v7
exl-id: 387bc362-4064-4181-9385-8e0c3423ba3e
TQID: 'https://experienceleague.adobe.com/1BTkZ--FyHkp7u0eya-lmuELDu8AMmeC96eGsonYcVM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
  - id: 71b1c383-45b9-57e0-b8cd-ea2e98a01a26
    internal-label: Surveys
subfeature_v2:
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
source-git-commit: 2ac66c0844ec361de9a1658f666c190fcfac8ffa
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 93%
---
# Configurer des questionnaires en ligne{#configuring-surveys}

>[!AVAILABILITY]
>
>Les questionnaires ne sont pas disponibles pour les [déploiements Campaign FFDA](../../architecture/enterprise-deployment.md).



## Propriétés du questionnaire {#survey-properties}

Les questionnaires en ligne sont entièrement configurables et personnalisables pour répondre à vos besoins. Les paramètres doivent être renseignés dans la fenêtre des propriétés.

Les paramètres disponibles sont présentés dans [ce document &#x200B;](../web/defining-web-forms-properties.md).

![](assets/s_ncs_admin_survey_properties_general.png)

## Stockage des données d&#39;un questionnaire {#survey-data-storage}

Par défaut, les champs des formulaires Web sont stockés dans la table des destinataires. Vous pouvez modifier la table utilisée en sélectionnant une nouvelle table dans le champ **[!UICONTROL Type de document]**. L&#39;icône **[!UICONTROL Loupe]** permet de visualiser le contenu de la table sélectionnée.

Les réponses fournies par les utilisateurs dans les questionnaires et qui ne sont pas stockées dans des champs (mais dans des variables locales) sont stockées dans la table **Réponses aux questionnaires**. Vous pouvez modifier le schéma utilisé à partir du champ **[!UICONTROL Bibliothèque]**. Ce champ n’est disponible que pour les **questionnaires**.
