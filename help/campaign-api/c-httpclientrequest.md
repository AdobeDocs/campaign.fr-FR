---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 6%
---
# HttpClientRequest (classe)

Un objet HttpClientRequest vous permet d&#39;effectuer certaines opérations en tant que client HTTP.

Exemple :

```text
var req = new HttpClientRequest("http://www.somewhere.com/login") var buffer = new MemoryBuffer() buffer.fromString("MyLogin" + ':' + "MyPassword", "iso-8859-1") req.header["Authorization"] = "Basic " + buffer.toBase64() req.header["Content-Type"] = "text/xml; charset=utf-8" req.method = "SEARCH" req.body = "<xml>any content</xml>" req.execute()
```

## « Keep Alive »

L’objet peut être utilisé dans deux modes différents : standard ou keep alive. Le mode standard permet d’envoyer une seule requête, le mode maintien en vie permet d’envoyer plusieurs requêtes tout en maintenant la connexion ouverte. L’état de l’objet dépend de la séquence d’utilisation de la méthode . Si la méthode connect() est appelée, l&#39;objet passe en mode « keep alive ». Exemple

```text
var req = new HttpClientRequest("http://evc-cit.info/cgi-bin/cit042/timeofday.cgi") req.connect() // Now the object is in keep-alive mode, we can sand many requests using // the same connection // Request ten times the time of the cgi var i = 0 while ( i < 10 ) { req.execute() var response = req.reponse i++ } req.disconnect()
```

## Requêtes asynchrones

Les requêtes sont exécutées par défaut en mode bloquant, ce qui signifie que les

[exécuter](m-httpclientrequest-execute.md)

La fonction ne renvoie le contrôle qu’une fois la requête envoyée et la réponse reçue. Il est également possible d’exécuter des requêtes en mode asynchrone. Dans ce cas, le

[exécuter](m-httpclientrequest-execute.md)

La fonction renvoie immédiatement le contrôle et une fonction sera appelée une fois la réponse reçue. Cela permet l’exécution simultanée de plusieurs requêtes. Le programme suivant est un exemple complet qui montre comment exécuter une série de chargements HTTP ouvrant 3 connexions en même temps, où chaque chargement commence une fois le dernier terminé.

```text
var list = [ "http://www.adobe.com/fr/", "http://www.google.com/", "http://www.mozilla.org/", "http://www.linux.org/", "http://www.postgresql.org/"] var requests = [] var complete = function(req, context, status) { if( status == "success" ) logInfo("Receiving " + context + ": " + req.url + ": code = " + req.response.code) else logWarning("Error " + context + ": " + req.url + ": " + status) sendNext(context) } function sendNext(context) { // Repeat until the first execute() passes while( list.length != 0 ) { // Pick one URL from the list var url = list.shift() var req = new HttpClientRequest(url) req.complete = complete try { req.execute(false, true, context, 5000) logInfo("Sending " + url) requests.push(req) return } catch(e) { // Log a message and pick up next item from list logWarning("Failed to send " + url) } } } // Start 3 requests sendNext(1) sendNext(2) sendNext(3) // Wait until all requests are completed HttpClientRequest.wait(requests) logInfo("Finished.")
```

## Méthodes

| Méthode | Description |
| --- | --- |
| [HttpClientRequest](m-httpclientrequest-httpclientrequest.md) | Crée un objet pour exécuter une requête client HTTP. |
| [se connecter](m-httpclientrequest-connect.md) | Ouvre la connexion HTTP et transmet l’objet en mode « keep-alive » |
| [déconnecter](m-httpclientrequest-disconnect.md) | Ferme la connexion HTTP d&#39;un objet en mode « keep-alive ». |
| [exécuter](m-httpclientrequest-execute.md) | Exécute la requête HTTP. |
| [attente](m-httpclientrequest-wait.md) | Attend la fin d’une liste de requêtes asynchrones. |

## Propriétés

| Propriété | Description |
| --- | --- |
| [corps](p-httpclientrequest-body.md) | Corps de la requête HTTP. |
| [terminé](p-httpclientrequest-complete.md) | Fonction à appeler lorsqu&#39;une requête asynchrone est terminée. |
| [en-tête](p-httpclientrequest-header.md) | Un objet JavaScript contenant les en-têtes HTTP de l’en-tête . |
| [méthode](p-httpclientrequest-method.md) | La méthode HTTP, sous la forme d’une chaîne de caractères |
| [response](p-httpclientrequest-response.md) | La réponse de la requête HTTP. Ceci est un objet de type HttpClientResponse |
| [url](p-httpclientrequest-url.md) | Adresse du serveur distant. |

## Fonctionnalités

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
