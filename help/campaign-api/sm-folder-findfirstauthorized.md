---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 28%
---
# FindFirstAuthorized

Trouve le premier dossier accessible pour l&#39;utilisateur courant remplissant la condition folderFilter

```text
XML folderEntity = FindFirstAuthorized ( String folderFilter, Boolean writeAccess, Number orgUnit )
```

## Paramètres

**folderFilter** Filtre sur les dossiers

**writeAccess** Le dossier renvoyé doit pouvoir être écrit

**orgUnit** Le dossier renvoyé doit être compatible avec l’entité organisationnelle spécifiée

## Valeur(s) renvoyée(s)

**folderEntity** Renvoie l&#39;entité de dossier associée (null si aucun dossier trouvé)

## Fonctionnalités

**Schéma :** [xtk:folder](s-xtk-folder.md)

**Statique :**

Oui
