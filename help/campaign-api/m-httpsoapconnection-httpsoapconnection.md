---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 17%
---
# HttpSoapConnection

Crée une connexion HTTP à un serveur SOAP.

```text
HttpSoapConnection (url [, codepage ] [, protocol ] [, async ])
```

## Paramètres

**url** URL du serveur incluant le chemin d’accès.

**codepage** Encodage pour la sérialisation de l’appel SOAP. Ce paramètre facultatif permet de spécifier le codage des caractères. Par défaut, l’encodage est UTF-8. Exemple:

* iso-8859-1
* utf-8
* utf-16

**protocol** Type de protocole SOAP utilisé. Ce paramètre facultatif permet de spécifier le protocole SOAP utilisé, qui est SOAP\_11 par défaut Valeurs possibles :

* SOAP\_11 : protocole SOAP 1.1.
* SOAP\_12 : protocole SOAP 1.2.
* 0 : protocole SOAP interne à Adobe Campaign.

**booléen async** défini sur true si la connexion est destinée à exécuter une requête asynchrone. Définissez sur false par défaut.

## Valeur renvoyée

Aucune.

## Remarques

Exemples:

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp")
```

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "UTF-16", HttpSoapConnection.SOAP_11)
```

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "UTF-8", 0)
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
