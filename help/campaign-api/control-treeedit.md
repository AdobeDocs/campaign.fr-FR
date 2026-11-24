---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 1%
---
# TreeEdit

Contrôle pour afficher et modifier différentes valeurs regroupées dans différentes catégories.

![Contrôle TreeEdit](assets/treeedit.253f1374.png)

## Propriétés

**backColor - string** Couleur d&#39;arrière-plan (ombre btn, blanc).

**border - string** Modifie le style du contour de contrôle (uni, double, incrustation, départ, aucun).

**modifiable - chaîne** Autorise la modification (true par défaut).

**font-size - integer** Modifie la taille de la police.

**libellé - chaîne** libellé associé.

**noImage - string** Masque les images des éléments dans la liste.

**nolabel - boolean** Masque le libellé associé.

**readOnly - boolean** Force le contrôle en lecture seule.

## Remarques

Propriétés des sous-éléments

* visibleIf : condition XTK permettant d&#39;afficher ou de masquer l&#39;élément.
* label : libellé de l&#39;élément.
* exprLabel : libellé de l&#39;élément sous forme d&#39;expression.
* xpath : chemin de l&#39;élément.
* img : image de l’élément.

Propriétés des sous-éléments en entrée

* modifiable : valeur modifiable. La valeur par défaut est héritée de l’élément racine.

Propriétés des sous-éléments de conteneur

* collapsed : true\|false Affiche ou masque les sous-éléments.

Exemple:

```xml
<input nolabel="true" type="treeEdit">
  <container label="Text fields">
    <input xpath="@text1"/>
    <input xpath="@text2"/>
    <input xpath="@text3"/>
    <input xpath="@text4"/>
    <input xpath="@text5"/>
  </container>
  <container label="Boolean fields">
    <input xpath="@boolean1"/>
    <input xpath="@boolean2"/>
    <input xpath="@boolean3"/>
  </container>
</input>
    
```
