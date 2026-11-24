---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '39'
ht-degree: 48%
---
# DOMDocument

Crée un document.

```text
DOMDocument (name [, namespaceURI ])
```

## Paramètres

**name** Nom du document.

**namespaceURI** URI de l’espace de noms du document.

## Valeur renvoyée

Aucune.

## Remarques

Exemple:

```javascript
var doc = new DOMDocument("test")
var doc2 = new DOMDocument("html", "http://www.w3.org/1999/xhtml")
```

## Fonctionnalités

**Méthode de classe :** [DOMDocument](c-domdocument.md)

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
