---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 14%
---
# getSchema

Retourne un mapping sur un schéma Adobe Campaign ou null si le schéma n’existe pas.

```text
getSchema (name [, checkIfUpdated ])
```

## Paramètres

**name** Nom complet du schéma.

**checkIfUpdated** Vérifiez si le schéma a été mis à jour dans le cache. Aucun impact si le schéma a déjà été instancié dans le script.

## Valeur renvoyée

Un mappage de schéma (voir l&#39;objet [Schema](c-schema.md)) ou la méthode lance une exception si aucun schéma ne correspond au nom.

## Remarques

Tous les schémas instanciés dans un script restent alloués en mémoire jusqu’à la fin du script. Exemple:

```javascript
      var schema = application.getSchema("nms:recipient")
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
