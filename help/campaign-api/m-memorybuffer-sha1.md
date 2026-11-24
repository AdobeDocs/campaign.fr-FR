---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 35%
---
# sha1

Calcule la signature SHA-1 du contenu MemoryBuffer.

```text
sha1 ()
```

## Paramètres

Aucune.

## Valeur renvoyée

Une chaîne de caractères qui est la représentation hexadécimale de la signature SHA-1.

## Remarques

Exemple:

```javascript
var memBuf = new MemoryBuffer();
memBuf.fromString("Hello world", "utf-8");
logInfo(memBuf.sha1()); // Writes down  => 7b502c3a1f48c8609ae212cdfb639dee39673f5e
```

## Fonctionnalités

**Méthode de classe :** [MemoryBuffer](c-memorybuffer.md)

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Message de diffusion
* Règle de typologie
* Import
* JSSP
* Méthode SOAP
* WebApp
* Workflow
