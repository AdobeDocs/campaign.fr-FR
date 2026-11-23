---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 6%
---
# setNextProcessingDate

Force la prochaine date de traitement par la tâche.

```text
setNextProcessingDate (timestamp)
```

## Paramètres

**date et heure** Date du prochain traitement. Si vide, le prochain traitement sera effectué immédiatement.

## Valeur renvoyée

Aucune.

## Remarques

* L’utilisation de cette méthode remplace la date du prochain traitement, si elle est fournie par le planificateur.
* Le traitement suivant est toujours effectué par la fonction \*\_reminder().

## Fonctionnalités

**Méthode de classe :** [WorkflowTask](c-workflowtask.md)

**Disponible en :**

* Workflow
