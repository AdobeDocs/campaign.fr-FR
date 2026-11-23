---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '62'
ht-degree: 25%
---
# ZipFile

> Avertissement :
>
> L’accès via les API de fichiers est limité aux dossiers **var**, **sftp** et temporaires d’Adobe Campaign.

Crée un nouvel objet Zip associé à un fichier.

```text
ZipFile (filename)
```

## Paramètres

**nom_fichier** Nom de l’archive à charger ou à créer.

## Valeur renvoyée

Aucune.

## Remarques

Exemple:

```javascript
var zip = new ZipFile("/tmp/archive.zip")
```

## Fonctionnalités

**Méthode de classe :** [ZipFile](c-zipfile.md)

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
