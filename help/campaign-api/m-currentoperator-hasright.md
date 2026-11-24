---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 34%
---
# hasRight

Vérifie si l’opérateur dispose d’un droit nommé spécifique.

```text
hasRight (name)
```

## Paramètres

**nom** Nom du droit.

## Valeur renvoyée

Vrai si l&#39;opérateur a ce droit.

## Remarques

Exemple:

```javascript
      var hasAdminRight = application.operator.hasRight("admin")
```

## Fonctionnalités

**Méthode de classe :** [CurrentOperator](c-currentoperator.md)

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
