---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 9%
---
# attente

Attend la fin d’une liste de requêtes asynchrones.

```text
wait (requests,waitAll)
```

## Paramètres

**requêtes** Un tableau de requêtes.

**waitAll** Booléen (par défaut true), attend que toutes les requêtes de la liste de requêtes soient terminées. Lorsque la valeur est définie sur false, si au moins une requête est terminée, la fonction sort de la boucle d’écoute.

## Valeur renvoyée

Aucune.

## Remarques

La fonction ne s’applique pas à une requête, mais est une fonction de la classe HttpClientRequest . Exemple:

```javascript
var req = new HttpClientRequest("http://www.adobe.com/fr/")
req.complete = function(req, context, status) { logInfo(status) }
req.execute(false, true)

HttpClientRequest.wait( [req] )
```

Une requête ne peut être ajoutée à la liste que si elle est asynchrone et si l&#39;appel [execute](m-httpclientrequest-execute.md) n&#39;a pas généré d&#39;exception. Une fois la requête terminée, elle est automatiquement supprimée de la liste. Cela signifie que lorsque la fonction renvoie un contrôle, la table transmise en tant que paramètre est vide. La liste peut être modifiée par la fonction [complete](p-httpclientrequest-complete.md) : par exemple, il est possible de démarrer une nouvelle requête et de l&#39;ajouter à la liste.

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
