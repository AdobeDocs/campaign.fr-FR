---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '33'
ht-degree: 51%
---
# BuildSqlSchemaDiff

Génère un document décrivant les différences entre la base de données physique et la description logique.

```text
XML sqlSchemaDiff = BuildSqlSchemaDiff ( XML sqlDiffParam, XML package )
```

## Paramètres

Paramètres de l’extension **sqlDiffParam**

**package** Package initial

## Valeur(s) renvoyée(s)

**sqlSchemaDiff** SqlSchemaDiff généré

## Fonctionnalités

**Schéma :** [xtk:builder](s-xtk-builder.md)

**Statique :**

Oui
