---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 40%
---
# champs

Renvoie une table qui contient le champ des champs ([SchemaNode](c-schemanode.md)) de la clé.

```text
fields
```

## Remarques

Exemple:

```javascript
var schema = application.getSchema("nms:delivery")
for each(var key in schema.root.keys)
{
  logInfo("Key: " + key.name)
  for each(var field in key.fields)
    logInfo("\t" + field.name + "\t" + field.type)
}
    
```

## Fonctionnalités

**Propriété de la classe :** [SchemaKey](c-schemakey.md)

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
