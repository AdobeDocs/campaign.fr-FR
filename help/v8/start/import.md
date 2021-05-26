---
solution: Campaign v8
product: Adobe Campaign
title: Prise en main des profils
description: Prise en main des profils
feature: Profils
role: Data Engineer
level: Beginner
exl-id: b0f8c057-dd4e-4284-b5a4-157986a1d95a
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 11%

---

# Importer des données dans Campaign {#ootb-profiles}

Campaign vous aide à ajouter des contacts à la base de données Cloud. Vous pouvez charger un fichier, planifier et automatiser plusieurs mises à jour de contact, collecter des données sur le Web ou saisir des informations de profil directement dans la table des destinataires.

[!DNL :bulb:] Prise en main d&#39; [](audiences.md)
[!DNL :bulb:] audiencesPrésentation du  [modèle de données de Campaign](../dev/datamodel.md)

## Import de profils dans un workflow

Les imports de profil sont configurés dans des modèles dédiés exécutés par le biais de workflows via l&#39;activité **Import**. Ils peuvent être répétés automatiquement selon un planning, par exemple pour automatiser l&#39;échange de données entre plusieurs systèmes d&#39;informations. Pour en savoir plus, consultez la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/import-export-workflows.html).

![](assets/import-wf.png)

En savoir plus dans la documentation de Campaign Classic v7 :

:[!DNL :arrow_upper_right:] : [Prise en main des imports et exports](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/get-started-data-import-export.html)

:[!DNL :arrow_upper_right:]: [Bonnes pratiques en matière d&#39;import et d&#39;export](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/best-practices/import-export-best-practices.html)

:[!DNL :arrow_upper_right:] : [Configurer et exécuter un import](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html)

## Exécution d’imports unitaires

Créez et exécutez une tâche d’importation de données générique pour charger des contacts dans la base de données Cloud.

![](assets/new-import.png)

:[!DNL :arrow_upper_right:] : Découvrez comment exécuter des tâches d’importation unitaire pour alimenter votre base de données dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html).

## Collecter des profils via des applications web

Utilisez Campaign pour créer des formulaires web et collecter et gérer facilement et efficacement les informations de profil. Vous pouvez partager ces formulaires sur votre site web, ce qui permet à vos contacts de fournir facilement leurs informations. Leurs informations sont envoyées à Campaign pour créer leur profil ou mettre à jour leurs informations si elles sont déjà présentes dans la base de données.

![](assets/web-form-page.png)

:[!DNL :arrow_upper_right:] : Découvrez comment créer des formulaires web dans la [documentation du Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/about-web-forms.html).

**Rubriques connexes :**

* [Créer des audiences](audiences.md)
* [Dédupliquer les profils](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/deduplication-merge.html)
* [Enrichir les données de profil](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/enriching-data.html)
