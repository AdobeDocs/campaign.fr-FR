---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 21%
---
# joinParts

Renvoie une table d&#39;instances SchemaNode pour lesquelles chaque élément représente une condition de la jointure.

```text
joinParts
```

## Remarques

Chaque élément du tableau possède deux propriétés :

* source - L’élément qui représente le champ de la table source.
* destination - L’élément qui représente le champ de la table de destination.

Exemple:

```javascript
var schema = application.getSchema("nms:recipient")
var root = schema.root

var link = root.children.country
for each(var join in link.joinParts)
{
  logInfo("src = " + join.source.name)
  logInfo("dst = " + join.destination.name)
}
```

## Fonctionnalités

**Propriété de la classe :** [SchemaNode](c-schemanode.md)

**Lecture seule :**

Oui

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
