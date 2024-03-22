---
title: Partager les audiences avec les solutions Adobe Experience Cloud
description: Découvrez comment partager des audiences avec des solutions Adobe Experience Cloud
feature: Audiences
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: c4d30771-db5e-40be-8af6-50f0fab9f9af
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 85%

---

# Partager les audiences avec les solutions Adobe Experience Cloud{#shared-audiences}


Option 1 : Sources et destinations AEP

Option 2 : Adobe People/AAM

Vous pouvez intégrer **Adobe Campaign** à **People Core Service** ou Adobe Audience Manager. Vous pourrez alors :

* importer dans Adobe Campaign des audiences/segments provenant de différentes solutions d&#39;Adobe Experience Cloud. L&#39;import d&#39;audiences peut être réalisé depuis les listes dans Adobe Campaign.

* Exportez des listes sous la forme d’audiences partagées Adobe Experience Cloud. Ces audiences peuvent être utilisées dans les différentes solutions Adobe Experience Cloud que vous utilisez. L&#39;export d&#39;audiences peut être réalisé à la suite d&#39;un ciblage dans un workflow, à l&#39;aide d&#39;une activité dédiée **[!UICONTROL Mise à jour d&#39;audience partagée]**.

L’intégration prend en charge deux types d’identifiants Adobe Experience Cloud :

* **Identifiant visiteur** : ce type d’identifiant permet de réconcilier des visiteurs Adobe Experience Cloud avec des destinataires Adobe Campaign.
* **Identifiant déclaré** : ce type d’identifiant permet de réconcilier tous les types de données avec les éléments de la base de données Adobe Campaign. Dans Adobe Campaign, il est représenté sous la forme d’une clé de réconciliation prédéfinie.

  >[!NOTE]
  >
  > Désormais, la source de données des ID déclarés peut également être utilisée avec l’intégration People Core Service.
  >
  >Si vous utilisez l’intégration People Core Service et que vous souhaitez ajouter l’intégration Audience Manager, vous aurez besoin de l’aide d’un consultant ou d’une consultante Adobe Audience Manager, qui vous aidera à éviter de perdre toutes les synchronisations d’ID collectées lors de la transition vers l’utilisation de cette source de données d’ID déclarés dans un contexte Adobe Audience Manager.

Pour plus d’informations, consultez la section :

[Documentation Adobe Audience Manager](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=fr){target="_blank"}

[Guide des composants de l’interface centrale de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=fr){target="_blank"}
