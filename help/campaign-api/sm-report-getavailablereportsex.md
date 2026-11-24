---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 25%
---
# GetAvailableReportsEx

Récupère la liste des rapports sans les historiques et en tenant compte des conditions/tris donnés et de la pagination

```text
XML reports = GetAvailableReportsEx ( String activeContext, String schema, String selection, XML where, XML orderBy, Number editionMode, Number lineCount, Number startLine, String locationName )
```

## Paramètres

**activeContext** ActiveContext (selection, global)

**schéma** impliqué

**sélection** des identifiants des entités sélectionnées, séparés par des ’,’

**where** Nœud &#39;where&#39; de filtrage

**orderBy** Nœud « orderBy » de tri

**editionMode** Lors de la modification, les rapports non publiés sont également visibles

**lineCount** Nombre de rapports à collecter

**startLine** décalage à appliquer pour la numérotation des pages

**locationName**

## Valeur(s) renvoyée(s)

**rapports** Liste des rapports éligibles

## Fonctionnalités

**Schéma :** [xtk:report](s-xtk-report.md)

**Statique :**

Oui
