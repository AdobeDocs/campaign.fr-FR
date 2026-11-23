---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 28%
---
# en-tête

Un objet contenant tous les en-têtes HTTP.

```text
header
```

## Remarques

Le nom des propriétés n’est pas sensible à la casse. Exemple:

```javascript
      var http = new HttpClientRequest("http://www.google.com/")
http.execute()
var response = http.response
for(var i in response.header)
  logInfo("header[" + i + "] => " + response.header[i])
    
```

Pour récupérer plusieurs en-têtes portant le même nom, utilisez la propriété [headers](p-httpclientresponse-headers.md) plutôt que la propriété header.

## Fonctionnalités

**Propriété de la classe :** [HttpClientResponse](c-httpclientresponse.md)

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
