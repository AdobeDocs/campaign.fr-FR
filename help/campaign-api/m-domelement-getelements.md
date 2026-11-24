---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 19%
---
# getElements

Retourne la liste des éléments enfants avec le nom renseigné, appartenant à cet élément.

```text
getElements ( [tagName ])
```

## Paramètres

**tagName** Nom des éléments recherchés. Si ce paramètre est omis, la fonction renvoie tous les éléments enfants.

## Valeur renvoyée

Tableau contenant la liste des éléments.

## Remarques

Cette méthode crée une table pour chaque appel. Il est donc préférable de conserver la table dans une variable locale plutôt que d&#39;effectuer plusieurs appels.

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
