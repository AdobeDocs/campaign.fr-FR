---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 6%
---
# GetReportData

```text
XML result = GetReportData ( Number cubeId, String queryDef, Boolean selectAll, Boolean useAggregates, XML cube )
```

## Paramètres

Identifiant du cube **cubeId**. Peut être défini sur 0 si le cube est transmis en tant que paramètre.

**queryDef** QueryDef défini dans le rapport

**selectAll** Select all

**useAggregates** Activer l’utilisation des agrégats

**cube** XML décrivant le cube.

## Valeur(s) renvoyée(s)

**résultat**

## Fonctionnalités

**Schéma :** [xtk:olapCube](s-xtk-olapcube.md)

**Statique :**

Oui
