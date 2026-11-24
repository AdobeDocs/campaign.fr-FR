---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 36%
---
# SoapService

Crée un service pour appeler les fonctions d&#39;un service Web.

```text
SoapService (cnx, namespace)
```

## Paramètres

**cnx** La connexion HTTP ([HttpSoapConnection](c-httpsoapconnection.md)).

**espace de noms** du service.

## Valeur renvoyée

Aucune.

## Remarques

Exemple:

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0)
var session = new SoapService(cnx, "xtk:session")
```

## Fonctionnalités

**Méthode de classe :** [SoapService](c-soapservice.md)

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
