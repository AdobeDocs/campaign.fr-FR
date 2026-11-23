---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 19%
---
# getNewIds

Retourne une liste d’identifiants des clés de la base interne.

```text
getNewIds (count [, sequence ])
```

## Paramètres

**count** Nombre d’identifiants que la méthode doit renvoyer.

**séquence** Nom de la séquence à utiliser.

## Valeur renvoyée

Une table contenant la liste des identifiants :

## Remarques

Cette méthode est équivalente aux méthodes SOAP NLWS.xtkSession.GetNewIds() et NLWS.xtkSession.GetNewIdsEx() , tout en étant plus efficace.

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
