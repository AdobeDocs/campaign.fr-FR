---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 11%
---
# findNode

Renvoie une instance de [SchemaNode](c-schemanode.md) ou la valeur null si le nœud n&#39;existe pas et que le paramètre mustExist est défini sur false.

```text
findNode (name [, strict ] [, mustExist ])
```

## Paramètres

**name** XPath représente le nom du nœud à rechercher

**strict** booléen qui indique si (strict à false) ou non, lorsque le nom du dernier élément du chemin n’existe pas tel quel, il doit être recherché en tant qu’attribut ou élément. Par défaut, cette valeur est définie sur true.

**mustExist** Valeur booléenne qui indique si une exception doit être levée si le nœud n’existe pas. true par défaut.

## Valeur renvoyée

Renvoie une instance [SchemaNode](c-schemanode.md) si le nœud est introuvable ou la valeur null si le paramètre mustExist est défini sur false.

## Remarques

Exemple:

```javascript
var schema = application.getSchema("nms:recipient");

logInfo("netSales: " + schema.root.findNode("@netSales"));
logInfo("merchandise/@lastPurchaseDate: " + schema.root.findNode("merchandise/@lastPurchaseDate", true, false));
```

Résultat :

```javascript
netSales: [object NodeDef]
merchandise/@lastPurchaseDate: [object NodeDef]
```

## Fonctionnalités

**Méthode de classe :** [SchemaNode](c-schemanode.md)

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
