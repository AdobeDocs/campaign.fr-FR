---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '30'
ht-degree: 20%
---
# getHeader

Renvoie un attribut défini dans l’en-tête de la requête.

```text
getHeader (name)
```

## Paramètres

**name** Nom de l’attribut de l’en-tête.

## Valeur renvoyée

Aucune.

## Remarques

Exemple:

```javascript
Host: <%= request.getHeader("host") %>
```

## Fonctionnalités

**Méthode de classe :** [HttpServletRequest](c-httpservletrequest.md)

**Disponible en :**

* JSSP
* WEBAPP
