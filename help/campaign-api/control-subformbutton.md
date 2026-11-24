---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 2%
---
# BoutonSousFormulaire

Bouton qui ouvre un sous-formulaire.

![Contrôle SubFormButton](assets/button.f0aea09a.png)

## Propriétés

**backColor - string** Couleur d&#39;arrière-plan (ombre btn, blanc).

**border - string** Modifie le style du contour de contrôle (uni, double, incrustation, départ, aucun).

**discardReadOnly - string** Empêche la propagation de la propriété « lecture seule » au sous-formulaire.

**font-size - integer** Modifie la taille de la police.

**img - chaîne** image associée.

**label - string** Libellé du bouton.

**nolabel - string** Permet d&#39;aligner le contrôle sur la colonne de libellé.

**prebuildSubForm - string** Initialise le sous-formulaire à la création du contrôle. Cette option est activée par défaut, mais elle peut être désactivée pour accélérer l’affichage initial.

**obligatoire - booléen** Le champ est obligatoire.

## Remarques

Exemple:

```xml
      <input type="subformbutton" label="Advanced parameters...">
  <form label=" Advanced parameters">
    <input xpath="@stopIfTooManyRejects"/>
    <input xpath="@traceMode"/>
  </form>
</input>
```
