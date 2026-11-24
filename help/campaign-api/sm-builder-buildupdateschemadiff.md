---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 41%
---
# BuildUpdateSchemaDiff

Génère un document décrivant les différences entre la base de données physique et la description logique.

```text
XML sqlSchemaDiff = BuildUpdateSchemaDiff ( XML parameters, Boolean useNamingConventions )
```

## Paramètres

**paramètres** Paramètres de mise à jour

**useNamingConventions** Utilisez les conventions de nommage SQL pour calculer les chemins des nouveaux champs.

## Valeur(s) renvoyée(s)

**sqlSchemaDiff** Schéma généré

## Fonctionnalités

**Schéma :** [xtk:builder](s-xtk-builder.md)

**Statique :**

Oui
