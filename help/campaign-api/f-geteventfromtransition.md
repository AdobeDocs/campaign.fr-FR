---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 6%
---
# getEventFromTransition

Renvoie le dernier événement à subir une transition donnée.

```text
getEventFromTransition (transitionName)
```

## Paramètres

**transitionName** Nom interne de la transition.

## Valeur renvoyée

Dernier événement ayant subi une transition donnée ou nul. L&#39;objet correspond à une entité dans le schéma &#39;xtk:workflowEvent&#39;.

## Fonctionnalités

**Disponible en :**

* Workflow
