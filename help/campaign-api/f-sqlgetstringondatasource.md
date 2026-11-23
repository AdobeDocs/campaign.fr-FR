---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 17%
---
# sqlGetStringOnDataSource

Retourne une chaîne issue d&#39;une requête SQL sur une source de données.

```text
sqlGetStringOnDataSource (query, dataSource [, value1, ... ])
```

## Paramètres

**requête** La requête SQL.

**dataSource** La source de données.

**value1, ...** variables de la requête SQL.

## Valeur renvoyée

Chaîne de texte correspondant à la requête.

## Remarques

Le paramètre « data source » est défini dans [sqlExecOnDataSource(query, dataSource, value1, ...)](f-sqlexecondatasource.md) fonction Les variables facultatives définies en tant que paramètres de cette fonction sont définies dans [sqlGetString(query, value1, ...)](f-sqlgetstring.md)

## Fonctionnalités

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
