---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '84'
ht-degree: 17%
---
# liste

Répertorie le contenu d’un répertoire.

```text
list ( [mask ] [, sort ] [, noCase ])
```

## Paramètres

**mask** Le masque de recherche (\* par défaut).

**sort** true pour trier le résultat (false par défaut).

**noCase** true pour ignorer la classe lors du tri (false par défaut).

## Valeur renvoyée

Une table contenant la liste des fichiers ( [Fichier](c-file.md) ) correspondant au chemin d’accès et au masque spécifiés.

## Remarques

Le nom du répertoire doit se terminer par un / sous Linux et un \\ sous Windows. Exemple:

```javascript
var dir = new File("c:\\temp\\")
var files = dir.list("*.*")
for each (var file in files)
  logInfo(file.name)
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
