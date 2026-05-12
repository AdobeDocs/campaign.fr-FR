---
title: Prise en main des rapports d’analyse d’Adobe Campaign
description: Découvrez comment créer des cubes.
feature: Reporting
role: Developer
level: Beginner
exl-id: f57f3074-981f-4bcf-9274-7908cd00a4a2
TQID: https://experienceleague.adobe.com/rWE0PPnY4uRgpGy9a-cucZFSGnRyaI9IwwjJFmvYY9s
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 529
ht-degree: 80%

---

# Prise en main des rapports d’analyse de Campaign {#gs-cube}

Adobe Campaign comprend un outil intuitif d’exploration des données permettant de créer des rapports dynamiques.

Utilisez les fonctionnalités de Marketing Analytics pour analyser et mesurer les données, calculer les statistiques, simplifier et optimiser la création et le calcul de rapports. Grâce à ce module, vous pouvez créer des rapports et des populations cibles, puis les stocker dans des listes à des fins de ciblage ou de segmentation dans Adobe Campaign.

Vous pouvez ainsi d&#39;étendre les capacités d&#39;exploration et d&#39;analyse des données de la base, tout en simplifiant le paramétrage des rapports et tableaux pour les utilisateurs finaux : ils n&#39;ont plus qu&#39;à sélectionner un cube existant, entièrement paramétré, lors de la création de leur rapport ou tableau pour en exploiter les calculs, mesures et statistiques.

Les cubes sont utilisés pour la génération de certains rapports intégrés, notamment les [rapports de diffusion](delivery-reports.md) (suivi des diffusions, clics, ouvertures, etc.).

Une fois créés et paramétrés, les cubes sont utilisés dans les boîtes de requête des rapports et les applications Web. Ils peuvent être utilisés et manipulés dans des tableaux croisés dynamiques.

Le module Marketing Analytics de Campaign vous permet de :

1. Créer des cubes et des indicateurs

   * agrégez et stockez des données dans une table de travail afin de pré-calculer des indicateurs, selon les besoins de lʼutilisateur,
   * réduisez le volume des données impliquées dans les différents calculs utilisés dans les rapports et dans les requêtes, afin dʼoptimiser grandement les temps de calcul des indicateurs.
   * simplifiez lʼaccès aux données, permettez aux utilisateurs de manipuler des données pré-agrégées ou non, selon différentes dimensions.

   Pour plus dʼinformations à ce sujet, consultez la section [Création dʼindicateurs](cube-indicators.md).

1. Créer des tableaux croisés dynamiques et explorer les données

   * explorez les données calculées, les mesures configurées,
   * sélectionnez les données à afficher et leur mode dʼaffichage,
   * personnalisez les mesures et les indicateurs utilisés,
   * proposez des outils dʼanalyse interactive à des utilisateurs sans connaissances techniques.

   Pour plus dʼinformations à ce sujet, consultez la section [Utilisation de cubes pour explorer les données](cube-tables.md).

1. Construire des requêtes à partir des données calculées et agrégées dans un cube.
1. Identifier des populations et les référencer dans des listes.

## Terminologie {#terminology}

Les cubes emploient une terminologie spécifique, consultez les termes utilisés ci-dessous.

* **Cube** : un cube est une représentation dʼinformations multidimensionnelles, il met à disposition des utilisateurs finaux des structures conçues pour des analyses interactives des données.

* **Table/schéma des faits** : la table des faits (ou le schéma des faits) contient les données brutes ou élémentaires sur lesquelles vont être construites les analyses. Il s’agit principalement de tables à gros volume (avec éventuellement des tables liées) et sur lesquelles les calculs peuvent être longs. Par exemple, une table des faits peut être : la table des broadlogs, la table des achats, etc.

* **Dimension** : les dimensions permettent de segmenter les données en groupes. Une fois créées, elles font office dʼaxes dʼanalyse. Dans la plupart des cas, pour une même dimension, plusieurs niveaux seront définis. Par exemple, pour une dimension temporelle, les niveaux seront les mois, jours, heures, minutes, etc. Cet ensemble de niveaux représente la hiérarchie des dimensions et permet d&#39;analyser les données à différents niveaux.

* **Mise en classe** : pour certains champs, vous pouvez définir une mise en classe afin de regrouper les valeurs et faciliter la lisibilité des informations. Les mises en classe sʼappliquent à des niveaux. Il est recommandé de définir une mise en classe lorsque les valeurs distinctes peuvent être nombreuses.

* **Mesure** - Les mesures les plus fréquentes sont la somme, la moyenne, le maximum, le minimum, l’écart type, etc. Les mesures peuvent être calculées : par exemple, le taux d&#39;acceptation d&#39;une offre est le ratio du nombre de fois où elle a été présentée par rapport au nombre de fois où elle a été acceptée.
