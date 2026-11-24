---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 33%
---
# FilesExist

Vérifie si des fichiers sont déjà présents sur le serveur (ou dans la table des ressources).

```text
XML exist = FilesExist ( XML files )
```

## Paramètres

**files** Liste de fichiers (@name) et de leurs clés MD5 (@md5) et booléen indiquant s’il peut s’agir d’une ressource (@checkResource).

## Valeur(s) renvoyée(s)

**existe** Liste de résultats (@md5 et @exists)

## Fonctionnalités

**Schéma :** [xtk:job](s-xtk-job.md)

**Statique :**

Oui
