---
title: Partager les audiences avec les solutions Adobe Experience Cloud
description: Découvrez comment partager des audiences avec des solutions Adobe Experience Cloud
feature: Audiences
role: User
level: Beginner
hide: true
exl-id: c4d30771-db5e-40be-8af6-50f0fab9f9af
TQID: https://experienceleague.adobe.com/Q7eY7lPXlHWEcaj-Hx4Bbqj-hwzMvrlxGGYeN5AxzRE
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 270
ht-degree: 83%

---

# Partager les audiences avec les solutions Adobe Experience Cloud{#shared-audiences}


Option 1 : Sources et destinations AEP

Option 2 : Adobe People/AAM

Vous pouvez intégrer **Adobe Campaign** à **People Core Service** ou Adobe Audience Manager. Vous pourrez alors :

* Importez les audiences/segments partagés de différentes solutions Adobe Experience Cloud dans Adobe Campaign. L&#39;import d&#39;audiences peut être réalisé depuis les listes dans Adobe Campaign.

* exporter des listes sous la forme d’audiences partagées Adobe Experience Cloud ; Ces audiences peuvent être exploitées dans les différentes solutions d’Adobe Experience Cloud que vous utilisez. L’export d’audiences peut être réalisé à la suite d’un ciblage dans un workflow, à l’aide d’une activité dédiée **[!UICONTROL Mise à jour d’audience partagée]**.

L’intégration prend en charge deux types d’identifiants Adobe Experience Cloud :

* **Identifiant visiteur** : ce type d’identifiant permet de réconcilier des visiteurs Adobe Experience Cloud avec des destinataires Adobe Campaign.
* **Identifiant déclaré** : ce type d’identifiant permet de réconcilier tous les types de données avec les éléments de la base de données Adobe Campaign. Dans Adobe Campaign, il est représenté sous la forme d’une clé de réconciliation prédéfinie.

  >[!NOTE]
  >
  > Désormais, la source de données des ID déclarés peut également être utilisée avec l’intégration de People Core Service.
  >
  >Si vous utilisez l’intégration People Core Service et que vous souhaitez ajouter l’intégration Audience Manager, vous aurez besoin de l’aide d’un consultant ou d’une consultante Adobe Audience Manager, qui vous aidera à éviter de perdre toutes les synchronisations d’ID collectées lors de la transition vers l’utilisation de cette source de données d’ID déclarés dans un contexte Adobe Audience Manager.

Pour plus d’informations, consultez la section :

[Documentation de Adobe Audience Manager](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=fr){target="_blank"}

[Guide des composants de l’interface centrale de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=fr){target="_blank"}
