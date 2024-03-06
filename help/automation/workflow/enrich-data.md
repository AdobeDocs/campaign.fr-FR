---
product: campaign
title: Enrichir les données
description: En savoir plus sur l’activité de workflow d’enrichissement
feature: Workflows, Enrichment Activity
role: User
exl-id: 3b3fa15f-b16e-42c8-a2e6-03350aee1903
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 70%

---

# Enrichir les données{#enriching-data}



## À propos de l&#39;enrichissement des données {#about-enriching-data}

Ce cas d’utilisation décrit les utilisations possibles de l’activité **[!UICONTROL Enrichissement]** dans un workflow de ciblage. Pour plus d’informations sur l’utilisation de l’activité **[!UICONTROL Enrichissement]**, voir la section : [Enrichissement](enrichment.md).

Vous trouverez également dans [cette section](email-enrichment-with-custom-date-fields.md) un cas pratique montrant comment enrichir une diffusion d’email avec des dates personnalisées.

Les contacts de la base marketing reçoivent une invitation à participer à un concours via une application web. Les résultats du concours sont récupérés dans la **[!UICONTROL Résultats de la compétition]** table. Cette table est liée à la table des contacts (**[!UICONTROL Destinataires]**). La variable **[!UICONTROL Résultats de la compétition]** Le tableau contient les champs suivants :

* Nom du jeu (@game)
* Numéro de l&#39;essai (@trial)
* Score (@score)

![](assets/uc1_enrich_1.png)

Un même contact présent dans la table des **[!UICONTROL Destinataires]** peut être associé à plusieurs lignes dans la table **[!UICONTROL Résultats jeux]**. Le lien entre les deux tables est donc de type 1-n. Voici un exemple des logs de résultats pour un destinataire :

![](assets/uc1_enrich_2.png)

L&#39;objectif de ce cas d&#39;utilisation est d&#39;envoyer des diffusions personnalisées aux participants du dernier jeu concours en fonction du meilleur score qu&#39;ils ont obtenu au cours de leurs différents essais. Le participant qui a obtenu le meilleur score se voit offrir le 1er prix, celui qui a obtenu le second score reçoit un lot de consolation, et tous les autres reçoivent un message leur proposant de retenter leur chance lors du prochain jeu.

Pour réaliser ce cas d&#39;utilisation, nous avons créé le workflow de ciblage suivant :

![](assets/uc1_enrich_3.png)

Les étapes principales de création du workflow sont les suivantes :

1. Deux activités de type **[!UICONTROL Requête]** et une **[!UICONTROL Intersection]** sont ajoutées afin de cibler les nouveaux abonnés qui ont participé au dernier jeu concours.
1. L’activité **[!UICONTROL Enrichissement]** permet d’ajouter des données stockées dans le tableau **[!UICONTROL Résultats jeux]**. Le champ **[!UICONTROL Score]** sur lequel la personnalisation de la diffusion sera effectuée est ajouté au tableau de travail du workflow.
1. L’activité de type **[!UICONTROL Partage]**, permet de créer des sous-ensembles de destinataires selon le score qu’ils ont obtenu.
1. Pour chacun des sous-ensembles, une activité de **[!UICONTROL Diffusion]** est ajoutée.

## Étape 1 : Ciblage {#step-1--targeting}

La première requête permet de cibler les destinataires qui ont été ajoutés dans la base de données au cours des six derniers mois.

![](assets/uc1_enrich_4.png)

La seconde requête permet de cibler les destinataires ayant participé au dernier jeu.

![](assets/uc1_enrich_5.png)

Une activité de type **[!UICONTROL Intersection]** est ensuite ajoutée pour cibler les destinataires qui ont été ajoutés dans la base de données au cours des six derniers mois et qui ont participé au dernier jeu.

## Etape 2 : Enrichissement {#step-2--enrichment}

Dans cet exemple, vous allez découvrir comment personnaliser les diffusions en fonction du champ **[!UICONTROL Score]**, stocké dans le tableau **[!UICONTROL Résultats jeux]**. Ce tableau a une relation de type 1-n avec la tableau des destinataires. L’activité **[!UICONTROL Enrichissement]** permet d’ajouter au tableau de travail du workflow des données provenant d’un tableau associé à la dimension de filtrage.

1. Dans l’écran d’édition de l’activité d’enrichissement, sélectionnez **[!UICONTROL Ajouter des données]**, puis **[!UICONTROL Données liées]** à la dimension de filtrage, et cliquez sur **[!UICONTROL Suivant]**.

   ![](assets/uc1_enrich_6.png)

