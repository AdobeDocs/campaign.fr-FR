---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '34'
ht-degree: 44%
---
# GenCreateOrUpdateSchemaSequenceDDL

Génère le script SQL utilisé pour créer ou mettre à jour la séquence du schéma autoPk.

```text
String sqlDDL = GenCreateOrUpdateSchemaSequenceDDL ( String schemaId, String newSequence, String oldSequence )
```

## Paramètres

Identifiant du schéma **schemaId**

**newSequence** Nouvelle séquence

**oldSequence** Ancienne séquence

## Valeur(s) renvoyée(s)

Script SQL **sqlDDL**

## Fonctionnalités

**Schéma :** [xtk:builder](s-xtk-builder.md)

**Statique :**

Oui
