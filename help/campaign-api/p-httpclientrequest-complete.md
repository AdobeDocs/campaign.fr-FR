---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 13%
---
# terminé

Fonction à appeler lorsqu&#39;une requête asynchrone est terminée.

```text
complete
```

## Remarques

La fonction doit accepter trois arguments :

* La requête
* Le contexte
* Le statut : « succès », « erreur » ou « délai d’expiration »

Le statut « succès » signifie qu’une réponse a été reçue, mais la réponse peut avoir n’importe quel code (200, 404, 503, etc.). Le statut « erreur » peut indiquer une interruption de la communication d&#39;une réponse mal structurée. Le statut « timeout » signifie que la connexion n’a pas pu être établie ou qu’aucune réponse n’a été reçue dans le délai configuré. Exemple:

```javascript
http.complete = function(req, context, status)
{
  if( status == "success" )
    logInfo("Response code = " + req.response.code)
}
```

## Fonctionnalités

**Propriété de la classe :** [HttpClientRequest](c-httpclientrequest.md)

**Lecture seule :**

Non

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
