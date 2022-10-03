---
title: Problèmes connues dans Campaign v8
description: Problèmes connus dans la dernière version de Campaign
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
exl-id: 89a4ab6c-de8e-4408-97d2-8b8e574227f9
source-git-commit: 96e9f5fe5f07ea0c476395d33efa4d6bcf10cf60
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 77%

---

# Problèmes connus{#known-issues}

Cette page répertorie les problèmes connus identifiés dans la variable **dernières versions de Campaign v8**. En outre, les limites de Campaign v8 sont répertoriées sur [cette page](ac-guardrails.md).


>[!NOTE]
>
>Adobe publie cette liste de problèmes connus à sa seule discrétion. Cette liste est établie en fonction du nombre de rapports de clients, la gravité et la disponibilité d’une solution de contournement. Si un problème que vous rencontrez n’est pas répertorié, il se peut qu’il ne réponde pas aux critères de publication sur cette page.

## Campaign v8.3.8{#8.3-issues}

### Modification du problème de l’activité Source de données #1 {#issue-1}

#### Description{#issue-1-desc}

Le **Modifier la source de données** l’activité échoue lors du transfert des données de la base de données locale Campaign vers la base de données cloud Snowflake. Lors du changement de direction, l’activité peut générer des problèmes.

#### Étapes de reproduction{#issue-1-repro}

1. Connectez-vous à la console cliente et créez un workflow.
1. Ajouter un **Requête** activité et une **Modifier la source de données** activité.
1. Définissez une requête sur la variable **email**, qui est une chaîne.
1. Exécutez le workflow et cliquez avec le bouton droit sur la transition pour visualiser la population : les enregistrements d&#39;email sont remplacés par `****`.
1. Vérifiez les logs de workflow : la valeur **Modifier la source de données** activity interprète ces enregistrements comme des valeurs numériques.

#### Message de l&#39;erreur{#issue-1-error}

```sql
04/13/2022 10:00:18 AM              Executing change data source 'Ok' (step 'Change Data Source')
04/13/2022 10:00:18 AM              Starting 1 connection(s) on pool 'nms:extAccount:ffda tractorsupply_mkt_stage8' (Snowflake, server='adobe-acc_tractorsupply_us_west_2_aws.snowflakecomputing.com', login='tractorsupply_stage8_MKT:tractorsupply_stage8')
04/13/2022 10:00:26 AM              ODB-240000 ODBC error: {*}Numeric value '{*}******{*}{{*}}' is not recognized\{*}   File 'wkf1285541_13_1_0_47504750#458318uploadPart0.chunk.gz', line 1, character 10140   Row 279, column "WKF1285541_13_1_0"["BICUST_ID":1]   If you would like to continue loading when a
04/13/2022 10:00:26 AM              n error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22018
04/13/2022 10:00:26 AM              WDB-200001 SQL statement 'COPY INTO wkf1285541_13_1_0 (SACTIVE, SADDRESS1, SADDRESS2, BICUST_ID, SEMAIL) FROM ( SELECT $1, $2, $3, $4, $5 FROM $$@BULK_wkf1285541_13_1_0$$) FILE_FORMAT = ( TYPE = CSV RECORD_DELIMITER = '\x02' FIELD_DELIMITER = '\x01' FIEL
04/13/2022 10:00:26 AM              D_OPTIONALLY_ENCLOSED_BY = 'NONE') ON_ERROR = ABORT_STATEMENT PURGE = TRUE' could not be executed.
```

#### Solution de contournement{#issue-1-workaround}

Pour que les données soient transférées de la base de données cloud de Snowflake vers la base de données locale de Campaign et de nouveau vers Snowflake, vous devez utiliser deux **Modifier la source de données** activités.

#### Référence interne{#issue-1-ref}

Référence : NEO-45549



### Problème lié à l’activité Modifier la source de données {#issue-2}

#### Description{#issue-2-desc}

Lors de l’injection de données dans la base de données cloud Snowflake avec une activité de campagne **Requête** et **Modifier la source de données**, le processus échoue lorsqu’une barre oblique inverse est présente dans les données. La chaîne source n’est pas placée dans une séquence d’échappement et les données ne sont pas traitées correctement sur Snowflake.

Ce problème ne se produit que si la barre oblique inverse se trouve à la fin de la chaîne, par exemple : `Barker\`.


#### Étapes de reproduction{#issue-2-repro}

1. Connectez-vous à la console cliente et créez un workflow.
1. Ajoutez une activité **Requête** et configurez-la.
1. Sélectionnez les données présentant les caractéristiques décrites ci-dessus.
1. Ajoutez une activité **Modifier la source de données** et configurez-la pour sélectionner la base de données cloud Snowflake.
1. Exécutez le workflow et vérifiez les logs associés pour constater l’erreur.


#### Message de l&#39;erreur{#issue-2-error}

```sql
Error:
04/21/2022 4:01:58 PM     loading when an error is encountered, use other values such as 'SKIP_FILE' or 'CONTINUE' for the ON_ERROR option. For more information on loading options, please run 'info loading_data' in a SQL client. SQLState: 22000
04/21/2022 4:01:58 PM    ODB-240000 ODBC error: String '100110668547' is too long and would be truncated   File 'wkf1656797_21_1_3057430574#458516uploadPart0.chunk.gz', line 1, character 0   Row 90058, column "WKF1656797_21_1"["SCARRIER_ROUTE":13]   If you would like to continue
```

#### Solution de contournement{#issue-2-workaround}

La solution de contournement consiste à exclure les données contenant une barre oblique inverse à la fin de la chaîne ou à les supprimer du fichier source.


#### Référence interne{#issue-2-ref}

Référence : NEO-45549


### L’activité Chargement de données (fichier) a échoué à télécharger le fichier sur le serveur {#issue-3}

#### Description{#issue-3-desc}

Lors du téléchargement d’un fichier sur le serveur Campaign avec une activité **Chargement de données (fichier)**, le processus s’arrête à 100 % mais ne se termine jamais.

#### Étapes de reproduction{#issue-3-repro}

1. Connectez-vous à la console cliente et créez un workflow.
1. Ajoutez une activité **Chargement de données (fichier)** et configurez-la.
1. Sélectionnez l’option **Télécharger sur le serveur**.
1. Sélectionnez le fichier sur votre ordinateur local,
1. Cliquez sur **Télécharger**


#### Message de l’erreur{#issue-3-error}

Le processus ne se termine jamais.

#### Solution de contournement{#issue-3-workaround}

La solution de contournement consiste à utiliser une ancienne console cliente. Cela vous permettra de télécharger le fichier sur le serveur.

En tant qu’administrateur Campaign, vous pouvez télécharger la console cliente Campaign v8.3.1 à partir de la [Distribution logicielle Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/fr/campaign.html?1_group.propertyvalues.property=.%2Fjcr%3Acontent%2Fmetadata%2Fdc%3Aversion&amp;1_group.propertyvalues.operation=equals&amp;1_group.propertyvalues.0_values=target-version%3Acampaign%2F8&amp;orderby=%40jcr%3Acontent%2Fjcr%3AlastModified&amp;orderby.sort=desc&amp;layout=list&amp;p.offset=0&amp;p.limit=4){target=&quot;_blank&quot;}.

Découvrez comment accéder à la distribution logicielle Adobe [sur cette page](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=fr){target=&quot;_blank&quot;}.

Découvrez comment mettre à niveau votre console cliente [sur cette page](connect.md).

#### Référence interne{#issue-3-ref}

Référence : NEO-47269.