---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 5%
---
# SetLogin

Change le compte d&#39;exécution.

```text
SetLogin ( String workflowId, String login )
```

## Paramètres

**workflowId** Identifiant ou nom interne du workflow.

**login** Login de l&#39;opérateur ou chaîne vide si aucun opérateur n&#39;est associé à ce workflow.

## Valeur(s) renvoyée(s)

Aucune.

## Remarques

Le compte d&#39;exécution associé à un workflow permet de forcer les droits d&#39;exécution à ceux d&#39;un opérateur spécifique plutôt qu&#39;à ceux de l&#39;opérateur ayant démarré le workflow. Le compte d’exécution n’est pas propagé lorsqu’un workflow est dupliqué.

## Fonctionnalités

**Schéma :** [xtk:workflow](s-xtk-workflow.md)

**Statique :**

Oui
