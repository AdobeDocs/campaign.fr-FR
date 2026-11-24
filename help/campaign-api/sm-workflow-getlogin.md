---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 3%
---
# GetLogin

Retourne les informations du compte d&#39;exécution.

```text
[ Number id, String login, String cs ] = GetLogin ( String workflowId )
```

## Paramètres

**workflowId** Identifiant ou nom interne du workflow.

## Valeur(s) renvoyée(s)

**id** Identifiant de l’opérateur ou 0 si aucun opérateur n’est associé à ce workflow.

**login** Login de l&#39;opérateur ou chaîne vide si aucun opérateur n&#39;est associé à ce workflow.

**cs** Chaîne de description de l’opérateur ou chaîne vide si aucun opérateur n’est associé à ce workflow.

## Remarques

Le compte d&#39;exécution associé à un workflow permet de forcer les droits d&#39;exécution à ceux d&#39;un opérateur spécifique plutôt qu&#39;à ceux de l&#39;opérateur ayant démarré le workflow. Le compte d’exécution n’est pas propagé lorsqu’un workflow est dupliqué.

## Fonctionnalités

**Schéma :** [xtk:workflow](s-xtk-workflow.md)

**Statique :**

Oui
