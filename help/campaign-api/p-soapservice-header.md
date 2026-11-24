---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 38%
---
# en-tête

Chaîne de caractères copiée mot pour mot dans l’en-tête SOAP.

```text
header
```

## Remarques

Les chaînes de caractères sont recopiées in-extenso dans l&#39;en-tête SOAP sans vérification. Exemple:

```javascript
      var cnx = new HttpSoapConnection(result.serverURL, "utf-8", HttpSoapConnection.SOAP_11)
var service = new SoapService(cnx, "urn:partner.soap.sforce.com")
service.header = "<ns1:SessionHeader xmlns:ns1='urn:partner.soap.sforce.com'><ns1:sessionId>123456</ns1:sessionId></ns1:SessionHeader>"
```

## Fonctionnalités

**Propriété de la classe :** [SoapService](c-soapservice.md)

**Lecture seule :**

Non

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
