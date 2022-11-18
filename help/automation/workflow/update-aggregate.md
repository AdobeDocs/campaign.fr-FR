---
product: campaign
title: Mettre à jour l’agrégat
description: En savoir plus sur l’activité de workflow de mise à jour d’agrégat
feature: Workflows
role: Data Engineer
level: Beginner
source-git-commit: 8d9b8d3e31362c2d69ec0fc6f16ab375538d7f10
workflow-type: ht
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