1. Choisissez ensuite l&#39;option **[!UICONTROL Données liées à la dimension de filtrage]**, sélectionnez la table **[!UICONTROL Résultats jeux]**, et cliquez sur **[!UICONTROL Suivant]**.

   ![](assets/uc1_enrich_7.png)

1. Saisissez un identifiant et un libellé, puis sélectionnez la variable **[!UICONTROL Limiter le nombre de lignes]** dans le **[!UICONTROL Données collectées]** champ . Dans le **[!UICONTROL Lignes à récupérer]** , sélectionnez &quot;1&quot; comme valeur. Pour chaque destinataire, l&#39;activité d&#39;enrichissement ajoutera une seule ligne de la **[!UICONTROL Résultats de la compétition]** à la table de travail du workflow. Cliquez sur **[!UICONTROL Suivant]**.

   ![](assets/uc1_enrich_8.png)

1. Dans cet exemple, nous souhaitons récupérer le meilleur score du destinataire, mais seulement pour le dernier jeu. Pour ce faire, ajoutez un filtre au **[!UICONTROL Nom du jeu]** pour exclure toutes les lignes relatives aux jeux précédents. Cliquez sur **[!UICONTROL Suivant]**.

   ![](assets/uc1_enrich_9.png)

1. Accédez au **[!UICONTROL Tri]** et cliquez sur le bouton **[!UICONTROL Ajouter]** , sélectionnez **[!UICONTROL Score]** et cochez la case dans le champ **[!UICONTROL descendant]** pour trier les éléments de la variable **[!UICONTROL Score]** dans l’ordre décroissant. Pour chaque destinataire, l&#39;activité d&#39;enrichissement ajoute une ligne correspondant au meilleur score obtenu lors du dernier jeu. Cliquez sur **[!UICONTROL Suivant]**.

   ![](assets/uc1_enrich_10.png)

1. Dans le **[!UICONTROL Données à ajouter]** , double-cliquez sur le **[!UICONTROL Score]** champ . Pour chaque destinataire, l&#39;activité d&#39;enrichissement ajoutera uniquement la **[!UICONTROL Score]** champ . Cliquez sur **[!UICONTROL Terminer]**.

   ![](assets/uc1_enrich_11.png)

Cliquez, avec le bouton droit de la souris sur la transition entrante de l’activité d’enrichissement, et sélectionnez **[!UICONTROL Afficher la cible]**. La table de travail contient les données suivantes :

![](assets/uc1_enrich_13.png)

Le schéma associé est le suivant :

![](assets/uc1_enrich_15.png)

Renouvelez cette opération sur la transition sortante de l’activité d’enrichissement. Vous pouvez constater que les données relatives au score des destinataires ont été ajoutées. Pour chaque destinataire, le score le plus élevé a bien été récupéré.

![](assets/uc1_enrich_12.png)

Le schéma correspondant a également été enrichi.

![](assets/uc1_enrich_14.png)

## Etape 3 : Partage et diffusions {#step-3--split-and-delivery}

Afin de répartir les destinataires en fonction de leur score, une activité de **[!UICONTROL Partage]** est ajoutée à la suite de l&#39;enrichissement.

![](assets/uc1_enrich_18.png)

1. Un premier sous-ensemble (**Gagnant**), a été défini pour inclure le destinataire ayant obtenu le meilleur score. Pour cela, définissez une limitation du nombre d&#39;enregistrements, appliquez un tri descendant sur le score, et limitez le nombre d&#39;enregistrements à 1.

   ![](assets/uc1_enrich_16.png)

1. Le second sous-ensemble (**Second**), inclut le destinataire ayant obtenu le second meilleur score. Le paramétrage est le même que pour le premier sous-ensemble.

   ![](assets/uc1_enrich_17.png)

1. Le troisième (**perdants**) contient tous les autres destinataires. Accédez au **[!UICONTROL Général]** et vérifiez les **[!UICONTROL Générer le complémentaire]** pour cibler tous les destinataires qui n’ont pas obtenu les deux meilleurs scores.

   ![](assets/uc1_enrich_19.png)

1. Pour chaque sous-ensemble, ajoutez une activité de type **[!UICONTROL Diffusion]**. Utilisez un modèle de diffusion différent pour chaque sous-ensemble.

   ![](assets/uc1_enrich_20.png)
