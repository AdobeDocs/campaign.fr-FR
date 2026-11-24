---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 9%
---
# terminé

Fonction à appeler lorsqu&#39;une requête asynchrone est terminée.

```text
complete
```

## Remarques

La fonction doit accepter quatre arguments :

* Le service
* Le résultat
* Le contexte : il s&#39;agit du paramètre transmis à la fonction [start](m-soapservice-start.md)
* Le statut

Le statut peut avoir les valeurs suivantes :

* « succès » signifie qu’un résultat a été reçu.
* « erreur » peut signifier que la communication a été interrompue, que la réponse a été mal structurée ou qu’une erreur HTTP s’est produite.
* « erreur » si une erreur SOAP est renvoyée. Dans ce cas, le résultat contient un objet décrivant l’erreur.
* « délai dépassé » signifie que la connexion n’a pas pu être établie ou qu’aucune réponse n’a été reçue dans le délai configuré.

Lorsque le résultat est « success », le résultat dépend du nombre de paramètres renvoyés :

* annuler si la requête ne renvoie aucune valeur
* La valeur si la requête renvoie un seul paramètre
* une table si la requête renvoie plusieurs paramètres

Lorsque l&#39;état est « default », le résultat est un objet qui contient les propriétés suivantes :

* message : message de description d’erreur.
* object : objet XML contenant le détail de l’erreur.

Exemple:

```javascript
http.complete = function(result, context, status)
{
  if( status == "success" )
    logInfo("Response code = " + result[0])
}
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
