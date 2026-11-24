---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 73%
---
# constructeur

Services de génération du serveur applicatif

## Méthodes

| Méthode | Description |
| --- | --- |
| [BuildOutputNavTree](sm-builder-buildoutputnavtree.md) | Fusionne les définitions d&#39;arborescence de navigation trouvées dans la base de données avec celle communiquée en paramètre. |
| [BuildOutputSchema](sm-builder-buildoutputschema.md) | Génère un schéma depuis un schéma source. |
| [BuildSchema](sm-builder-buildschema.md) | Génère un schéma depuis un schéma source. |
| [BuildSchemaFromId](sm-builder-buildschemafromid.md) | Génère un schéma depuis l&#39;identifiant d&#39;un schéma source. |
| [BuildSqlSchemaDiff](sm-builder-buildsqlschemadiff.md) | Génère un document décrivant les différences entre la base de données physique et la description logique. |
| [BuildUpdateOneSchemaDiff](sm-builder-buildupdateoneschemadiff.md) | Génère un document décrivant les différences entre une table de la base de données physique et la description logique de cette table. |
| [BuildUpdateSchemaDiff](sm-builder-buildupdateschemadiff.md) | Génère un document décrivant les différences entre la base de données physique et la description logique. |
| [CheckTableExists](sm-builder-checktableexists.md) | Vérifie si une table existe dans la base de données |
| [Créer Une Base De Données](sm-builder-createdb.md) | Crée la base de données |
| [Évaluer JavaScript](sm-builder-evaluatejavascript.md) | Évaluation d&#39;un code JavaScript. |
| [EvaluateJavaScriptTemplate](sm-builder-evaluatejavascripttemplate.md) | Évaluation d&#39;un template JavaScript (JST). |
| [ExecSql](sm-builder-execsql.md) | Exécute un ordre SQL |
| [ExecSqlScript](sm-builder-execsqlscript.md) | Exécute un script SQL |
| [GenCreateDbDDL](sm-builder-gencreatedbddl.md) | Génère le script SQL de création de la base de données. |
| [GenCreateOrUpdateSchemaSequenceDDL](sm-builder-gencreateorupdateschemasequenceddl.md) | Génère le script SQL utilisé pour créer ou mettre à jour la séquence du schéma autoPk. |
| [GenerateNavTree](sm-builder-generatenavtree.md) | Merge toutes les définitions d&#39;arborescences de navigation et sauve le résultat en tant que &#39;xtk:merged&#39;. |
| [GenerateSchema](sm-builder-generateschema.md) | Génère le code d&#39;un schéma depuis des paramètres de haut niveau. |
| [GetDbParams](sm-builder-getdbparams.md) | Récupère les paramètres actuels de la source de données. |
| [GetDefaultNamespace](sm-builder-getdefaultnamespace.md) | Récupère l&#39;espace de noms par défaut. |
| [InstallPackage](sm-builder-installpackage.md) | Installer un package. |
| [InstallPackageImpl](sm-builder-installpackageimpl.md) | Installer un package (méthode interne à ne pas utiliser). |
| [InstallVendorPackages](sm-builder-installvendorpackages.md) | Installer un ou plusieurs packages standards. |
| [RemoveSchemaLinkRef](sm-builder-removeschemalinkref.md) | Supprime le schéma et les références des liens inverses. |
| [ResolvePackageReferences](sm-builder-resolvepackagereferences.md) | Résout les dépendances présentes dans le package |
| [UpdateDb](sm-builder-updatedb.md) | Mettre à jour la base de données. |
| [UpdateSchemaFromDatabase](sm-builder-updateschemafromdatabase.md) | Met à jour le schéma depuis sa représentation physique en base de données. |
| [UpdateTempSchemasFromDatabase](sm-builder-updatetempschemasfromdatabase.md) | Met à jour une collection de schémas depuis leur représentation physique en base de données. |

## Méthodes génériques

| Méthode | Description |
| --- | --- |
| [créer](f-create.md) | Crée une nouvelle entité correspondant à un schéma donné. |
| [charger](f-load.md) | Charge et retourne une entité correspondant à un schéma et une clé donnés. |
| [enregistrer](m-entity-save.md) | Enregistre une entité dans la base de données. |
