---
product: campaign
title: Mise à jour d’agrégat
description: En savoir plus sur l’activité de workflow de mise à jour d’agrégat
feature: Workflows
role: Data Engineer
level: Beginner
source-git-commit: 8d9b8d3e31362c2d69ec0fc6f16ab375538d7f10
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 20%

---

# Mise à jour d’agrégat{#update-aggregate}

Agrégats définis dans [cubes](../../v8/reporting/gs-cubes.md) à des fins de création de rapports, peut être mis à jour avec une activité spécifique. A **[!UICONTROL Workflow]** est disponible lors de la configuration de l’agrégat.

En savoir plus sur les cubes et les agrégats dans [cette section](../../v8/reporting/customize-cubes.md#calculate-and-use-aggregates).

Pour mettre à jour un agrégat, éditez le **[!UICONTROL Mise à jour d&#39;agrégat]** et sélectionnez le cube et l&#39;agrégat à mettre à jour.

Vous pouvez configurer un **Mise à jour complète** ou **Mise à jour partielle**.

![](assets/update-aggregate-details.png)

Par défaut, une mise à jour complète est exécutée lors de chaque calcul. Pour activer une mise à jour partielle, sélectionnez l&#39;option et définissez les conditions de mise à jour.

![](assets/update-aggregate-partial.png)

Il est recommandé d’ajouter une **[!UICONTROL Planificateur]** pour paramétrer la fréquence des mises à jour des calculs.
