---
title: Prise en main des profils
description: Prise en main des profils
feature: Profiles, Data Management
role: User
level: Beginner
exl-id: b0f8c057-dd4e-4284-b5a4-157986a1d95a
source-git-commit: e0ec2940db3120dc8fbfd17dd2f5083bbf31232c
workflow-type: ht
source-wordcount: '228'
ht-degree: 100%

---

# Import de données dans Campaign {#ootb-profiles}

Campaign vous aide à ajouter des contacts à la base de données cloud. Vous pouvez charger un fichier, planifier et automatiser plusieurs mises à jour des contacts, collecter des données sur le Web ou saisir des informations de profil directement dans la table des destinataires.

![](../assets/do-not-localize/glass.png) Prise en main des [audiences](audiences.md)

![](../assets/do-not-localize/glass.png) Présentation du [modèle de données Campaign](../dev/datamodel.md)

## Import de profils dans un workflow

Les imports de profils sont configurés dans des modèles dédiés, exécutés par le biais de workflows via l&#39;activité **Import**. Ils peuvent être répétés automatiquement selon un planning, par exemple pour automatiser l&#39;échange de données entre plusieurs systèmes d&#39;informations. En savoir plus dans [cette section](../../automation/workflow/recurring-import-workflow.md).

![](assets/import-wf.png)


## Exécution d&#39;imports unitaires

Créez et exécutez un traitement d&#39;import de données générique pour charger des contacts dans la base de données cloud.

![](assets/new-import.png)

![](../assets/do-not-localize/book.png) Découvrez comment exécuter des traitements d’imports unitaires pour alimenter votre base de données en consultant la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=fr){target="_blank"}.

## Collecte de profils via des applications web

Utilisez Campaign pour créer des formulaires web, et collecter et gérer facilement et efficacement les informations de profil. Vous pouvez partager ces formulaires sur votre site web, ce qui permet à vos contacts de fournir facilement leurs informations. Leurs informations sont envoyées à Campaign pour créer leur profil ou mettre à jour leurs informations si elles sont déjà présentes dans la base de données.

![](assets/web-form-page.png)

![](../assets/do-not-localize/book.png) Découvrez comment créer des formulaires web dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/about-web-forms.html?lang=fr){target="_blank"}.

**Rubriques connexes**

* [Création d&#39;audiences](audiences.md)
* [Dédupliquer les profils](../../automation/workflow/deduplication-merge.md)
* [Enrichir les données de profil](../../automation/workflow/enrich-data.md)
