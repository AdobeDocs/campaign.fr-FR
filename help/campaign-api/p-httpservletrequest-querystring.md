---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '36'
ht-degree: 13%
---
# queryString

Retourne la partie de l&#39;URL de la requête correspondant aux paramètres.

```text
queryString
```

## Remarques

Exemple : queryString de l’URL suivante :

```javascript
      http://adobe.com/nms/test.jst?id=1234&param=dummy#aFragment
```

renvoie la chaîne suivante :

```javascript
id=1234&param=dummy
```

## Fonctionnalités

**Propriété de la classe :** [HttpServletRequest](c-httpservletrequest.md)

**Lecture seule :**

Oui

**Disponible en :**

* JSSP
* WEBAPP
