---
title: Problèmes connus de Campaign v8
description: Problèmes connus dans la dernière version de Campaign
feature: Overview
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 099d14ace04df1b98e03be283a6436f49f535958
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 2%

---

# Problèmes connus{#known-issues}

Cette page répertorie les problèmes connus identifiés dans la variable **dernière version de Campaign v8**. En outre, les limitations accompagnant Campaign v8 sont répertoriées. [dans cette page](known-limitations.md).


>[!NOTE]
>
>Adobe publie cette liste de problèmes connus à sa propre discrétion. Elle est basée sur le nombre de rapports client, la gravité et la disponibilité de la solution. Si un problème que vous rencontrez n’est pas répertorié, il se peut qu’il ne corresponde pas aux critères de publication sur cette page.

## Modification du problème de l’activité Source de données {#issue-1}

### Description

Le **Modifier la source de données** l’activité échoue lors du transfert des données de la base de données locale Campaign vers la base de données cloud Snowflake. Lors du changement de direction, l’activité peut générer des problèmes.

### Étapes de production

1. Connectez-vous à la console cliente et créez un workflow.
1. Ajouter un **Requête** activité et une **Modifier la source de données** activité.
1. Définissez une requête sur la variable **email**, qui est une chaîne.
1. Exécutez le workflow et cliquez avec le bouton droit sur la transition pour visualiser la population : les enregistrements d&#39;email sont remplacés par `****`.
1. Vérifiez les logs de workflow : la valeur **Modifier la source de données** activity interprète ces enregistrements comme des valeurs numériques.

### Solution

Pour que les données soient transférées de la base de données cloud de Snowflake vers la base de données locale de Campaign et de nouveau vers Snowflake, vous devez utiliser deux **Modifier la source de données** activités.

### Référence interne

Référence : NEO-45549


## L&#39;activité de chargement (fichier) n&#39;a pas pu télécharger de fichier sur le serveur {#issue-2}

### Description

Le téléchargement du fichier sur le serveur Campaign s’arrête à 100 % de progression, mais ne se termine jamais.

### Étapes de production

1. Connectez-vous à la console cliente et créez un workflow.
1. Ajouter un **Chargement (fichier)** et configurez-la.
1. Sélectionnez la **Télécharger sur le serveur** .
1. Sélectionnez le fichier sur votre ordinateur local,
1. Cliquez sur **Télécharger**

### Solution

Aucun

### Référence interne

Référence : NEO-47269