---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '33'
ht-degree: 9%
---
# WorkflowTransition (classe)

Représente une transition de workflow.

Une transition est un objet opaque qui est récupéré à l’aide de méthodes telles que ou et qui est utilisé pour activer la transition de tâche.

Exemple:

```text
var done = task.doneTransition() task.postEvent(done) task.setCompleted() return 0
```

## Fonctionnalités

**Disponible en :**

* Workflow
