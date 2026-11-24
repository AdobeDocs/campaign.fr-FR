---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 34%
---
# method

La méthode HTTP, sous la forme d’une chaîne de caractères

```text
method
```

## Remarques

La valeur de cette propriété est systématiquement passée en majuscules. Exemple:

```javascript
var http = new HttpClientRequest(url)
http.method = "SEARCH"
```

## Fonctionnalités

**Propriété de la classe :** [HttpClientRequest](c-httpclientrequest.md)

**Lecture seule :**

Non

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
