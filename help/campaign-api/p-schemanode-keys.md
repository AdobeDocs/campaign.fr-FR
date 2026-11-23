---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '35'
ht-degree: 45%
---
# clés

Renvoie une table avec les définitions des [clés SchemaKey](c-schemakey.md) du nœud actuel.

```text
keys
```

## Remarques

Exemple:

```javascript
var schema = application.getSchema("nms:delivery")
for each(var key in schema.root.keys)
  logInfo("Key: " + key.name + "\t is-internal: " + key.isInternal)
    
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
