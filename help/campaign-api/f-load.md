---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 11%
---
# charge

> Avertissement :
>
> L’accès via les API de fichiers est limité aux dossiers **var**, **sftp** et temporaires d’Adobe Campaign.

Charge et retourne une entité correspondant à un schéma et une clé donnés.

```text
load (key)
```

## Paramètres

**key** Chaîne de caractères correspondant à la clé de l’entité.

## Valeur renvoyée

Renvoie l’entité sous la forme d’un objet JavaScript.

## Remarques

load n’est pas une fonction globale, mais une méthode de schéma. Pour l’appeler, vous devez lui ajouter le préfixe du schéma souhaité. Par exemple :

```javascript
var delivery = NLWS.nmsDelivery.load("12435")
```

Les propriétés et sous-propriétés de cet objet peuvent être modifiées à volonté. Contrairement à la méthode [get()](f-get.md), le document n’est pas automatiquement enregistré dans la base de données. Vous devez appeler la méthode [save()](m-entity-save.md) sur l’objet . Si l&#39;entité est introuvable dans la base de données, il s&#39;agit d&#39;une erreur et le script est interrompu.

## Fonctionnalités

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
