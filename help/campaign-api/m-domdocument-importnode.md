---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 34%
---
# importNode

Crée une copie de nœud à partir d’un autre document.

```text
importNode (importedNode, deep)
```

## Paramètres

Nœud Source **importedNode**.

**deep** true si le nœud complet doit être copié, false dans le cas contraire.

## Valeur renvoyée

Copie du nœud.

## Remarques

Exemple:

```javascript
var result = doc.importNode(rcpResult, true);
doc.root.appendChild(result);
```

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
