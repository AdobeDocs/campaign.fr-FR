---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 20%
---
# fromJXON

Crée un nouveau document à partir d’un objet JSON.

```text
fromJXON (obj)
```

## Paramètres

**obj** Objet JXON représentant le document XML à créer.

## Valeur renvoyée

Aucune.

## Remarques

Les fonctions transmettant un DOMDocument ou un DOMElement en tant que paramètre acceptent également directement un objet JSON. Il n’est pas nécessaire de créer un objet intermédiaire à l’aide de cette fonction. Une exception est générée si l’objet n’est pas un objet JSON valide. Cette fonction s&#39;applique à la classe DOMDocument. Exemple:

```javascript
var doc = DOMDocument.fromJXON(
    {form : {name: "address", "namespace": "nms", colcount: 2}})
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
