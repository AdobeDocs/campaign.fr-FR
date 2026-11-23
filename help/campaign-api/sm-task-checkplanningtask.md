---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 6%
---
# VérifierTâchePlanification

Fonction interne utilisée pour vérifier les surcharges dans le planning des opérateurs de la tâche (retourne ’true’ si surcharge). Cette fonction vérifie également la cohérence des planifications de tâches associées et les met à jour si nécessaire.

```text
Boolean workloadAlert = CheckPlanningTask ( Number taskId )
```

## Paramètres

Identifiant de la tâche **taskId**.

## Valeur(s) renvoyée(s)

**workflowAlert** Avertissement de surcharge de ressources

## Fonctionnalités

**Schéma :** [nms:task](s-nms-task.md)

**Statique :**

Oui
