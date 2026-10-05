---
title: Partager les audiences avec les solutions Adobe Experience Cloud
description: Découvrez comment partager des audiences avec des solutions Adobe Experience Cloud
feature: Audiences, Profiles
role: User
level: Beginner
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
    internal-label: Audiences
  - id: f529d0bd-1401-4c88-9833-43228cc1d40f
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 95%
---
# Partager les audiences avec les solutions Adobe Experience Cloud{#shared-audiences}

Option 1 : Sources et destinations AEP

Option 2 : Adobe People/AAM

Vous pouvez intégrer **Adobe Campaign** à **People Core Service** ou Adobe Audience Manager. Vous pourrez alors :

* Importez dans Adobe Campaign des audiences/segments partagés provenant de différentes solutions d’Adobe Experience Cloud. L’import d’audiences peut être réalisé depuis les listes dans Adobe Campaign.

* Exportez des listes sous la forme d’audiences partagées Adobe Experience Cloud. Ces audiences peuvent être exploitées dans les différentes solutions d’Adobe Experience Cloud que vous utilisez. L’export d’audiences peut être réalisé à la suite d’un ciblage dans un workflow, à l’aide d’une activité dédiée **[!UICONTROL Mise à jour d’audience partagée]**.

L’intégration prend en charge deux types d’identifiants Adobe Experience Cloud :

* **Identifiant visiteur** : cet identifiant permet de réconcilier des visiteurs Adobe Experience Cloud avec des destinataires Adobe Campaign.
* **Identifiant déclaré** : ce type d’identifiant permet de réconcilier tous les types de données avec les éléments de la base de données Adobe Campaign. Il s’agit de la clé de réconciliation prédéfinie dans Adobe Campaign.

  >[!NOTE]
  >
  > La source de données des ID déclarés peut également être utilisée avec l’intégration de People Core Service.
  >
  >Si vous utilisez l’intégration People Core Service et que vous souhaitez ajouter l’intégration Audience Manager, vous aurez besoin de l’aide d’un consultant ou d’une consultante Adobe Audience Manager, qui vous aidera à éviter de perdre toutes les synchronisations d’ID collectées lors de la transition vers l’utilisation de cette source de données d’ID déclarés dans un contexte Adobe Audience Manager.

Pour plus d’informations, consultez la section :

[Base de connaissances ](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=fr){target="_blank"}.

[Guide des composants de l’interface centrale d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=fr){target="_blank"}.
