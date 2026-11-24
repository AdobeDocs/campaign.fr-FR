---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 48%
---
# BuildUpdateOneSchemaDiff

Génère un document décrivant les différences entre une table de la base de données physique et la description logique de cette table.

```text
XML sqlSchemaDiff = BuildUpdateOneSchemaDiff ( String schemaId, Boolean useNamingConventions )
```

## Paramètres

Identifiant du schéma **schemaId**

**useNamingConventions** Utilisez les conventions de nommage SQL pour calculer les chemins des nouveaux champs.

## Valeur(s) renvoyée(s)

**sqlSchemaDiff** Schéma généré

## Fonctionnalités

**Schéma :** [xtk:builder](s-xtk-builder.md)

**Statique :**

Oui
