---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 4%
---
# WakeupTask

Force le traitement anticipé d&#39;une ou plusieurs tâches en attente.

```text
WakeupTask ( String workflowId, String taskIdentifier, String activityName )
```

## Paramètres

**workflowId** Identifiant ou nom interne du workflow.

**taskIdentifier** L&#39;identifiant de la tâche (champ @taskIdentifier) ou une chaîne vide pour forcer le traitement anticipé de toutes les tâches en attente associées à une activité donnée.

**activityName** Nom de l’activité à laquelle forcer le traitement anticipé de toutes les tâches associées ou une chaîne vide.

## Valeur(s) renvoyée(s)

Aucune.

## Remarques

Si ni taskIdentifier, ni activityName ne sont spécifiés, toutes les tâches en attente sont prises en compte.

## Fonctionnalités

**Schéma :** [xtk:workflow](s-xtk-workflow.md)

**Statique :**

Oui
