---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '69'
ht-degree: 7%
---
# Nettoyage

Purge l’historique d’un workflow.

```text
Cleanup ( String workflowId )
```

## Paramètres

**workflowId** Identifiant ou nom interne du workflow.

## Valeur(s) renvoyée(s)

Aucune.

## Remarques

Supprime tous les événements traités, les tâches terminées, les tâches ayant échoué et les messages du journal. Supprime également la progression du diagramme si le workflow est terminé. Cette méthode supprime uniquement les données qui ne sont plus utilisées par le moteur de workflow et n’a aucune incidence sur le comportement du workflow.

## Fonctionnalités

**Schéma :** [xtk:workflow](s-xtk-workflow.md)

**Statique :**

Oui
