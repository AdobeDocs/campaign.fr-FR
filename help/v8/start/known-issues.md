---
title: Problèmes connus de Campaign v8
description: Problèmes connus dans la dernière version de Campaign
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: e82ae1158926fb6335380626158089c6394377a1
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 3%

---

# Problèmes connus{#known-issues}

Cette page répertorie les problèmes connus identifiés dans la variable **dernière version de Campaign v8**. En outre, les limitations accompagnant Campaign v8 sont répertoriées. [dans cette page](known-limitations.md).


>[!NOTE]
>
>Adobe publie cette liste de problèmes connus à sa propre discrétion. Elle est basée sur le nombre de rapports client, la gravité et la disponibilité de la solution. Si un problème que vous rencontrez n’est pas répertorié, il se peut qu’il ne corresponde pas aux critères de publication sur cette page.

## Modification du problème de l’activité Source de données {#issue-1}

### Description{#issue-1-desc}

Le **Modifier la source de données** l’activité échoue lors du transfert des données de la base de données locale Campaign vers la base de données cloud Snowflake. Lors du changement de direction, l’activité peut générer des problèmes.

### Étapes de production{#issue-1-repro}

1. Connectez-vous à la console cliente et créez un workflow.
1. Ajouter un **Requête** activité et une **Modifier la source de données** activité.
1. Définissez une requête sur la variable **email**, qui est une chaîne.
1. Exécutez le workflow et cliquez avec le bouton droit sur la transition pour visualiser la population : les enregistrements d&#39;email sont remplacés par `****`.
1. Vérifiez les logs de workflow : la valeur **Modifier la source de données** activity interprète ces enregistrements comme des valeurs numériques.

### Message de l&#39;erreur{#issue-1-error}

```
04/13/2022 10:00:18 AM              Executing change data source 'Ok' (step 'Change Data Source')
04/13/2022 10:00:18 AM              Starting 1 connection(s) on pool 'nms:extAccount:ffda tractorsupply_mkt_stage8' (Snowflake, server='adobe-acc_tractorsupply_us_west_2_aws.snowflakecomputing.com', login='tractorsupply_stage8_MKT:tractorsupply_stage8')
04/13/2022 10:00:26 AM              ODB-240000 ODBC error: {*}Numeric value '{*}******{*}{{*}}' is not recognized\{*}   File 'wkf1285541_13_1_0_47504750#458318uploadPart0.chunk.gz', line 1, character 10140   Row 279, column "WKF1285541_13_1_0"["BICUST_ID":1]   If you would like to continue loading when a
04/13/2022 10:00:26 AM              n error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22018
04/13/2022 10:00:26 AM              WDB-200001 SQL statement 'COPY INTO wkf1285541_13_1_0 (SACTIVE, SADDRESS1, SADDRESS2, BICUST_ID, SEMAIL) FROM ( SELECT $1, $2, $3, $4, $5 FROM $$@BULK_wkf1285541_13_1_0$$) FILE_FORMAT = ( TYPE = CSV RECORD_DELIMITER = '\x02' FIELD_DELIMITER = '\x01' FIEL
04/13/2022 10:00:26 AM              D_OPTIONALLY_ENCLOSED_BY = 'NONE') ON_ERROR = ABORT_STATEMENT PURGE = TRUE' could not be executed.
```

### Solution{#issue-1-workaround}

Pour que les données soient transférées de la base de données cloud de Snowflake vers la base de données locale de Campaign et de nouveau vers Snowflake, vous devez utiliser deux **Modifier la source de données** activités.

### Référence interne{#issue-1-ref}

Référence : NEO-45549



## Échec de l’activité de chargement (fichier) en raison d’une barre oblique inverse {#issue-2}

### Description{#issue-2-desc}

Lors de l’injection de données dans la base de données cloud Snowflake avec une activité de chargement de campagne, le processus peut échouer en raison d’une barre oblique inverse présente dans le fichier source. La chaîne n’est pas placée dans une séquence d’échappement et les données ne sont pas traitées correctement sur Snowflake.

Ce problème se produit uniquement si la barre oblique inverse se situe à la fin de la chaîne, par exemple : &quot;Barker\&quot;.


### Étapes de production{#issue-2-repro}

1. Connectez-vous à la console cliente et créez un workflow.
1. Ajouter un **Chargement (fichier)** et configurez-la.
1. Sélectionnez un fichier local avec les caractéristiques décrites ci-dessus.
1. Exécutez le workflow et vérifiez les logs du workflow pour voir l’erreur.


### Message de l&#39;erreur{#issue-2-error}

```
Error:
04/21/2022 4:01:58 PM     loading when an error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22000
04/21/2022 4:01:58 PM    ODB-240000 ODBC error: String '100110668547' is too long and would be truncated   File 'wkf1656797_21_1_3057430574#458516uploadPart0.chunk.gz', line 1, character 0   Row 90058, column "WKF1656797_21_1"["SCARRIER_ROUTE":13]   If you would like to continue
```

### Solution{#issue-2-workaround}

Pour pallier ce problème, exportez les fichiers avec des guillemets doubles autour des valeurs telles que &quot;Barker&quot; et incluez une option de format de fichier FIELD_OPTIONALLY_ENCLOSED_BY = &#39;&quot;&#39;.

### Référence interne{#issue-2-ref}

Référence : NEO-45549


## L&#39;activité de chargement (fichier) n&#39;a pas pu télécharger de fichier sur le serveur {#issue-3}

### Description{#issue-3-desc}

Lors du téléchargement d’un fichier sur le serveur Campaign avec un **Chargement (fichier)** , le processus s’arrête à 100 %, mais ne se termine jamais.

### Étapes de production{#issue-3-repro}

1. Connectez-vous à la console cliente et créez un workflow.
1. Ajouter un **Chargement (fichier)** et configurez-la.
1. Sélectionnez la **Télécharger sur le serveur** .
1. Sélectionnez le fichier sur votre ordinateur local,
1. Cliquez sur **Télécharger**


### Message de l&#39;erreur{#issue-3-error}

Le processus ne se termine jamais.

### Solution{#issue-3-workaround}

Aucun

### Référence interne{#issue-3-ref}

Référence : NEO-47269