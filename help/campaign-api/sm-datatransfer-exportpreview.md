---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 16%
---
# ExportPreview

Calcule l&#39;aperçu des colonnes du fichier de sortie sur les premières lignes de la requête

```text
[ XML resultColumns, XML resultXML, String resultSQLRequest ] = ExportPreview ( XML dataTransferStep, Number lineCount, Boolean countMode, String calcFieldName )
```

## Paramètres

**dataTransferStep** Étape du transfert où le champ calculé est défini.

**lineCount** Nombre de lignes à renvoyer

**countMode** Mode comptage de lignes

**calcFieldName** Nom du champ calculé observé. Si vide, il s’agit d’un aperçu global du fichier de sortie.

## Valeur(s) renvoyée(s)

**resultColumns** Renvoie les valeurs des colonnes du fichier d’exportation (line/col/val, line/col/errors).

**resultXML** renvoie le document XML de sortie de la requête.

**resultSQLRequest** Renvoie la requête SQL exécutée.

## Fonctionnalités

**Schéma :** [xtk:dataTransfer](s-xtk-datatransfer.md)

**Statique :**

Oui
