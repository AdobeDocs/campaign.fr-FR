---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 28%
---
# fromXMLString

Crée un nouveau document à partir d&#39;une chaîne de caractères XML.

```text
fromXMLString (string)
```

## Paramètres

**chaîne** chaîne de caractères XML.

## Valeur renvoyée

Aucune.

## Remarques

Une exception est générée si l&#39;argument n&#39;est pas un document XML valide. Cette fonction s&#39;applique à la classe DOMDocument. Exemple:

```javascript
var doc = DOMDocument.fromXMLString(
    '<?xml version="1.0" encoding="ISO-8859-1"?>' +
    '<form name="address" namespace="nms" colcount="2"/>')
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
