---
title: Prise en main des rapports d’analyse d’Adobe Campaign
description: Découvrez comment créer des cubes.
feature: Reporting
role: Data Engineer
level: Beginner
exl-id: f57f3074-981f-4bcf-9274-7908cd00a4a2
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: ht
source-wordcount: '525'
ht-degree: 100%

---

# Prise en main des rapports d’analyse de Campaign {#gs-cube}

Adobe Campaign comprend un outil intuitif d’exploration des données permettant de créer des rapports dynamiques.

Utilisez les fonctionnalités de Marketing Analytics pour analyser et mesurer les données, calculer les statistiques, simplifier et optimiser la création et le calcul de rapports. Grâce à ce module, vous pouvez créer des rapports et des populations cibles, puis les stocker dans des listes à des fins de ciblage ou de segmentation dans Adobe Campaign.

Vous pouvez étendre les capacités d’exploration et d’analyse des bases de données, tout en simplifiant la configuration des rapports et tableaux pour les utilisateurs finaux : ils n’ont ainsi plus qu’à sélectionner un cube existant, entièrement configuré, lors de la création de leur rapport ou tableau pour en exploiter les calculs, mesures et statistiques.

Les cubes sont utilisés pour la génération de certains rapports intégrés, notamment les [rapports de diffusion](delivery-reports.md) (suivi des diffusions, clics, ouvertures, etc.).

Une fois créés et configurés, les cubes sont utilisés dans les boîtes de requête des rapports et les applications web. Ils peuvent être exploités et manipulés au sein de tableaux croisés dynamiques.

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

* **Dimension** : les dimensions permettent de segmenter les données en groupes. Une fois créées, elles font office dʼaxes dʼanalyse. Dans la plupart des cas, pour une même dimension, plusieurs niveaux seront définis. Par exemple, pour une dimension temporelle, les niveaux seront les mois, jours, heures, minutes, etc. Cet ensemble de niveaux représente la hiérarchie de la dimension et permet dʼanalyser plus ou moins finement les données.

* **Mise en classe** : pour certains champs, vous pouvez définir une mise en classe afin de regrouper les valeurs et faciliter la lisibilité des informations. Les mises en classe sʼappliquent à des niveaux. Il est recommandé de définir une mise en classe lorsque les valeurs distinctes peuvent être nombreuses.

* **Mesure** : les mesures courantes sont la somme, la moyenne, le maximum, le minimum, lʼécart-type, etc. Les mesures peuvent être calculées, par exemple le taux dʼacceptation dʼune offre sera le rapport entre le nombre de fois où une offre a été présentée et le nombre de fois où elle a été acceptée.
