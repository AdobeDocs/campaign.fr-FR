---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 25%
---
# getConnection

Retourne une nouvelle connexion au serveur de base de données.

```text
getConnection ()
```

## Paramètres

Aucune.

## Valeur renvoyée

Une [connexion](c-dbengine.md) au serveur de base de données.

## Remarques

Il est possible de libérer la connexion avant la fin de l&#39;exécution du script à l&#39;aide de la méthode [dispose](m-dbengine-dispose.md).

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
