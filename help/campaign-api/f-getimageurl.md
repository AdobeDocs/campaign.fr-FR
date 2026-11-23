---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 31%
---
# getImageUrl

Active la génération de l’URL d’accès aux ressources publiques

```text
getImageUrl (ID|internal name)
```

## Paramètres

**ID\|nom interne** ID de la ressource publique ou nom interne de la ressource.

## Valeur renvoyée

Renvoie l’URL d’accès à la ressource publique.

## Remarques

Les ressources doivent être publiées sur les serveurs frontaux. Exemple:

```xml
              <%= getImageUrl(content.@["banner-id"]) %>Code HTML généré :http://media.adobe.com/res/img/18cd386d9e8b7f35f3477ac6a9efd762.jpg
```

## Fonctionnalités

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Message de diffusion
* Règle de typologie
* Import
* JSSP
* Méthode SOAP
* WebApp
* Workflow
