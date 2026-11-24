---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 4%
---
# WorkflowTask (classe)

Statut d’une tâche de workflow.

Une ⌐`WorkflowTask` est une classe qui ne peut pas être instanciée et pour laquelle une seule instance est accessible dans les activités de workflow appelées `task`.

## Méthodes

| Méthode | Description |
| --- | --- |
| [setCompleted](m-workflowtask-setcompleted.md) | Indique que la tâche est terminée. |
| [postEvent](m-workflowtask-postevent.md) | Active une transition. |
| [setNextProcessingDate](m-workflowtask-setnextprocessingdate.md) | Force la prochaine date de traitement par la tâche. |
| [doneTransition](m-workflowtask-donetransition.md) | Renvoie la transition « terminé » de l’activité. |
| [errorTransition](m-workflowtask-errortransition.md) | Retourne la transition « error » de l&#39;activité. |
| [transitionByType](m-workflowtask-transitionbytype.md) | Renvoie la transition correspondant au type donné. |
| [transitionByName](m-workflowtask-transitionbyname.md) | Renvoie les transitions correspondant au nom donné. |
| [transitions](m-workflowtask-transitions.md) | Retourne la liste des transitions de l’activité. |
| [attente](m-workflowtask-wait.md) | Attend un signal. |

## Fonctionnalités

**Disponible en :**

* Workflow
