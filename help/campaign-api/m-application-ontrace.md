---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 14%
---
# onTrace

Ajoute ou supprime une fonction d&#39;interception de messages de trace.

```text
onTrace ( [function ])
```

## Paramètres

**function** La fonction d&#39;interception à ajouter. Si ce paramètre est ignoré, la fonction ajoutée le plus récemment est supprimée.

## Valeur renvoyée

Aucune.

## Remarques

La fonction prend un objet avec les propriétés suivantes comme argument :

* gravité (chaîne) - La gravité du message (« error », « warning », « info », « status », « verbose »)
* type (chaîne) - Le type de message (« log », « wdbc », etc.)
* message (String) - Le message

La fonction est protégée contre la rentrée : elle n&#39;interceptera pas les messages de trace qu&#39;elle a elle-même créés. Exemple:

```javascript
var file = new File("c:/temp/trace.txt")
file.open("w")

// Add a new trace handler
application.onTrace(function(log) {
  file.writeln(log.gravity.toString() + " " + log.message)
  return true
})

logInfo("This is an information message")
logWarning("This is a warning")

// Remove the trace handler
application.onTrace()

file.close()
```

## Fonctionnalités

**Méthode de classe :** [Application](c-application.md)

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
