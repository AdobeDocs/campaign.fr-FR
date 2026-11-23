---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 23%
---
# setEntry

Ajoute ou met à jour un fichier dans l&#39;archive.

```text
setEntry (filename, buffer)
```

## Paramètres

**nom** Nom du fichier source.

**buffer** MemoryBuffer contenant le fichier.

## Valeur renvoyée

Aucune.

## Remarques

L&#39;archive ne sera pas modifiée sur le disque tant que la méthode [save()](m-zipfile-save.md) n&#39;aura pas été appelée.

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
