---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 17%
---
# SubmitFromModel

Soumet un traitement à partir d&#39;un modèle

```text
Number jobId = SubmitFromModel ( String schema, String where, String methodName, XML diff, Boolean async )
```

## Paramètres

**schéma** Schéma du modèle de traitement

**where** Expression de sélection de modèle

**methodName** Nom de la méthode à appeler

Contenu XML **diff** à ajouter au modèle

**async** Effectuer un envoi de tâche asynchrone

## Valeur(s) renvoyée(s)

**jobId** Identifiant du traitement qui vient d&#39;être créé

## Fonctionnalités

**Schéma :** [xtk:job](s-xtk-job.md)

**Statique :**

Oui
