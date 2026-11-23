---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 10%
---
# CodeEdit

Contrôle pour l’édition du code source.

![Contrôle CodeEdit](assets/codeedit.8a744c8b.png)

## Propriétés

**backColor - string** Couleur d&#39;arrière-plan (ombre btn, blanc).

**border - string** Modifie le style du contour de contrôle (uni, double, incrustation, départ, aucun).

**contentType - string** Langue du code source, utilisée pour la coloration syntaxique et d&#39;autres options liées à la langue. Les langues prises en charge sont les suivantes :

* Valeur par défaut
* xml
* dtd
* xsl
* html
* txt
* Javascript
* sql

D’autres langues peuvent également être ajoutées en modifiant le fichier editor.cfg situé dans le même répertoire que nlclient.exe.

**font-size - integer** Modifie la taille de la police.

**libellé - chaîne** libellé associé.

**nolabel - boolean** Masque le libellé associé.

**readOnly - boolean** Force le contrôle en lecture seule.

**toobar - boolean** Affiche ou masque la barre d&#39;outils.

**toolbarAlign - chaîne** Position de la barre d’outils : horizontale ou verticale.

## Remarques

Exemple:

```xml
<input xpath="code" nolabel="true" type="CodeEdit"
       contentType="JavaScript" toolbar="true" toolbarAlign="horizontal"/>
```
