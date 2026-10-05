---
title: Importer des profils dans Campaign
description: Découvrez comment importer des profils dans Campaign
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: b6a5083f-2b5a-4f5b-ad30-d91363752896
TQID: 'https://experienceleague.adobe.com/qoVtBCkTTk2DKaR605exVaJvjQ7kjKRoRg-9fJqdoo4'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
    internal-label: Audiences
  - id: f529d0bd-1401-4c88-9833-43228cc1d40f
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 95%
---
# Importer des profils depuis un fichier{#create-profiles}

Pour renseigner votre base de données Campaign, vous pouvez : [ajouter manuellement des profils](create-profiles.md) ou importer des profils comme décrit ci-dessous. Vous pouvez également utiliser des fichiers importés pour mettre à jour les données de contact.

## Importer des profils avec un workflow {#import-profiles-with-a-wf}

Les workflows peuvent être utiles pour automatiser certains de vos imports. Que vous importiez des données à partir d’un fichier local ou d’un serveur SFTP, vous pouvez utiliser des workflows pour standardiser vos procédures de gestion des données.

### Utiliser les données d&#39;une liste : lecture de liste {#data-from-read-list}

Préparez et structurez vos données dans un fichier pour les importer avec un workflow. [En savoir plus](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/read-list.html?lang=fr){target="_blank"}.

### Charger des données depuis un fichier {#data-from-a-file}

Les données traitées dans un workflow peuvent êtes extraites d&#39;un fichier structuré pour qu’elles puissent être importées dans Adobe Campaign. [En savoir plus](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading--file-.html?lang=fr){target="_blank"}.

Une fois les données collectées, vous pouvez les utiliser dans vos workflows, par exemple pour enrichir une diffusion ou mettre à jour la base de données. Pour plus d’informations, consultez [cette section](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/use-workflow-data.html?lang=fr){target="_blank"}.

## Imports ponctuels{#import-jobs}

Adobe Campaign offre une fonctionnalité d&#39;import générique qui permet, par exemple, d&#39;extraire une liste de clients ou de prospects qui feront alors partie d&#39;une population cible, ou de fournir à votre base de données des données provenant de fichiers externes.

Les imports génériques sont gérés à partir du menu **[!UICONTROL Profils et cibles > Traitements]** de la page d’accueil d’Adobe Campaign.

![](assets/new-import-job.png)

Les étapes d&#39;un import générique sont détaillées dans la documentation de [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=fr){target="_blank"}.
