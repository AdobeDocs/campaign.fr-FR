---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 3%
---
# GetValidationParameters

Retourne les paramètres d’une tâche de validation en cours.

```text
XML content = GetValidationParameters ( String workflowId, String taskIdentifier )
```

## Paramètres

**workflowId** Identifiant ou nom interne du workflow.

**taskIdentifier** Identifiant de la tâche de type validation (champ @taskIdentifier).

## Valeur(s) renvoyée(s)

**content** Le document XML contenant les paramètres.

## Remarques

Le document renvoyé contient toutes les informations concernant la validation, qui a répondu et qui peut encore répondre.

* Les attributs title, creationDate, processingDate, timeout, status, abortReason et completionDate correspondent aux attributs de la tâche de validation.
* isAssignee : l’opérateur actuel fait partie du groupe affecté à cette tâche.
* hasResponded : l&#39;opérateur actuel a déjà répondu.
* canReply : l&#39;opérateur courant peut répondre (soit personne n&#39;a encore répondu, soit plusieurs réponses sont autorisées).

## Fonctionnalités

**Schéma :** [xtk:workflow](s-xtk-workflow.md)

**Statique :**

Oui
