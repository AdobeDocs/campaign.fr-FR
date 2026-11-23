---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 29%
---
# GetFilesToDownload

Retourne la liste des fichiers présents sur le serveur concernant la diffusion.

```text
[ XML filesToDownload, XML filesNotToDownload ] = GetFilesToDownload ( Number deliveryId )
```

## Paramètres

Identifiant de diffusion **deliveryId**

## Valeur(s) renvoyée(s)

**filesToDownload** renvoie la liste des fichiers téléchargeables en tant qu’élément \[properties/filesToDownload\]

**filesNotToDownload** renvoie la liste des fichiers qui ne peuvent pas être téléchargés en tant qu’élément \[properties/filesNotToDownload\]

## Fonctionnalités

**Schéma :** [nms:delivery](s-nms-delivery.md)

**Statique :**

Oui
