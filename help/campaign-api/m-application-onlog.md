---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 9%
---
# onLog

Ajoute ou supprime une fonction d&#39;interception des messages écrits dans le journal

```text
onLog ( [function ])
```

## Paramètres

**function** La fonction d&#39;interception à ajouter. Si ce paramètre est ignoré, la fonction ajoutée le plus récemment est supprimée.

## Valeur renvoyée

Aucune.

## Remarques

La fonction ajoutée le plus récemment est appelée en premier. La fonction prend un objet avec les propriétés suivantes comme argument :

* type (Nombre) - Type de message (0=erreur, 1=avertissement, 2=information, 3=statut, 4=verbose)
* code (Nombre) - Code d&#39;erreur (0 s&#39;il ne s&#39;agit pas d&#39;une erreur)
* object (String) - Objet lié au message (non utilisé)
* message (String) - Le message

La fonction doit renvoyer une valeur booléenne. La valeur true empêche toutes les fonctions d&#39;interception suivantes de recevoir le message. La fonction est protégée contre la rentrée : elle n&#39;interceptera pas les messages qu&#39;elle a écrits dans le journal lui-même. Exemple:

```javascript
var file = new File("c:/temp/log.txt")
file.open("w")

// Add a new log handler
application.onLog(function(log) {
  file.writeln(log.type.toString() + " " + log.message)
  return true
})

logInfo("This is an information message")
logWarning("This is a warning")

// Remove the log handler
application.onLog()

// This message won't be caught
logInfo("Finished.")

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
