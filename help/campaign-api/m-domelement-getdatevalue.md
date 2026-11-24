---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 20%
---
# getDateValue

Renvoie la valeur de type date+heure de la référence de nœud d’après le XPath donné.

```text
getDateValue (xpath)
```

## Paramètres

**chemin**.

## Valeur renvoyée

Un objet de type Date correspondant à la valeur du nœud référencé.

## Remarques

La syntaxe du XPath accepte uniquement un sous-ensemble de langues XPath. Une exception est générée si le chemin d’accès est mal formé ou si la valeur n’est pas une date valide.

## Fonctionnalités

**Méthode de classe :** [DOMElement](c-domelement.md)

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Message de diffusion
* Règle de typologie
* Import
* JSSP
* Méthode SOAP
* WebApp
* Workflow
