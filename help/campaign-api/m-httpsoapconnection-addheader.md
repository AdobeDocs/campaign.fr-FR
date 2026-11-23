---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 26%
---
# addHeader

Ajoute un en-tête HTTP

```text
addHeader (headerName, headerValue)
```

## Paramètres

**headerName** chaîne de caractères correspondant au nom de l’en-tête HTTP.

**headerValue** chaîne de caractères correspondant au contenu de l’en-tête HTTP.

## Valeur renvoyée

Aucune.

## Remarques

Les en-têtes spécifiés de cette manière prévalent sur les en-têtes par défaut lors des appels SOAP. Exemple:

```javascript
      var cnx = new HttpSoapConnection("http://localhost/test/Service1.asmx");
var memBuf = new MemoryBuffer();
memBuf.fromString("rico:pass@word1")
cnx.addHeader("Authorization","Basic " + memBuf.toBase64());
```

## Fonctionnalités

**Méthode de classe :** [HttpSoapConnection](c-httpsoapconnection.md)

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Message de diffusion
* Règle de typologie
* Import
* JSSP
* Méthode SOAP
* WebApp
* Workflow
