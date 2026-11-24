---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '32'
ht-degree: 46%
---
# removeAll

Supprime toutes les entités de la collection.

```text
removeAll ()
```

## Paramètres

Aucune.

## Valeur renvoyée

Aucune.

## Remarques

Exemple:

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
delivery.attachment.removeAll()
delivery.save()
```

## Fonctionnalités

**Méthode de la classe :** [EntityCollection](c-entitycollection.md)

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
