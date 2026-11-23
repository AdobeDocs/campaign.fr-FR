---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 20%
---
# getElementsByTagNameNS

Renvoie la liste de tous les éléments enfants dont le nom est spécifié.

```text
getElementsByTagNameNS (namespaceURI, localName)
```

## Paramètres

**namespaceURI** L’URI de l’espace de noms des éléments recherchés.

**localName** Nom des éléments recherchés.

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
