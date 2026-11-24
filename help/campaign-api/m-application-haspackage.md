---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '42'
ht-degree: 35%
---
# hasPackage

Teste si un package est installé.

```text
hasPackage (name)
```

## Paramètres

**name** Nom complet du package.

## Valeur renvoyée

True si le package est installé.

## Remarques

Exemple:

```javascript
var hasMRM = application.hasPackage("nms:mrm")
```

## Fonctionnalités

**Méthode de classe :** [Application](c-application.md)

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
