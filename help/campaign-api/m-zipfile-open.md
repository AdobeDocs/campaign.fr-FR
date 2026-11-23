---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 18%
---
# ouvert

Charge une archive existante.

```text
open ()
```

## Paramètres

Aucune.

## Valeur renvoyée

Aucune.

## Remarques

Dans le cas d&#39;une archive existante, vous devez d&#39;abord appeler la méthode ⌐[fileCount](p-zipfile-filecount.md) pour récupérer le nombre de fichiers ou [getEntry()](m-zipfile-getentry.md) pour extraire un fichier. La méthode soulève une exception si le fichier n’existe pas ou si le fichier n’est pas une archive valide.

## Fonctionnalités

**Méthode de classe :** [ZipFile](c-zipfile.md)

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
