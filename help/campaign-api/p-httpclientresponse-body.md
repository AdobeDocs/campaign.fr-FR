---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 18%
---
# corps

Corps de la réponse HTTP sous la forme d’un objet MemoryBuffer.

```text
body
```

## Remarques

Le codage du corps de la réponse est accessible via la propriété [codePage](p-httpclientresponse-codepage.md). Le corps de la réponse HTTP est donné sous la forme d&#39;un objet [MemoryBuffer](c-memorybuffer.md). Toutes les méthodes applicables à un [MemoryBuffer](c-memorybuffer.md) sont donc applicables au corps de la réponse HTTP. Exemple:

```javascript
      var http = new HttpClientRequest("http://www.google.com/")
http.execute()
var response = http.response
if( response.code != 200 )
  throw "HTTP request failed with " + response.message
var content = response.body.toString(response.codePage)
```

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
