---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 14%
---
# télécharger

Télécharge un fichier du serveur vers un fichier local ou vers la mémoire.

```text
download (URL [, append ])
```

## Paramètres

**URL** URL du fichier à télécharger.

**append** Par défaut, si le fichier téléchargé existe déjà sur le disque local, il sera remplacé par le nouveau fichier reçu. Si la valeur booléenne est activée, Adobe Campaign écrit le contenu téléchargé dans le fichier portant le même nom avec le contenu existant.

## Valeur renvoyée

Aucune.

## Remarques

Pour récupérer le fichier dans un fichier local, commencez par utiliser la méthode setFile. Exemple:

```javascript
var ftp = new FTP
ftp.setFile("c:/rfc.txt")
ftp.download("ftp://ftp.funet.fi/pub/standards/RFC/rfc2068.txt")
```

## Fonctionnalités

**Méthode de classe :** [FTP](c-ftp.md)

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
