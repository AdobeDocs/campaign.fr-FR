---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 17%
---
# isEqualNode

Compare deux nœuds.

```text
isEqualNode (arg)
```

## Paramètres

**arg** Le deuxième nœud.

## Valeur renvoyée

true si les deux nœuds sont égaux, sinon false.

## Remarques

Deux nœuds sont égaux si les conditions suivantes sont vérifiées :

* Les deux nœuds sont de type .
* Les propriétés nodeName, localName, namespaceURI, prefix et nodeValue doivent être identiques.
* Les deux nœuds sont de type .
* Les attributs doivent être égaux.
* Les nœuds doivent être égaux.

Comme la normalisation peut affecter l’égalité, nous vous recommandons de la normaliser avant de la comparer.

## Fonctionnalités

**Méthode de classe :** [DOMNode](c-domnode.md)

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
