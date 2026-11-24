---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 6%
---
# Répondre

Répond à une tâche en cours de type validation.

```text
Reply ( String workflowId, String taskIdentifier, String response, String choice )
```

## Paramètres

**workflowId** Identifiant ou nom interne du workflow.

**taskIdentifier** Identifiant de la tâche de type validation (champ @taskIdentifier).

**réponse** Commentaire associé à la réponse.

**choix** Le choix de la réponse. Ce choix doit correspondre au nom de la transition à activer.

## Valeur(s) renvoyée(s)

Aucune.

## Remarques

L’opérateur actuel doit faire partie du groupe assigné par la tâche.

## Fonctionnalités

**Schéma :** [xtk:workflow](s-xtk-workflow.md)

**Statique :**

Oui
