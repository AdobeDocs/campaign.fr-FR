---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 20%
---
# sqlSelect

Exécute une requête SQL et retourne le résultat sous forme de document XML.

```text
sqlSelect (format, query [, dataSource ])
```

## Paramètres

**format** Chaîne séparée par des virgules décrivant le format des données attendues sous la forme d’un nom :type\[:length\] type list docName, \[fieldXPath:type,\]\*

**requête** La requête SQL.

**dataSource** La source de données.

## Valeur renvoyée

Objet XML contenant une liste d’éléments pour chaque ligne du résultat de la requête.

## Remarques

Exemple:

```javascript
var res = sqlSelect("publicUrl,@sstringValue:string",
        "select sstringValue from XtkOption where sname='XtkFileRes_PublicUrl'")
logInfo(res.publicUrl.@sstringValue.toString())
```

```javascript
var xmlRes = sqlSelect("name:string,file:string:64","select relname, relfilenode from  pg_class WHERE relkind='r' AND pg_get_userbyid(relowner)<>'postgres';");
```

## Fonctionnalités

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
