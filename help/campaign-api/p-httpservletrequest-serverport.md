---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 11%
---
# serverPort

Renvoie le numéro de port utilisé pour contacter le serveur.

```text
serverPort
```

## Remarques

Exemple : serverPort de l’URL suivante :

```javascript
http://adobe.com:8080/nms/test.jst
```

renvoie la chaîne suivante :

```javascript
8080
```

serverPort de l’URL suivante :

```javascript
http://adobe.com/nms/test.jst
```

renvoie la chaîne suivante :

```javascript
80
```

## Fonctionnalités

**Propriété de la classe :** [HttpServletRequest](c-httpservletrequest.md)

**Lecture seule :**

Oui

**Disponible en :**

* JSSP
* WEBAPP
