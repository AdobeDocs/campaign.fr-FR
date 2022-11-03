---
title: Créer un cube dans Adobe Campaign
description: Découvrez comment créer des cubes
feature: Reporting
role: Data Engineer
level: Beginner
source-git-commit: 7fc3e5b9f12ca48ef0921e27844ef9fef71ac06b
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 25%

---


# Créer un cube{#create-a-cube}

## Espace de travail des cubes {#cube-workspace}

Pour accéder aux cubes, accédez à **[!UICONTROL Administration > Paramétrage > Cubes]** à partir de l&#39;explorateur Campaign.

![](assets/cube-node.png)

Avec les cubes, vous pouvez :

* Exporter des données directement dans un rapport, conçu dans la variable **[!UICONTROL Rapports]** de la plateforme Adobe Campaign.

   Pour cela, créez un nouveau rapport et sélectionnez le cube à utiliser.

   ![](assets/create-new-cube.png)

   Les cubes apparaissent comme des modèles à partir desquels sont créés les rapports. Une fois le modèle sélectionné, cliquez sur **[!UICONTROL Créer]** pour configurer et afficher le nouveau rapport.

   Vous pouvez alors adapter les mesures, modifier le mode d&#39;affichage ou configurer le tableau, puis afficher le rapport à partir du bouton central.

   ![](assets/display-cube-table.png)

* Référencer un cube dans la **[!UICONTROL Requête]** d’un rapport afin d’utiliser ses indicateurs, comme dans l’exemple ci-dessous :

   ![](assets/cube-report-query.png)

