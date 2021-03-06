---
product: campaign
title: Cellules
description: Cellules
feature: Workflows, Targeting Activity
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 7%

---

# Cellules{#cells}

Le **[!UICONTROL Cellules]** L’activité fournit une vue des différents sous-ensembles sous forme de colonnes de données. Il facilite la manipulation des sous-ensembles et est également conçu pour exploiter les fonctionnalités de personnalisation.

![](assets/wf_split_cells.png)

Cette activité peut être configurée pour renseigner des paramètres spécifiques en fonction des besoins de l&#39;utilisateur. Par défaut, le détail de chaque sous-ensemble est présenté dans une fenêtre dédiée, via le **[!UICONTROL Cellules]** et **[!UICONTROL Avancé]** onglets.

![](assets/wf_split_cells_with_customization.png)

Dans l&#39;exemple ci-dessous, le formulaire de saisie a été modifié : a **[!UICONTROL Données]** un onglet a été ajouté pour permettre l&#39;association d&#39;une offre et d&#39;un niveau de priorité pour chaque sous-ensemble.

![](assets/cells-activity-sample.png)

Pour cette configuration, les informations suivantes ont été ajoutées au formulaire de workflow, dans la variable **[!UICONTROL Administration > Paramétrages > Formulaires de saisie]** noeud de l’explorateur Adobe Campaign :

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

La personnalisation des formulaires de saisie dans Adobe Campaign est réservée à des utilisateurs experts. Pour plus d’informations, consultez cette  .
