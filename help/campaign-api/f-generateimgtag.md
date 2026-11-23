---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 28%
---
# generateImgTag

Active la génération d’une balise HTML &lt;img> à partir d’une ressource publique.

```text
generateImgTag (ID)
```

## Paramètres

**ID** ID de ressource publique

## Valeur renvoyée

Renvoie la balise HTML &lt;img> avec les propriétés de l’image contenue dans la définition de la ressource publique.

## Remarques

Les ressources doivent être publiées sur les serveurs frontaux. Exemple:

```xml
              <%= generateImgTag(content.@["banner-id"]) %>Code HTML généré :<img src="http://media.adobe.com/res/img/18cd386d9e8b7f35f3477ac6a9efd762.jpg" width="800" height="200" alt="My image"/>
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
