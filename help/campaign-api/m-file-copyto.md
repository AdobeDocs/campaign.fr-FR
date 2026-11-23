---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '40'
ht-degree: 37%
---
# copyTo

Copie un fichier.

```text
copyTo (fileName)
```

## Paramètres

**fileName** Nom du fichier ou du dossier cible (doit être un chemin complet).

## Valeur renvoyée

Aucune.

## Remarques

Exemples:

```javascript
var f = new File("c:/file.txt")
f.copyTo("c:/file2.txt")

var f2 = new File("c:/file.txt")
f2.copyTo("c:/dir/")
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
