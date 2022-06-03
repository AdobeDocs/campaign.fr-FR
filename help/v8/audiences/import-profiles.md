---
title: Importer des profils dans Campaign
description: Découvrez comment importer des profils dans Campaign
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: b6a5083f-2b5a-4f5b-ad30-d91363752896
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: ht
source-wordcount: '307'
ht-degree: 100%

---

# Importer des profils depuis un fichier{#create-profiles}

Pour renseigner votre base de données Campaign, vous pouvez : [ajouter manuellement des profils](create-profiles.md) ou importer des profils comme décrit ci-dessous. Vous pouvez également utiliser des fichiers importés pour mettre à jour les données de contact.

## Importer des profils avec un workflow {#import-profiles-with-a-wf}

Les workflows peuvent être utiles pour automatiser certains de vos imports. Que vous importiez des données à partir d&#39;un fichier local ou d&#39;un serveur SFTP, vous pouvez utiliser des workflows pour standardiser vos procédures de Data Management.

### Utiliser les données d&#39;une liste : lecture de liste {#data-from-read-list}

Préparez et structurez vos données dans un fichier pour les importer avec un workflow.

Pour plus d&#39;informations sur l&#39;utilisation de l&#39;activité de lecture de liste dans un workflow, reportez-vous à la section [Documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/read-list.html?lang=fr){target=&quot;_blank&quot;}.

### Charger des données depuis un fichier {#data-from-a-file}

Les données traitées dans un workflow peuvent êtes extraites d&#39;un fichier structuré pour qu&#39;elles puissent être importées dans Adobe Campaign.

Vous trouverez une description de l&#39;activité de chargement des données dans la section [Documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/data-loading--file-.html?lang=fr){target=&quot;_blank&quot;}.

Une fois les données collectées, vous pouvez les utiliser dans vos workflows, par exemple pour enrichir une diffusion ou mettre à jour la base de données. Pour en savoir plus à ce sujet, consultez la [documentation de Campaign Classic v7]https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/how-to-use-workflow-data.htmll){target=&quot;_blank&quot;}.

## Imports ponctuels{#import-jobs}

Adobe Campaign offre une fonctionnalité d&#39;import générique qui permet, par exemple, d&#39;extraire une liste de clients ou de prospects qui feront alors partie d&#39;une population cible, ou de fournir à votre base de données des données provenant de fichiers externes.

Les imports génériques sont gérés à partir du menu **[!UICONTROL Profils et cibles > Tâches]** de la page d&#39;accueil d&#39;Adobe Campaign.

![](assets/new-import-job.png)

Les étapes de création d&#39;un import générique sont détaillées dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=fr){target=&quot;_blank&quot;}.
