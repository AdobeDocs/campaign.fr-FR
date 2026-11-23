---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '32'
ht-degree: 15%
---
# serverName

Renvoie le nom du serveur de requête.

```text
serverName
```

## Remarques

Exemple : serverName de l&#39;URL suivante :

```javascript
      http://adobe.com:8080/nms/test.jst?id=1234&param=dummy#aFragment
```

renvoie la chaîne suivante :

```javascript
adobe.com
```

## Fonctionnalités

**Propriété de la classe :** [HttpServletRequest](c-httpservletrequest.md)

**Lecture seule :**

Oui

**Disponible en :**

* JSSP
* WEBAPP
