---
product: campaign
title: Suivi d’une campagne
description: Découvrez comment effectuer le suivi dʼune campagne grâce au marketing distribué de Campaign
feature: Distributed Marketing
version: Campaign v8, Campaign Classic v7
role: User
exl-id: 9904c1c6-c233-4aa2-a237-338ebde15661
TQID: https://experienceleague.adobe.com/v-ZkfPAMBCbVOb0FheuwmYILdV4uFjbGu6cv2uoKccc
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: cdc2fbe67fe123c895c8d3d71daffe022ba5c030
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 72%
---
# Suivi d’une campagne{#tracking-a-campaign}



Les opérateurs de l’entité centrale peuvent effectuer un tracking des commandes des opérations proposées dans la liste des kits de campagne.

Ils peuvent ainsi :

* [Filtrer les kits](#filter-packages),
* [Modifier les packages](#edit-packages),
* [Annuler un kit](#cancel-a-package),
* [Réinitialisation dʼun package](#reinitializing-a-package).

## Filtrer les kits {#filter-packages}

Dans l’onglet **[!UICONTROL Campagnes]**, vous pouvez afficher la liste des **[!UICONTROL Kits de campagne]** qui regroupe toutes les campagnes de marketing distribué existantes. Vous pouvez filtrer cette liste de sorte qu’elle n’affiche que les campagnes qui sont déjà publiées, en retard, en attente de validation, etc. Pour ce faire, cliquez sur les liens dans la section supérieure de cette vue ou utilisez le lien **[!UICONTROL Filtrer la liste]** et sélectionnez le statut du kit de campagne à afficher.

![Liste des packages de campagne avec le filtre de statut ouvert : en édition, en attente d&#39;approbation, approuvés, rejetés, etc.](assets/mkg_dist_catalog_filter.png)

## Modifier les packages {#edit-packages}

La page des **[!UICONTROL kits de campagne]** permet de visualiser le résumé de chaque kit.

Ce résumé affiche les informations suivantes : le libellé, le type d&#39;opération, le nom de l&#39;opération à partir de laquelle le kit a été créé et le dossier d&#39;enregistrement.

Cliquez sur le nom du kit pour le modifier. Vous pouvez alors visualiser les commandes réalisées par les entités locales et leur statut.

Cette information est proposée aussi dans la vue **[!UICONTROL Commandes d&#39;opérations]** qui liste unitairement toutes les commandes réalisées.

![Liste des commandes de campagne affichant chaque commande avec son entité locale, sa campagne et son statut (Disponible ou Annulé).](assets/mkg_dist_catalog_op_command_details.png)

Les opérateurs et opératrices centraux peuvent modifier la commande. Vous avez le choix entre les deux méthodes suivantes :

1. L’opérateur ou l’opératrice peut cliquer sur le nom de la commande pour l’éditer : il ou elle accède alors aux détails de celle-ci.

   ![Cliquez sur une commande dans la liste des commandes de Campaign pour ouvrir son tableau de bord avec le statut, le package, l&#39;entité locale et les validations.](assets/mkg_dist_catalog_op_command_edit1.png)

   L&#39;onglet **[!UICONTROL Edition > Général]** permet de consulter les informations renseignées par l&#39;entité locale lors de la commande de l&#39;opération.

   ![Onglet Modifier la commande, Général : libellé, entité organisationnelle, opérateur affecté, statut et commentaire de l&#39;entité locale.](assets/mkg_dist_catalog_op_command_edit1a.png)

1. L’opérateur peut cliquer sur le libellé du kit de campagne pour l’éditer : il peut éventuellement modifier certains paramétrages.

   ![Ouverture d&#39;un kit de la liste, puis d&#39;une de ses commandes de campagne, chacune affichant son tableau de bord.](assets/mkg_dist_catalog_op_command_edit2.png)

## Annuler un kit {#cancel-a-package}

À tout moment, l’entité centrale a la possibilité d’annuler un kit de campagne.

Pour cela, cliquez sur le bouton **[!UICONTROL Annuler]** à partir du **[!UICONTROL Tableau de bord]** du kit de campagne.

![Le bouton Annuler le package sur le tableau de bord du package ouvre la boîte de dialogue Action sur le package avec un champ Commentaire.](assets/mkg_dist_cancel_op_from_dashboard.png)

Vous avez la possibilité de motiver cette annulation dans le champ **[!UICONTROL Commentaire]**.

Pour les **opérations locales**, l&#39;annulation d&#39;un kit le supprime de la liste des opérations marketing disponibles.

Pour les **campagnes collaboratives**, l’annulation d’un kit d’opération provoque de nombreuses actions :

1. L&#39;annulation de toutes les commandes relatives à ce kit,

   ![Tableau de bord des packages annulés répertoriant ses commandes de campagne, chacune avec le statut Annulée.](assets/mkg_dist_mutual_op_cancelled.png)

1. L&#39;annulation de l&#39;opération de référence et l&#39;arrêt de tous les traitements actifs (workflows, diffusions),

   ![Annulation du tableau de bord de la campagne de référence avec ses diffusions e-mail et SMS affichées comme Arrêtées.](assets/mkg_dist_mutual_op_cancelled1.png)

1. L&#39;envoi d&#39;une notification aux entités locales concernées.

   ![Annulation de l&#39;e-mail de package informant une entité locale que la campagne a été annulée de manière centralisée.](assets/mkg_dist_mutual_op_cancelled2.png)

Les kits annulés restent accessibles et peuvent être réinitialisés par l’entité centrale (voir ci-dessous) si nécessaire. Ils ne seront proposés aux entités locales qu’une fois approuvés et démarrés. Le processus de réinitialisation d’un package est présenté ci-dessous.

## Réinitialisation dʼun package {#reinitializing-a-package}

Vous pouvez réinitialiser un kit de campagne déjà publié afin de le modifier puis le mettre à nouveau à disposition des entités locales.

1. Pour cela, sélectionnez le kit concerné.
1. Cliquez sur le lien **[!UICONTROL Réinitialiser le kit pour l&#39;utiliser à nouveau]**, puis sur **[!UICONTROL OK]**.

   ![Réinitialisez la boîte de dialogue de confirmation du package : le statut devient En édition, avec le bouton OK.](assets/mkg_dist_mutual_op_reinit.png)

1. Cliquez sur le bouton **[!UICONTROL Enregistrer]** pour valider la réinitialisation du kit.

   ![Tableau de bord du package annulé avec le bouton Enregistrer en surbrillance pour approuver la réinitialisation.](assets/mkg_dist_mutual_op_reinit2.png)

1. Le statut du package passe à **[!UICONTROL En cours d’édition]**. Il peut alors être modifié, approuvé et publié pour être à nouveau proposé dans la liste des kits de campagne.

>[!NOTE]
>
>Vous pouvez également réinitialiser un kit de campagne qui a été annulé.
