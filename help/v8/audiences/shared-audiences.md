---
title: Partager les audiences avec les solutions Adobe Experience Cloud
description: Découvrez comment partager des audiences avec des solutions Adobe Experience Cloud
feature: Audiences, Profiles
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 9bea7904ea4507083d2cf45193877e7a2539d0c7
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 100%

---

# Partager les audiences avec les solutions Adobe Experience Cloud{#shared-audiences}

Option 1 : Sources et destinations AEP

Option 2 : Adobe People/AAM

Vous pouvez intégrer **Adobe Campaign** à **People Core Service** ou Adobe Audience Manager. Vous pourrez alors :

* importer dans Adobe Campaign des audiences/segments provenant de différentes solutions d&#39;Adobe Experience Cloud. L&#39;import d&#39;audiences peut être réalisé depuis les listes dans Adobe Campaign.

* exporter des listes sous la forme d’audiences partagées Adobe Experience Cloud. Ces audiences peuvent être exploitées dans les différentes solutions d’Adobe Experience Cloud que vous utilisez. L’export d’audiences peut être réalisé à la suite d’un ciblage dans un workflow, à l’aide d’une activité dédiée **[!UICONTROL Mise à jour d’audience partagée]**.

L’intégration prend en charge deux types d’identifiants Adobe Experience Cloud :

* **Identifiant visiteur** : cet identifiant permet de réconcilier des visiteurs Adobe Experience Cloud avec des destinataires Adobe Campaign.
* **Identifiant déclaré** : ce type d’identifiant permet de réconcilier tous les types de données avec les éléments de la base de données Adobe Campaign. Il s’agit de la clé de réconciliation prédéfinie dans Adobe Campaign.

   >[!NOTE]
   >
   > La source de données des ID déclarés peut également être utilisée avec l’intégration de People Core Service.
   >
   >Si vous utilisez l’intégration de People Core Service et que vous souhaitez ajouter l’intégration d’Audience Manager, vous aurez besoin de l’aide d’un consultant Adobe Audience Manager. Ce dernier vous aidera à éviter de perdre toutes les synchronisations d’ID collectées lors de la transition vers l’utilisation de cette source de données d’ID déclarés dans un contexte Adobe Audience Manager.

Pour plus d&#39;informations, consultez la section :

[https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=fr](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=fr)

[https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=fr](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=fr)