---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '39'
ht-degree: 12%
---
# projet

Renvoie le nom du protocole utilisé (HTTP, HTTPS, etc.) pour accéder à cette page.

```text
scheme
```

## Remarques

Exemple : le schéma de l’URL suivante :

```javascript
      http://adobe.com/fr:8080/nms/test.jst?id=1234&param=dummy#aFragment
```

renvoie la chaîne suivante :

```javascript
http
```

## Fonctionnalités

**Propriété de la classe :** [HttpServletRequest](c-httpservletrequest.md)

**Lecture seule :**

Oui

**Disponible en :**

* JSSP
* WEBAPP
