---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 15%
---
# BoutonRadio

Un bouton radio permet d&#39;effectuer un choix parmi plusieurs options. Les balises &lt;input> sont utilisées pour énumérer les options possibles.

![Contrôle RadioButton](assets/radio.11bc90a8.png)

## Propriétés

**backColor - string** Couleur d&#39;arrière-plan (ombre btn, blanc).

**border - string** Modifie le style de bordure du contrôle (uni, double, inséré, départ, aucun).

**checkedValue - chaîne** Valeur liée au choix.

**font-size - integer** Modifie la taille de la police.

**libellé - chaîne** libellé associé.

**nolabel - boolean** Masque le libellé associé.

**readOnly - boolean** Force le contrôle en lecture seule.

## Remarques

Exemple:

```xml
      <input type="RadioButton" xpath="@gender" checkedValue="0" label="Choice 1"/>
<input type="RadioButton" xpath="@gender" checkedValue="1" label="Choice 2"/>
<input type="RadioButton" xpath="@gender" checkedValue="2" label="Choice 3"/>
```