* Insérez un tableau croisé dynamique basé sur un cube dans n&#39;importe quelle page d&#39;un rapport. Pour cela, référencez le cube à utiliser dans le **[!UICONTROL Données]** du tableau croisé dynamique sur la page concernée.

   ![](assets/cube-in-a-report.png)

   Pour plus dʼinformations, consultez la section [Exploration des données dans un rapport](cube-tables.md#explore-the-data-in-a-report).


>[!CAUTION]
>
>Des autorisations d’administrateur sont nécessaires pour créer des cubes.

## Créer un cube{#cube-create}

Avant de commencer la construction d&#39;un rapport cube, identifiez les dimensions et mesures pertinentes, puis créez-les dans le cube.

Pour créer un cube, les étapes sont les suivantes :

1. Sélectionner la table de travail. [En savoir plus](#select-the-work-table).
1. Définissez des dimensions. [En savoir plus](#define-dimensions).
1. Définissez des mesures. [En savoir plus](#build-indicators).
1. Créez des agrégats (facultatif). [En savoir plus](customize-cubes.md#calculate-and-use-aggregates).

Dans l&#39;exemple ci-dessous, découvrez comment créer rapidement un cube simple dans un rapport afin d&#39;en exporter les mesures.

### Sélection de la table de travail {#select-the-work-table}

Pour créer un cube, procédez comme suit :

1. Cliquez sur le bouton **[!UICONTROL Nouveau]** au-dessus de la liste des cubes.

   ![](assets/create-a-cube.png)

1. Sélectionnez le schéma contenant les éléments que vous souhaitez explorer (également appelé &quot;schéma des faits&quot;). Dans cet exemple, sélectionnez la valeur par défaut **Destinataire** table.
1. Cliquez sur **[!UICONTROL Enregistrer]** pour créer le cube : il est ajouté à la liste des cubes. Vous pouvez maintenant utiliser les onglets pour le configurer.

1. Cliquez sur le bouton **[!UICONTROL Filtrer les données source...]** lien permettant d&#39;appliquer les calculs de ce cube aux données de la base.

   ![](assets/cube-filter-source.png)

### Définition des dimensions {#define-dimensions}

Une fois le cube créé, définissez ses dimensions. Les Dimensions sont les axes d&#39;analyse définis pour chaque cube selon leur schéma des faits associé. Il s’agit des dimensions explorées dans l’analyse, telles que l’heure (année, mois, date), une classification de produits ou de contrats (famille, référence, etc.), un segment de population (par ville, tranche d’âge, statut, etc.).

Pour créer des dimensions, procédez comme suit :

1. Accédez au **[!UICONTROL Dimension]** du cube et cliquez sur le bouton **[!UICONTROL Ajouter]** pour créer une nouvelle dimension.
1. Dans le **[!UICONTROL Champ d&#39;expression]**, cliquez sur le bouton **[!UICONTROL Expression d’édition]** pour sélectionner le champ contenant les données concernées.

   ![](assets/cube-add-dimension.png)

1. Dans cet exemple, nous sélectionnons le destinataire **Age**. Pour ce champ, vous pouvez définir une mise en classe afin de regrouper les âges et faciliter la lecture des informations. Nous vous recommandons d’utiliser la mise en classe lorsque plusieurs valeurs distinctes sont probables.

Pour cela, cochez l&#39;option **[!UICONTROL Activer la mise en classe.]** [En savoir plus](customize-cubes.md#data-binning).

1. Ajouter un **Date** dimension de type . Ici, nous allons afficher les dates de création du profil du destinataire. Pour cela, cliquez sur **[!UICONTROL Ajouter]** et choisissez le champ **[!UICONTROL Date de création]** dans la table des destinataires.
Vous pouvez personnaliser le mode d’affichage des dates. Pour cela, sélectionnez la hiérarchie à utiliser et les niveaux à générer :

![](assets/cube-date-dimension.png)

Dans notre exemple, nous ne voulons afficher que les années, les mois et les jours. Notez que vous ne pouvez pas travailler simultanément avec des semaines et des semestres/mois : ces niveaux ne sont pas compatibles.

1. Créez une autre dimension pour analyser les données par rapport à la ville du destinataire. Pour cela, ajoutez une nouvelle dimension et sélectionnez la ville, sous le noeud **[!UICONTROL Localisation]** du schéma des destinataires.

Vous pouvez activer la mise en classe afin de simplifier la lecture des informations et lier les valeurs à une valeur d&#39;énumération.

Sélectionnez l&#39;énumération dans la liste déroulante.. Notez que cette énumération doit être définie comme **[!UICONTROL Réservé à la mise en classe]**.

![](assets/cube-dimension-with-enum.png)

Seules les valeurs présentes dans l&#39;énumération seront affichées. Toutes les autres seront regroupées sous le libellé défini dans le champ **[!UICONTROL Libellé des autres valeurs]**.

Pour plus d&#39;informations, consultez [cette section](customize-cubes.md#dynamically-manage-bins).

### Construction des indicateurs {#build-indicators}

Une fois les dimensions définies, définissez un mode de calcul pour les valeurs à afficher dans les cellules.

Pour cela, créez les indicateurs dans la **[!UICONTROL Mesures]** . Créez autant de mesures que de colonnes à afficher dans les rapports basés sur ce cube.

Pour créer des indicateurs, procédez comme suit :

1. Accédez au **[!UICONTROL Mesures]** et cliquez sur l’onglet **[!UICONTROL Ajouter]** bouton .
1. Sélectionnez le type de mesure et la formule à appliquer. Dans cet exemple, nous comptons le nombre de femmes parmi les destinataires. Notre mesure se base sur le schéma des faits et utilise l&#39;opérateur **[!UICONTROL Comptage]**.

   ![](assets/cube-new-measure.png)

   Utilisez la variable **[!UICONTROL Filtrer les données de la mesure...]** pour sélectionner uniquement les femmes. [En savoir plus](customize-cubes.md#define-measures).

   ![](assets/cube-filter-measure-data.png)

1. Saisissez le libellé de la mesure et enregistrez-la.

   ![](assets/cube-save-measure.png)

1. Enregistrez le cube.


Vous pouvez maintenant créer un rapport basé sur ce cube. [En savoir plus](cube-tables.md).