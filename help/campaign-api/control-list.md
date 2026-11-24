---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 2%
---
# Liste

Liste de mémoire.

## Propriétés

**backColor - string** Couleur d&#39;arrière-plan (ombre btn, blanc).

**border - string** Modifie le style du contour de contrôle (uni, double, incrustation, départ, aucun).

**modifiable - booléen** Autorise la modification de la liste.

**font-size - integer** Modifie la taille de la police.

**form - string** Formulaire d&#39;édition.

**img - chaîne** image pour chaque ligne.

**libellé - chaîne** libellé associé.

**nolabel - booléen** Aucun libellé.

**notitle - boolean** n’affiche pas le titre des colonnes.

**noToolbar - boolean** Masque la barre d&#39;outils.

**ordered - boolean** autorise la planification de la liste.

**readOnly - boolean** Force le contrôle en lecture seule.

**toobarAlign - chaîne** horizontale \| verticale.

**toobarCaption - string** Libellé affiché dans la barre d&#39;outils.

**zoom - booléen** Affiche le formulaire d’édition.

**zoomOnAdd - boolean** Ouvre un formulaire lorsqu&#39;une ligne est ajoutée.

**xpathIndex - xpath** L&#39;index de la sélection sera stocké à l&#39;emplacement spécifié par ce chemin.

**xpathSelection - xpath** nœud dans lequel le chemin XPATH sera stocké pour atteindre l’élément sélectionné.

## Remarques

Exemple 1 :

```xml
      <input type="list" xpath="dataTransferStep" nolabel="true" editable="false"
       zoom="true" form="xtk:exportSource" zoomOnAdd="true" img="xtk:script.bmp">
  <input xpath="@name" colSize="15"/>
  <input xpath="@active" editable="true" colSize="15"/>
</input>
```

Exemple 2 :

```xml
<input type="list" xpath="operator" zoom="true">
  <input xpath="@name" colSize="15"/>
  <form>
    <input xpath="@name"/>
  </form>
</input>
```
