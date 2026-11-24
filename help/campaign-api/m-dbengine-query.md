---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 6%
---
# requête

Exécute une requête SQL de type SELECT.

```text
query (command [, value1, ... ])
```

## Paramètres

**commande** commande SQL.

**value1, ...** Variables de la commande.

## Valeur renvoyée

Un curseur qui permet d’effectuer une itération sur le résultat de la requête.

## Remarques

Avertissement : contrairement à ce qui est indiqué dans la section Fonctionnalités , la fonction de requête n’est pas disponible dans WebApp. Les variables remplacent les paramètres de la commande . Le type de variable doit correspondre au paramètre déclaré dans la commande . Les types suivants sont disponibles :

* $(sz) string
* Mémo $(m)
* $(l) long
* $(s) court
* $(b) octet
* $(d) double
* $(f) flottant
* $(ts) date et heure
* $(dt) date
* $(tm) fois
* $(dur) timespan

Les paramètres de substitution suivants sont automatiquement remplacés par une valeur et n’ont pas besoin d’une variable liée.

* $(id) Génère un identifiant
* $(id:NmsTrackingLogId) Génère un identifiant grâce à une séquence spécifique
* $(curdate) Date et heure actuelles

L&#39;itération sur le curseur se fait via un « for each » et retourne un tableau pour chaque ligne récupérée. Chaque élément de la table correspond à un champ de la requête et le type d’élément dépend du type de champ. Exemple:

```javascript
var cnx = application.getConnection()

var stmt = cnx.query("SELECT iOperatorId, sName, tsLastModified " +
                     "FROM xtkOperator " +
                     "WHERE iOperatorId > $(l)", 1000)
for each(var row in stmt)
  logInfo(row[0] + " : " + row[1] + " " + row[2])

cnx.dispose()
```

Dans cet exemple, row\[0\] est un nombre qui correspond à iOperatorId, row\[1\] est une chaîne de caractères qui correspond à sName et row\[2\] est une date qui correspond à tsLastModified. L&#39;opérateur a besoin des droits &#39;sql&#39; pour utiliser cette fonction, sinon une exception est levée.

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
