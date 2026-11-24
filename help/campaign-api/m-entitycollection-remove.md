---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 34%
---
# supprimer

Supprime une entité de la collection.

```text
remove (index|object)
```

## Paramètres

**index\|objet** Index de l’entité à supprimer ou de l’entité elle-même.

## Valeur renvoyée

Aucune.

## Remarques

Exemples:

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
delivery.attachment.remove(1)
delivery.save()
```

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
var attach = delivery.attachment[1]
delivery.attachment.remove(attach)
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
