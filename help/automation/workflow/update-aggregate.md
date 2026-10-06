---
product: campaign
title: Mettre à jour l’agrégat
description: En savoir plus sur l’activité de workflow de mise à jour d’agrégat
feature: Workflows
role: Developer
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 9a213522-bacf-44f9-98a6-caaaf037a0f9
TQID: 'https://experienceleague.adobe.com/k0rl6aa1U0pK2z1dP7aGkDYk15ML3o8I0y-VwspH4mw'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 100%
---
# Mettre à jour l’agrégat{#update-aggregate}

Les agrégats définis dans les [cubes](../../v8/reporting/gs-cubes.md) à des fins de création de rapports, peuvent être mis à jour avec une activité spécifique. Un onglet **[!UICONTROL Workflow]** est disponible lors de la configuration de l’agrégat.

En savoir plus sur les cubes et les agrégats dans [cette section](../../v8/reporting/customize-cubes.md#calculate-and-use-aggregates).

Pour mettre à jour un agrégat, modifiez l’activité **[!UICONTROL Mettre à jour l’agrégat]** et sélectionnez le cube ainsi que l’agrégat à mettre à jour.

Vous pouvez configurer une **Mise à jour complète** ou une **Mise à jour partielle**.

![](assets/update-aggregate-details.png)

Par défaut, une mise à jour complète est exécutée lors de chaque calcul. Pour activer une mise à jour partielle, sélectionnez l’option éponyme et définissez les conditions de mise à jour.

![](assets/update-aggregate-partial.png)

Il est recommandé d’ajouter une activité **[!UICONTROL Planificateur]** pour définir la fréquence de mise à jour des calculs.
