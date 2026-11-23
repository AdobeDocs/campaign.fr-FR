---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 40%
---
# renameTo

Renomme un fichier.

```text
renameTo (fileName)
```

## Paramètres

**fileName** Nouveau nom de fichier (doit être un chemin d&#39;accès complet).

## Valeur renvoyée

Aucune.

## Remarques

Exemples:

```javascript
var f = new File("c:/file.txt")
f.renameTo("c:/file2.txt")

var f2 = new File("c:/file.txt")
f2.renameTo("c:/dir/")
```

## Fonctionnalités

**Méthode de classe :** [Fichier](c-file.md)

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
