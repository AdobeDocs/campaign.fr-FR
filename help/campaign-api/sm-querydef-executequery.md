---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '38'
ht-degree: 39%
---
# ExecuteQuery

Récupère des données à partir d&#39;une requête

```text
XML output = queryDef.ExecuteQuery () const
```

## Paramètres

Aucune.

## Valeur(s) renvoyée(s)

Document XML de sortie **output**

## Remarques

La requête prend en charge quatre types d’opérations :

* sélectionner
* get
* getIfExists
* count

## Exemple

```javascript
var query = NLWS.xtkQueryDef.create(
  {queryDef: {schema: "xtk:workflow", operation: "select", 
    select: {
        node: [{expr: "@id"},
               {expr: "@label"},
               {expr: "@internalName"}] 
    }, 
    where: {
      condition: [{expr: "[folder/@name]='nmsTechnicalWorkflow'"},
                  {expr: "@production = 1"}]
    }, 
    orderBy: {
      node: {expr: "@internalName", sortDesc: "false"}
    }
  }})

var res = query.ExecuteQuery()

var workflows = res.getElementsByTagName("workflow")
for each (var w in workflows)
  logInfo(w.getAttribute("internalName"))
        
```

## Fonctionnalités

**Schéma :** [xtk:queryDef](s-xtk-querydef.md)

**Statique :**

Non

**Const :**

Oui

**Clé uniquement :**

Non
