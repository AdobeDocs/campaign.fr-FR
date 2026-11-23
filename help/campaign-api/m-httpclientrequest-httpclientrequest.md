---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 30%
---
# HttpClientRequest

Crée un objet pour exécuter une requête client HTTP.

```text
HttpClientRequest ( [URL ])
```

## Paramètres

**URL** URL du destinataire de la requête.

## Valeur renvoyée

Aucune.

## Remarques

Si la commande FTP échoue, une exception est générée. Exemple:

```javascript
var http = new HttpClientRequest("http://www.somewhere.com/login")

var buffer = new MemoryBuffer()
buffer.fromString("MyLogin" + ':' + "MyPassword", "iso-8859-1")

http.header["Authorization"] = "Basic " + buffer.toBase64()
http.header["Content-Type"] = "text/xml; charset=utf-8"

http.method = "SEARCH"
http.body = "<xml>any content</xml>"

http.execute()
       
```

## Fonctionnalités

**Méthode de classe :** [HttpClientRequest](c-httpclientrequest.md)

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
