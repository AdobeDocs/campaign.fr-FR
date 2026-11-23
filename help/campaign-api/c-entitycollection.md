---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 18%
---
# EntityCollection (classe)

Représente une collection d’une entité.

Un tel objet ne peut pas être instancié directement. Vous devez utiliser les méthodes create(), get() ou load().

Les éléments d’une collection peuvent être énumérés avec `for` ou `for each`. Cet exemple illustre une énumération de fichiers associés à une diffusion.

```text
var delivery = NLWS.nmsDelivery.load("12345") for each(var attach in delivery.attachment) logInfo(attach.label)
```

## Méthodes

| Méthode | Description |
| --- | --- |
| [ajouter](m-entitycollection-add.md) | Ajoute une nouvelle entité à la collection. |
| [supprimer](m-entitycollection-remove.md) | Supprime une entité de la collection. |
| [removeAll](m-entitycollection-removeall.md) | Supprime toutes les entités de la collection. |

## Propriétés

| Propriété | Description |
| --- | --- |
| [longueur](p-entitycollection-length.md) | Renvoie le numéro d’entité de la collection. |

## Fonctionnalités

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
