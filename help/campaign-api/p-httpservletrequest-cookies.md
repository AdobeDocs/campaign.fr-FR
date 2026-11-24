---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '36'
ht-degree: 16%
---
# cookies

Retourne les cookies de la requête.

```text
cookies
```

## Remarques

La propriété cookies renvoie un objet , avec un cookie correspondant pour chacune de ses propriétés. Exemple:

```javascript
var cookies = request.cookies
for(var name in cookies)
{
var value = cookies[name].value
document.write(name + " : " + value + "<br>")
}
```

## Fonctionnalités

**Propriété de la classe :** [HttpServletRequest](c-httpservletrequest.md)

**Lecture seule :**

Oui

**Disponible en :**

* JSSP
* WEBAPP
