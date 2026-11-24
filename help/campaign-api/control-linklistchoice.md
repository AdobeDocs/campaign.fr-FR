---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 3%
---
# LinkListChoice

Choix d&#39;une ou plusieurs entités.

## Propriétés

**backColor - string** Couleur d&#39;arrière-plan (ombre btn, blanc).

**border - string** Modifie le style du contour de contrôle (uni, double, incrustation, départ, aucun).

**dblClickAction - chaîne** Nom du formulaire à ouvrir lors du double-clic.

**font-size - integer** Modifie la taille de la police.

**libellé - chaîne** libellé associé.

**multiSelection - boolean** autorise la sélection multiple

**nolabel - boolean** Masque le libellé associé.

**readOnly - boolean** Force le contrôle en lecture seule.

**serialize - boolean** Enregistre la dernière sélection dans le fichier configuration.wu de l’utilisateur

**xpath-link - string** Lien de la liste.

## Remarques

Exemples:

```xml
      <input xpath="." type="linkListChoice" xpath-link="operator">
  <input xpath="[/]"  label="Operator or named right "/>
  <input xpath="@type"/>
  <input xpath="comment"/>
  <sysFilter>
    <condition expr="@type <> 1"/>
  </sysFilter>
  <orderBy>
    <node expr="@type"/>
  </orderBy>
</input>
```
