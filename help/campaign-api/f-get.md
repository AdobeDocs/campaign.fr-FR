---
source-git-commit: 3319b56a62aa8a8364c7f2f85bc81708a66a5978
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 11%
---
# get

Charge et retourne une entité correspondant à un schéma et une clé donnés.

```text
get ( [key or content ])
```

## Paramètres

**clé ou contenu** Chaîne de caractères correspondant à la clé de l’entité de contenu XML pour créer ou initier une nouvelle entité.

## Valeur renvoyée

Renvoie l’entité sous la forme d’un objet JavaScript.

## Remarques

get n’est pas une fonction globale, mais une méthode de schéma. Pour l’appeler, vous devez lui ajouter le préfixe du schéma souhaité. Par exemple :

```javascript
var delivery = NLWS.nmsDelivery.get("12435")
```

Les propriétés et sous-propriétés de cet objet peuvent être modifiées à volonté. Le document est automatiquement enregistré dans la base de données lorsque le script se termine en cas de modification. S’il ne s’agit pas d’une création et que l’entité ne figure pas déjà dans la base de données, il s’agit d’une erreur et le script est interrompu.

## Fonctionnalités

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
