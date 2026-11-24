---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 9%
---
# exécuter

Exécute la requête HTTP.

```text
execute ( [hasProxy ] [, async ] [, reuseaddr ] [, context ] [, timeout ])
```

## Paramètres

**hasProxy** Boolean défini sur true si vous devez utiliser un proxy HTTP. Par défaut, cette valeur est définie sur false.

Booléen **async** défini sur true si la requête est asynchrone. Par défaut, cette valeur est définie sur false.

Booléen **reuseaddr** défini sur true si le socket sous-jacent doit permettre la réutilisation des adresses locales. Par défaut, cette valeur est définie sur false.

**context** Le contexte est tout objet qui sera transféré au deuxième argument de la fonction [complete](p-httpclientrequest-complete.md) en cas de requête asynchrone.Par défaut, cette valeur est définie sur null.

**timeout** Durée d&#39;attente maximale en millisecondes en cas de requête asynchrone. Si ce paramètre n’est pas défini, le temps d’attente est de 5 minutes.

## Valeur renvoyée

Aucune.

## Remarques

Si la connexion HTTP échoue, une exception est générée. La propriété [response](p-httpclientrequest-response.md) n&#39;est valide qu&#39;après un appel réussi de la fonction d&#39;exécution. Exemple:

```javascript
          
        var http = new HttpClientRequest("http://www.google.com")
        http.method = "GET"
        // Note: Here, http.response == undefined
        http.execute()
        var response = http.response
      
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
