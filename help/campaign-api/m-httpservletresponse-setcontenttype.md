---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '29'
ht-degree: 20%
---
# setContentType

Modifie le type de document de la réponse.

```text
setContentType (name)
```

## Paramètres

Type MIME **name** du document.

## Valeur renvoyée

Aucune.

## Remarques

Exemple:

```javascript
      response.setContentType("text/html;charset=ISO-8859-1")
```

## Fonctionnalités

**Méthode de classe :** [HttpServletResponse](c-httpservletresponse.md)

**Disponible en :**

* JSSP
* WEBAPP
