---
product: campaign
title: Cellules
description: Cellules
feature: Workflows, Targeting Activity
exl-id: d85645a6-fc15-4c3a-9d67-d4230224e1f7
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 100%

---

# Cellules{#cells}

L&#39;activité **[!UICONTROL Cellules]** fournit une vue des différents sous-ensembles sous forme de colonnes de données. Elle facilite la manipulation des sous-ensembles et est également conçue pour utiliser les fonctionnalités de personnalisation.

![](assets/wf_split_cells.png)

Cette activité peut être configurée dans le but de renseigner des paramètres spécifiques en fonction des besoins de l&#39;utilisateur. Par défaut, le détail de chaque sous-ensemble est présenté dans une fenêtre dédiée, dans les onglets **[!UICONTROL Cellules]** et **[!UICONTROL Avancé]**.

![](assets/wf_split_cells_with_customization.png)

Dans l&#39;exemple ci-dessous, le formulaire de saisie a été modifié : un onglet **[!UICONTROL Données]** a été ajouté pour permettre l&#39;association d&#39;une offre et d&#39;un niveau de priorité pour chaque sous-ensemble.

![](assets/cells-activity-sample.png)

Pour réaliser ce paramétrage, les informations suivantes ont été ajoutées dans le formulaire des workflows, sous le nœud **[!UICONTROL Administration > Configurations > Formulaires de saisie]** de l&#39;explorateur Adobe Campaign :

```
<container img="nms:miniatures/mini-enrich.png" label="Data">
                <input xpath="@code"/>
                <container xpath="select/node[@alias='@numTest']">
                  <input alwaysActive="true" expr="'long'" type="expr" xpath="@type"/>
                  <input alwaysActive="true" expr="'Priority'" type="expr" xpath="@label"/>
                  <input label="Priority" maxValue="12" minValue="0" type="number"
                         xpath="@value" xpathEditFromType="@type"/>
                </container>
                <container xpath="select/node[@alias='@test']">
                  <input alwaysActive="true" expr="'string'" type="expr" xpath="@type"/>
                  <input alwaysActive="true" expr="'Identifier'" type="expr" xpath="@label"/>
                  <input label="Cell identifier" xpath="@value"/>
                </container>
                <container xpath="select/node[@alias='linkTest']">
                  <input alwaysActive="true" expr="'link'" type="expr" xpath="@type"/>
                  <input alwaysActive="true" expr="'nms:offer'" type="expr" xpath="@dataType"/>
                  <input alwaysActive="true" expr="'Offre'" type="expr" xpath="@label"/>
                  <input computeStringAlias="@valueLabel" label="Offers" notifyPathList="@_cs|@valueLabel"
                         schema="nms:offer" type="linkEdit" xpath="@value"/>
                </container>
```

La personnalisation des formulaires de saisie dans Adobe Campaign est réservée aux utilisateurs et utilisatrices experts.