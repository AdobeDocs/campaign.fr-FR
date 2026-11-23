---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 5%
---
# Tuer

Arrête inconditionnellement un workflow.

```text
Kill ( String workflowId )
```

## Paramètres

**workflowId** Identifiant ou nom interne du workflow.

## Valeur(s) renvoyée(s)

Aucune.

## Remarques

Cette méthode est utile si un workflow ne peut pas être arrêté normalement. Cela peut se produire si le workflow ou une tâche ont une affinité particulière ou si le module wfserver gérant cette affinité ne tourne plus. Dans ce cas, le workflow reste marqué « Arrêt demandé » et ne peut être arrêté que par la commande Tuer.

## Fonctionnalités

**Schéma :** [xtk:workflow](s-xtk-workflow.md)

**Statique :**

Oui
