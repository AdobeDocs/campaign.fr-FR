---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 16%
---
# getEntry

Extrait un fichier de l’archive.

```text
getEntry (filename)
```

## Paramètres

**nom** Nom du fichier dans l&#39;archive.

## Valeur renvoyée

⌐ [MemoryBuffer](c-memorybuffer.md) contenant le contenu du fichier.

## Remarques

L&#39;archive doit avoir été ouverte avec la méthode ⌐[open()](m-zipfile-open.md) avant de pouvoir utiliser cette méthode. Sinon, une exception est générée. Exemple : l’exemple suivant extrait le fichier dir/content.xml d’une archive et l’enregistre dans le dossier /tmp/ .

```javascript
var zip = new ZipFile("/tmp/archive.zip")
zip.open()

var content = zip.getEntry("dir/content.xml")
content.save("/tmp/content.xml")

zip.dispose()
content.dispose()
```

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
