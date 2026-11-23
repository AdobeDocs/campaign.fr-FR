---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 21%
---
# se débarrasser

Libère la connexion de toutes les ressources qui lui sont liées.

```text
dispose ()
```

## Paramètres

Aucune.

## Valeur renvoyée

Aucune.

## Remarques

Une connexion créée à l&#39;aide de la méthode [application.getConnection()](m-application-getconnection.md) est libérée automatiquement à la fin du script. L’appel de cette méthode est utile pour les scripts qui peuvent avoir une longue durée de vie.

## Fonctionnalités

**Méthode de classe :** [DBEngine](c-dbengine.md)

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
