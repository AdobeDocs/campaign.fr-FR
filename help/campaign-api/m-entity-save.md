---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '32'
ht-degree: 46%
---
# enregistrer

Enregistre une entité dans la base de données.

```text
save ()
```

## Paramètres

Aucune.

## Valeur renvoyée

Aucune.

## Remarques

Exemple:

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
delivery.label = "Diffusion 12345"
delivery.save()
```

## Fonctionnalités

**Méthode de classe :** [Entité](c-entity.md)

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
