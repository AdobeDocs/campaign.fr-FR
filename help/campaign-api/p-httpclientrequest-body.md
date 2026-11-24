---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 15%
---
# corps

Corps de la requête HTTP.

```text
body
```

## Remarques

L&#39;objet affecté au corps de la requête est traité comme suit :

* undefined, null, function : ne sont pas considérés comme des éléments envoyables, le corps de la requête HTTP est vide.
* number, boolean, string, XML, Object : transformé en chaîne de caractères en fonction de la méthode toString et codé en fonction du type de contenu de l’en-tête HTTP.
* [MemoryBuffer](c-memorybuffer.md) : le contenu est copié dans le corps de la requête sans modification.

Exemple:

```javascript
var query = "Select \"urn:schemas:calendar:uid\" " // etc...
var apptRequest =
  "<g:searchrequest xmlns:g="DAV:">\n" +
  "  <g:sql>\n" +
        query +
  "  </g:sql>\n" +
  "</g:searchrequest>"
http.body = apptRequest
    
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
