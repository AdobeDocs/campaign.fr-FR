---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 17%
---
# getBooleanValue

Renvoie la valeur de nœud booléenne référencée par le XPath donné.

```text
getBooleanValue (xpath)
```

## Paramètres

**chemin**.

## Valeur renvoyée

true si la valeur de texte du nœud référencé est &#39;true&#39; ou &#39;1&#39;, false si la valeur est &#39;false&#39; ou &#39;0&#39;.

## Remarques

La syntaxe du XPath accepte uniquement un sous-ensemble de langues XPath. Le test de valeur n’est pas sensible à la casse. Une exception est générée si le chemin d’accès est mal formé ou si la valeur n’est pas une valeur booléenne valide.

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
