---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 40%
---
# énumérations

Renvoie la table contenant la liste des [énumérations](c-enumeration.md) définies dans ce schéma.

```text
enumerations
```

## Remarques

Exemple:

```javascript
var schema = application.getSchema("nms:delivery")
for each(var e in schema.enumerations)
{
  logInfo(e.name)
}
```

## Fonctionnalités

**Propriété de la classe :** [Schéma](c-schema.md)

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
