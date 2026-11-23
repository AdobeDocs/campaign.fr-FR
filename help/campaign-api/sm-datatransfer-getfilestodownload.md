---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 28%
---
# GetFilesToDownload

Retourne la liste des fichiers concernant ce transfert présents sur le serveur

```text
[ XML filesToDownload, XML filesNotToDownload ] = GetFilesToDownload ( Number jobId )
```

## Paramètres

Identifiant du transfert **jobId**

## Valeur(s) renvoyée(s)

**filesToDownload** renvoie la liste des fichiers téléchargeables sous la forme de l’élément \[dataTransfer/properties/filesToDownload\]

**filesNotToDownload** renvoie la liste des fichiers qui ne peuvent pas être téléchargés en tant qu’élément \[dataTransfer/properties/filesNotToDownload\]

## Fonctionnalités

**Schéma :** [xtk:dataTransfer](s-xtk-datatransfer.md)

**Statique :**

Oui
