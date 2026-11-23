---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 8%
---
# Exécuter

Exécute immédiatement un workflow et attend sa fin.

```text
XML workflow = Execute ( String workflowId, Boolean simulationMode, Boolean keepResult, Boolean logSQL )
```

## Paramètres

**workflowId** Identifiant ou nom interne du workflow.

**simulationMode** Simulation de l&#39;exécution.

**keepResult** Conserver les résultats intermédiaires.

**logSQL** Est-il nécessaire d&#39;enregistrer une trace des ordres SQL ?

## Valeur(s) renvoyée(s)

**workflow** Résultat de l’exécution.

## Fonctionnalités

**Schéma :** [xtk:workflow](s-xtk-workflow.md)

**Statique :**

Oui
