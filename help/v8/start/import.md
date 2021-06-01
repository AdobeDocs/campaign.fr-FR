---
product: Adobe Campaign
title: Prise en main des profils
description: Prise en main des profils
feature: Profils
role: Data Engineer
level: Beginner
exl-id: b0f8c057-dd4e-4284-b5a4-157986a1d95a
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 59%

---

# Import de données dans Campaign {#ootb-profiles}

Campaign vous aide à ajouter des contacts à la base de données cloud. Vous pouvez charger un fichier, planifier et automatiser plusieurs mises à jour des contacts, collecter des données sur le Web ou saisir des informations de profil directement dans la table des destinataires.

[!DNL :bulb:] Prise en main d&#39; [](audiences.md)
[!DNL :bulb:] audiencesPrésentation du  [modèle de données de Campaign](../dev/datamodel.md)

## Import de profils dans un workflow

Les imports de profils sont configurés dans des modèles dédiés, exécutés par le biais de workflows via l’activité **Import**. Ils peuvent être répétés automatiquement selon un planning, par exemple pour automatiser l’échange de données entre plusieurs systèmes d’informations. Pour en savoir plus, consultez la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/import-export-workflows.html?lang=fr).

![](assets/import-wf.png)

En savoir plus dans la documentation de Campaign Classic v7 :

[!DNL :arrow_upper_right:] [Prise en main des imports et exports](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/get-started-data-import-export.html?lang=fr)

[!DNL :arrow_upper_right:] [Bonnes pratiques en matière d&#39;import et d&#39;export](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/best-practices/import-export-best-practices.html?lang=fr)

[!DNL :arrow_upper_right:] [Configurer et exécuter un import](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html?lang=fr)

## Exécution d’imports unitaires

Créez et exécutez un traitement d’import de données générique pour charger des contacts dans la base de données cloud.

![](assets/new-import.png)

[!DNL :arrow_upper_right:] Découvrez comment exécuter des tâches d’importation unitaire pour alimenter votre base de données dans la documentation  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=fr).

## Collecte de profils via des applications web

Utilisez Campaign pour créer des formulaires web et collecter et gérer facilement et efficacement les informations de profil. Vous pouvez partager ces formulaires sur votre site web, ce qui permet à vos contacts de fournir facilement leurs informations. Leurs informations sont envoyées à Campaign pour créer leur profil ou mettre à jour leurs informations si elles sont déjà présentes dans la base de données.

![](assets/web-form-page.png)

[!DNL :arrow_upper_right:] Découvrez comment créer des formulaires web dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/about-web-forms.html).

**Rubriques connexes**

* [Création d’audiences](audiences.md)
* [Déduplication des profils](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/deduplication-merge.html?lang=fr)
* [Enrichissement des données de profil](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/enriching-data.html?lang=fr)
