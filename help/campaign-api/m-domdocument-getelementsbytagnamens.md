---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 20%
---
# getElementsByTagNameNS

Renvoie la liste de tous les éléments du document avec le nom et l’espace de noms spécifiés.

```text
getElementsByTagNameNS (namespaceURI, localName)
```

## Paramètres

**namespaceURI** URI d’espace de noms.

**localName** Nom des éléments recherchés.

## Valeur renvoyée

Tableau contenant la liste des éléments.

## Remarques

Cette méthode crée une table pour chaque appel. Il est donc préférable de conserver la table dans une variable locale plutôt que d&#39;effectuer plusieurs appels.

## Fonctionnalités

**Méthode de classe :** [DOMDocument](c-domdocument.md)

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
