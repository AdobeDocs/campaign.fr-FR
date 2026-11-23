---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 4%
---
# attente

Attend un signal.

```text
wait (timeout)
```

## Paramètres

**délai d&#39;attente** en millisecondes.

## Valeur renvoyée

Valeur booléenne définie sur true si un signal est reçu avant l’expiration du temps d’attente.

## Remarques

Le signal est émis par les méthodes SOAP [Wakeup](sm-workflow-wakeup.md) et [WakeupTask](sm-workflow-wakeuptask.md). Le protocole utilisé (UDP) ne garantit pas la réception des messages. Ce signal n&#39;est utile que pour exécuter une opération plus rapidement. Avertissement : ce signal ne sera jamais reçu dans un sous-workflow. Exemple : Voici un exemple classique d&#39;utilisation : une boucle traite les opérations provenant d&#39;une file d&#39;attente (poll()) puis attend un certain temps entre chaque opération. Un délai supplémentaire est ajouté pour forcer la passivation du workflow.

```javascript
var lifetime = 30 * 60 * 1000 // 30 minutes
var frequency = 30 * 1000 // 30 seconds
var start = new Date().getTime()
while( new Date().getTime() - start < lifetime )
{
  poll()
  task.wait(frequency)
}
 
```

## Fonctionnalités

**Méthode de classe :** [WorkflowTask](c-workflowtask.md)

**Disponible en :**

* Workflow
