---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 4%
---
# NormalizeField

```text
NormalizeField ( XML selectedWebApp, XML archivedField, String newSQLName, String tableName, String schemaId, Boolean rename )
```

## Paramètres

**selectedWebApp** Liste des questionnaires pouvant contenir le champ à normaliser.

**archivedField** Informations sur le champ à normaliser.

**newSQLName** Nouveau nom SQL de ce champ.

**tableName** Nom de la table qui contiendra le nouveau champ SQL.

**schemaId** Identifiant du schéma (vue) où ajouter une référence appartenant au nouveau champ (facultatif).

**renommer** Renommer également les champs précédemment normalisés.

## Valeur(s) renvoyée(s)

Aucune.

## Fonctionnalités

**Schéma :** [nms:webApp](s-nms-webapp.md)

**Statique :**

Oui
