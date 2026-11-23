---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 18%
---
# queryWithTypes

Exécute une requête SQL de type SELECT avec spécification du type de colonne.

```text
queryWithTypes (command, types [, value1, ... ])
```

## Paramètres

**commande** commande SQL.

**types** Table contenant le type de colonne.

**value1, ...** variables de commande.

## Valeur renvoyée

Un curseur qui permet d’effectuer une itération sur le résultat de la requête.

## Remarques

Avertissement : contrairement à ce qui est indiqué dans la section Fonctionnalités , la fonction queryWithTypes n’est pas disponible dans WebApp. La fonction est identique à [requête](m-dbengine-query.md), avec le type de colonnes ajouté. Dans la plupart des cas, le type de colonne n’est pas utilisé, car il peut être déduit automatiquement. C&#39;est pourquoi la [requête](m-dbengine-query.md) doit être préférée. Cependant, dans certains cas, en particulier avec les colonnes de type Oracle et date, il peut être nécessaire d’expliciter le type. Les types de colonnes sont des chaînes de caractères dans la liste suivante :

* string
* datetime
* date
* time
* timespan
* double
* float
* boolean
* byte
* short
* long
* int64
* memo
* blob
* link
* bin

Exemple:

```javascript
var cnx = application.getConnection()

var stmt = cnx.query("SELECT iOperatorId, sName, tsLastModified " +
                     "FROM xtkOperator " +
                     "WHERE iOperatorId > $(l)",
                     ["long", "string", "datetime"],
                     1000)
for each(var row in stmt)
  logInfo(row[0] + " : " + row[1] + " " + row[2])

cnx.dispose()
```

L&#39;opérateur doit disposer des droits &#39;sql&#39; pour utiliser cette fonction, sinon une exception est levée.

## Fonctionnalités

**Méthode de classe :** [DBEngine](c-dbengine.md)

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
