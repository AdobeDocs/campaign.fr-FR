---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 21%
---
# en-tête

Un objet JavaScript contenant les en-têtes HTTP de l’en-tête .

```text
header
```

## Remarques

Toutes les propriétés de l’objet d’en-tête sont accessibles en mode lecture/écriture et sont énumérables. Chaque propriétaire de l’objet d’en-tête est une entrée dans l’en-tête HTTP de la requête. Les noms de propriété ne sont pas sensibles à la casse (comme pour les en-têtes HTTP). Exemple:

```javascript
var http = new HttpClientRequest(url)

var buffer = new MemoryBuffer()
buffer.fromString(userName + ':' + password, "iso-8859-1")

http.header["Authorization"] = "Basic " + buffer.toBase64()
http.header["Content-Type"] = "text/xml; charset=utf-8"
http.header["Date"] = (new Date()).toGMTString()
//Note: http.header.Date == http.header.date

for( var i in http.header )
logInfo("header[" + i + "] => " + http.header[i])
```

## Fonctionnalités

**Propriété de la classe :** [HttpClientRequest](c-httpclientrequest.md)

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
