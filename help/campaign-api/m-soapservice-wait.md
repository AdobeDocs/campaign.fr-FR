---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 16%
---
# attente

Attend la fin d’une liste de requêtes SOAP asynchrones.

```text
wait (requests)
```

## Paramètres

**requêtes** Un tableau de requêtes.

## Valeur renvoyée

Aucune.

## Remarques

La fonction ne s’applique pas à un service, mais est une fonction du bin SoapService. Exemple:

```javascript
...
var req = service.start(1234, "GetOption", sessionToken, "XtkDatabaseId")

// Do some stuff here

// Wait until the end of the request
SoapService.wait( [req] )
```

Une fois la requête terminée, elle est automatiquement supprimée de la liste. Cela signifie que lorsque la fonction renvoie un contrôle, la table transmise en tant que paramètre est vide. La liste peut être modifiée par la fonction [complete](p-soapservice-complete.md) : par exemple, il est possible de démarrer une nouvelle requête et de l&#39;ajouter à la liste.

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
