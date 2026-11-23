---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 3%
---
# LienSousFormulaire

Lien qui ouvre un sous-formulaire.

![Contrôle SubFormLink](assets/urlbutton.d1cf6f42.png)

## Propriétés

**backColor - string** Couleur d&#39;arrière-plan (ombre btn, blanc).

**border - string** Modifie le style du contour de contrôle (uni, double, incrustation, départ, aucun).

**discardReadOnly - string** Empêche la propagation de la propriété « lecture seule » au sous-formulaire.

**font-size - integer** Modifie la taille de la police.

**img - chaîne** image associée.

**libellé - chaîne** libellé du bouton.

**nolabel - string** Permet d&#39;aligner le contrôle sur la colonne de libellé.

**prebuildSubForm - string** Initialise le sous-formulaire lors de la création du contrôle. Cette option est activée par défaut, mais elle peut être désactivée pour accélérer l’affichage initial.

## Remarques

Exemple:

```xml
      <input type="subformlink" label="Advanced parameters...">
  <form label=" Advanced parameters">
    <input xpath="@stopIfTooManyRejects"/>
    <input xpath="@traceMode"/>
  </form>
</input>
```
