---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '69'
ht-degree: 13%
---
# Exporter

Génération et export d’un rapport

```text
Export ( String reportName, XML context, String exportFormat, String fileName, Boolean isAdHoc )
```

## Paramètres

**reportName** Nom interne du rapport

**context** Contexte d&#39;exécution.

**exportFormat** Les valeurs possibles sont : XLS, OOXML\_SS, ODF\_SS, PDF

XLS génère un document Excel 94-2003\
 OOXML\_SS génère un document Excel 2007\
 ODF\_SS génère un document ouvert

**fileName** Nom du fichier de sortie

**isAdHoc** Indique si l’exportation concerne un rapport ad hoc

## Valeur(s) renvoyée(s)

Aucune.

## Fonctionnalités

**Schéma :** [xtk:report](s-xtk-report.md)

**Statique :**

Oui
