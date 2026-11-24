---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 2%
---
# Modification du diagramme

Ce contrôle est utilisé pour modifier des diagrammes tels que des workflows ou des questionnaires.

![Contrôle DiagramEdit](assets/diagramedit.d750db7e.png)

## Propriétés

**backColor - string** Couleur d&#39;arrière-plan (ombre btn, blanc).

**border - string** Modifie le style du contour de contrôle (uni, double, incrustation, départ, aucun).

**libellé - chaîne** libellé associé.

**nolabel - boolean** Affiche le libellé sous la forme d&#39;une bulle d&#39;aide.

**readOnly - boolean** Force le contrôle en lecture seule.

## Remarques

La barre d&#39;outils peut être personnalisée, chaque sous-élément de ce contrôle correspond à des boutons supplémentaires de la barre d&#39;outils.

```xml
<input type="diagramEdit" xpath=".">
  <input type="separator"/>
  <input img="xtk:properties.png" label="Properties" resetForm="true" prebuildSubForm="true">
    <form name="properties" label="Properties">
      <input xpath="/tmp/@test"/>
    </form>
  </input>
  <input type="separator"/>
  <input img="nms:prepare.png" label="Publish" checkModify="true">
    <form name="properties" label="Properties">
      <input xpath="/tmp/@test"/>
    </form>
  </input>
</input>
```

Pour plus d&#39;informations sur les boutons de la barre d&#39;outils, consultez la documentation du contrôle SubFormButton .
