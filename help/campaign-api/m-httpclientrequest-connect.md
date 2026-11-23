---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 13%
---
# connecter

Ouvre la connexion HTTP et transmet l’objet en mode « keep-alive »

```text
connect ( [hasProxy ] [, async ])
```

## Paramètres

**hasProxy** Boolean sur true si vous devez utiliser un proxy HTTP. Par défaut, cette valeur est définie sur false.

**booléen async** défini sur true si la connexion est destinée à exécuter une requête asynchrone. Définissez sur false par défaut.

## Valeur renvoyée

Aucune.

## Remarques

Si la connexion HTTP échoue, une exception est générée. La propriété de réponse ne devient valide qu’après un appel réussi à la fonction d’exécution . N&#39;oubliez pas d&#39;appeler disconnect() une fois la connexion terminée. Exemple:

```javascript
// Mistake with the hostname gogle instead of google
var badHttp = new HttpClientRequest("www.gogle.fr");
try {
  badHttp.connect();
} catch (e) {
  // Here an exception has been raised
}

var goodHttp = new HttpClientRequest("www.google.fr");
try {
  goodHttp.connect();
} catch (e) {
  // No exeception raised
}
...
goodHttp.disconnect();
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
