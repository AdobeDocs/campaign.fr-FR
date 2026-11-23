---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 7%
---
# SetResolved

Déclare une entité comme n&#39;ayant plus de conflits.

```text
SetResolved ( String conflictId )
```

## Paramètres

**ID de conflit** Identifiant de conflit.

## Valeur(s) renvoyée(s)

Aucune.

## Remarques

Lorsque tous les conflits sont résolus, cette méthode permet de replacer l&#39;entité à son emplacement normal. Tous les attributs et éléments en conflit doivent être résolus avant d’appeler cette méthode.

## Fonctionnalités

**Schéma :** [xtk:conflict](s-xtk-conflict.md)

**Statique :**

Oui
