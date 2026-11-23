---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 35%
---
# Exécuter

Exécute un traitement de manière synchrone (dans ce mode les informations de progression et l&#39;annulation ne sont pas disponibles).

```text
String id = job.Execute ( String methodName ) const
```

## Paramètres

**methodName** Nom de la méthode à appeler sur l&#39;entité

## Valeur(s) renvoyée(s)

**id** Identifiant du traitement créé (renvoyé même si le traitement a échoué s&#39;il a été créé dans la base de données)

## Fonctionnalités

**Schéma :** [xtk:job](s-xtk-job.md)

**Statique :**

Non

**Const :**

Oui

**Clé uniquement :**

Non
