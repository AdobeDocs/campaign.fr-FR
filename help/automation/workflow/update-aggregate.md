---
product: campaign
title: Mise à jour d’agrégat
description: En savoir plus sur l’activité de workflow de mise à jour d’agrégat
feature: Workflows
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 42%

---

# Mise à jour d&#39;agrégat{#update-aggregate}

Les agrégats sont définis au niveau d&#39;un cube, à des fins de reporting. Un onglet **[!UICONTROL Workflow]** est disponible lors du paramétrage d&#39;un agrégat.

Pour plus d&#39;informations sur les cubes et l&#39;utilisation des agrégats dans Adobe Campaign, reportez-vous à la section [Documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/designing-reports-with-cubes/about-cubes.html?lang=fr){target=&quot;_blank&quot;}.


Pour mettre à jour un agrégat, éditez le **[!UICONTROL Mise à jour d&#39;agrégat]** et sélectionnez le cube et l&#39;agrégat à mettre à jour.

Vous pouvez effectuer une **Mise à jour complète** ou **Mise à jour partielle**.

Par défaut, une mise à jour complète est exécutée lors de chaque calcul. Pour activer une mise à jour partielle, sélectionnez l&#39;option correspondante et définissez les conditions de mise à jour.

**Bonne pratique** : une activité **[!UICONTROL Planificateur]** peut être utilisée pour définir la fréquence de mise à jour des calculs.

![](assets/scheduler-and-cube-aggregate.png)
