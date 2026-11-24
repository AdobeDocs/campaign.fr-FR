---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 8%
---
# SoapService (classe)

Permet d&#39;effectuer des appels SOAP sur un service Web.

## Blocage des appels

Voici un exemple type d’utilisation : vous devez d’abord créer une connexion, puis un service à l’aide de cette connexion, et enfin déclarer les méthodes SOAP pour ce service. La méthode SOAP est exposée sous la forme d’une méthode JavaScript de l’objet de service.

```text
var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0) var session = new SoapService(cnx, "xtk:session") session.addMethod("GetOption", "xtk:session#GetOption", ["token", "string", "name", "string"], ["value", "string", "type", "byte"]) var result = session.GetOption("admin/", "NmsBroadcast_DefaultProvider") var value = result[0] var type = result[1] logInfo("Value = " + value) logInfo("Type = " + type)
```

## Appels non bloquants

Il est possible d&#39;effectuer des appels non bloquants (asynchrones), c&#39;est-à-dire d&#39;exécuter une requête SOAP vers un serveur et de continuer l&#39;exécution du script sans attendre le résultat. Les principales différences avec le mode de blocage sont les suivantes :

* La connexion doit être créée en mode asynchrone

* Utilisez les

  [start](m-soapservice-start.md)

  fonction.

* Définition d’une

  [terminé](p-soapservice-complete.md)

  fonction sur le service, à appeler à la réception de la réponse.

* Le

  [SoapService.wait](m-soapservice-wait.md)

  La fonction sert à attendre la fin du traitement d&#39;un ensemble de requêtes.

L’exemple de script suivant effectue une série d’appels SOAP « GetOption » vers un serveur Adobe Campaign en ouvrant 3 connexions simultanément.

```text
var list = [ "XtkDatabaseId", "XtkKey", "WdbcTimeZone", "NmsServer_URL", "NmsBroadcast_DefaultProvider"] var requests = [] function complete(service, result, context, status) { if( status == "success" ) logInfo("option " + context + ": value = " + result[0]) else if( status == "fault" ) logInfo("option " + context + ": fault = " + result.message) else logInfo("option " + context + ": " + status) sendNext(service) } function createService() { // Create the connection var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0, true) // Create the service var service = new SoapService(cnx, "xtk:session") service.addMethod("GetOption", "xtk:session#GetOption", ["token", "string", "name", "string"], ["value", "string", "type", "byte"]) // Change the timeout to 5 seconds service.timeout = 5000 // Setup the callback function service.complete = complete return service } function sendNext(service) { if( list.length == 0) return // Pick an item from the list var name = list.shift() // Use the name as context var context = name // Send the request var req = service.start(context, "GetOption", "admin/", name) // Add the request to the wait queue requests.push(req) } // Open 3 connections and start a request on each one sendNext(createService()) sendNext(createService()) sendNext(createService()) SoapService.wait(requests) logInfo("Done.")
```

## Méthodes

| Méthode | Description |
| --- | --- |
| [SoapService](m-soapservice-soapservice.md) | Crée un service pour appeler les fonctions d&#39;un service Web. |
| [addMethod](m-soapservice-addmethod.md) | Déclare une fonction sur le service. |
| [disposer](m-soapservice-dispose.md) | Libère les ressources utilisées par l’objet . |
| [démarrer](m-soapservice-start.md) | Lance une requête en mode asynchrone. |
| [attente](m-soapservice-wait.md) | Attend la fin d’une liste de requêtes SOAP asynchrones. |

## Propriétés

| Propriété | Description |
| --- | --- |
| [terminé](p-soapservice-complete.md) | Fonction à appeler lorsqu&#39;une requête asynchrone est terminée. |
| [en-tête](p-soapservice-header.md) | Chaîne de caractères copiée mot pour mot dans l’en-tête SOAP. |
| [temporisation](p-soapservice-timeout.md) | Temps d&#39;attente maximum en millisecondes dans le cas d&#39;une requête asynchrone. Si ce paramètre n’est pas défini, le temps d’attente est de 5 minutes. |

## Fonctionnalités

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
