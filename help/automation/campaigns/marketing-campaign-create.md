---
product: campaign
title: Création de campagnes marketing
description: Découvrez comment créer et exécuter des campagnes marketing
feature: Campaigns, Cross Channel Orchestration, Programs
exl-id: 90dd2dad-1380-490e-b958-4a28a7d930ed
source-git-commit: ad286059a9f4b63d7de4fa5130760f36d0976431
workflow-type: tm+mt
source-wordcount: '1318'
ht-degree: 99%

---

# Créer les programmes et les campagnes{#create-programs-and-campaigns}

Les composants d’orchestration de Campaign se trouvent dans l’onglet **[!UICONTROL Campagnes]** : vous y trouverez un aperçu des programmes et campagnes marketing, ainsi que des éléments connexes.

Un programme marketing est constitué de campagnes, elles-mêmes constituées de diffusions, de ressources, etc. Toutes les informations relatives aux diffusions, budgets, validants et documents connexes sont regroupées au sein de la campagne.

![](assets/campaigns-create-from-home.png)

![](assets/do-not-localize/how-to-video.png) [Découvrir les programmes et les campagnes en vidéo](#video)

## Travailler avec des programmes et des plans{#work-with-plan-and-program}

### Créer la hiérarchie des plans et programmes {#create-plan-and-program}

Chaque campagne appartient à un programme qui appartient à son tour à un plan. Tous les plans, programmes et campagnes sont disponibles dans le menu **[!UICONTROL Calendrier des campagnes]** de l’onglet **Campagnes**.

Avant de lancer la création de vos campagnes et diffusions, configurez l’arborescence de vos dossiers pour les plans et programmes marketing.

1. Cliquez sur l&#39;icône **Explorateur** dans la page d&#39;accueil.
1. Cliquez avec le bouton droit de la souris sur le dossier dans lequel vous souhaitez créer le plan.
1. Sélectionnez **Ajouter un dossier > Gestion de campagne > Plan**.

   ![](assets/create-new-plan-folder.png)

1. Renommez le plan.
1. Cliquez avec le bouton droit de la souris sur le plan nouvellement créé et sélectionnez **Propriétés...**.
1. Dans l&#39;onglet **Général**, modifiez le **nom interne** pour éviter les doublons lors des exports de package.

   ![](assets/plan-properties.png)

1. Cliquez sur **Enregistrer**.
1. Cliquez avec le bouton droit de la souris sur le plan nouvellement créé et sélectionnez **Ajouter un dossier &#39;Programme&#39;**.

   ![](assets/program-folder.png)

1. Répétez les étapes décrites ci-dessus pour renommer le nouveau dossier de programmes et modifier le nom interne.


### Configurer un programme {#edit-a-program}

Lorsque vous éditez un programme, utilisez les onglets présentés ci-dessous pour naviguer et le paramétrer.

* L&#39;onglet **Planning** affiche le calendrier du programme sur un mois, une semaine ou une journée selon que vous cliquez sur l&#39;un des onglets dans l&#39;en-tête du calendrier. Vous pouvez créer une campagne, un programme ou une tâche à partir de cette page. [En savoir plus](#campaign-calendar)

* L&#39;onglet **Modifier** vous permet de modifier le programme : son nom, ses dates de début et fin, son budget, ses documents associés, etc.

   ![](assets/new-program-edit-tab.png)

## Utiliser des campagnes{#work-with-campaigns}

### Créer une campagne {#create-a-campaign}

Vous pouvez créer une campagne à partir de la liste des campagnes. Pour afficher cette vue, sélectionnez le menu **[!UICONTROL Campagnes]** dans le tableau de bord **[!UICONTROL Campagnes]**, puis cliquez sur **[!UICONTROL Créer]**.

Le champ **[!UICONTROL Programme]** permet de sélectionner le programme auquel sera rattachée l’opération. Cette information est obligatoire.

![](assets/new-campaign-settings.png)

Vous pouvez également créer les campagnes à partir du calendrier des campagnes ou des programmes. [En savoir plus](#campaign-calendar)

Dans la fenêtre de création de campagne, sélectionnez le modèle de campagne et ajoutez un nom et une description de la campagne. Vous pouvez également spécifier les dates de début et de fin de la campagne.

Cliquez sur **[!UICONTROL OK]** pour créer la campagne. Celle-ci est ajoutée au planning du programme, ainsi qu’à la liste des campagnes.

Vous pouvez ensuite modifier l’opération que vous venez de créer et en définir les paramètres. Pour ouvrir et configurer cette campagne, vous pouvez :

1. Parcourir le calendrier des campagnes, sélectionner la campagne que vous souhaitez afficher, puis cliquer sur le lien **[!UICONTROL Ouvrir]**.
1. Parcourir l’onglet **[!UICONTROL Planning]** du programme, sélectionner la campagne et l’ouvrir.
1. Parcourir la liste des campagnes et cliquer sur le nom de la campagne à modifier.

Toutes ces actions vous permettent d’accéder au tableau de bord de la campagne.

![](assets/campaigns-dashboard-approve.png)

Accédez aux sections suivantes pour apprendre à configurer votre campagne :

* [Ajouter des diffusions](marketing-campaign-deliveries.md)
* [Gérer les ressources et les documents](marketing-campaign-assets.md)
* [Créer l’audience cible](marketing-campaign-target.md)
* [Configurer le processus de validation](marketing-campaign-approval.md)
* [Gérer les stocks et les budgets](providers--stocks-and-budgets.md)


### Modifier les paramètres de la campagne {#campaign-settings}

Les campagnes sont créées à partir de modèles de campagne. Vous pouvez configurer des modèles réutilisables pour lesquels certaines options sont sélectionnées et d’autres paramètres sont déjà enregistrés.

Pour chaque campagne, les fonctionnalités suivantes sont disponibles :

* Documents de référence et ressources : vous pouvez associer des documents à la campagne (brief, compte-rendu, images, etc.). Tous les formats de document sont pris en charge. [En savoir plus](marketing-campaign-deliveries.md#manage-associated-documents).
* Définir les coûts : pour chaque campagne, Adobe Campaign permet de définir les postes de coût et les structures de calcul des coûts qui pourront être utilisés lors de la création de la campagne marketing. Par exemple : coûts d’impression, utilisation d’une agence externe, location de salle, etc. [En savoir plus](providers--stocks-and-budgets.md#defining-cost-categories).
* Définir des objectifs : vous pouvez définir des objectifs quantifiables pour une campagne, tels que le nombre d’abonnés, le chiffre d’affaires, etc. Ces informations sont ensuite utilisées dans les rapports de campagne.
* Gérer les adresses de contrôle et les populations témoin. [En savoir plus](marketing-campaign-deliveries.md#defining-a-control-group).
* Gestion des validations : vous pouvez sélectionner les traitements qui feront l&#39;objet d&#39;une validation et éventuellement sélectionner les opérateurs ou groupes d&#39;opérateurs validants. [En savoir plus](marketing-campaign-approval.md#checking-and-approving-deliveries).

>[!NOTE]
>
>Pour accéder aux paramètres de la campagne et les mettre à jour, cliquez sur le lien **[!UICONTROL Paramètres avancés de la campagne...]** de l&#39;onglet **[!UICONTROL Modifier]**.

### Surveiller une campagne {#monitor-a-campaign}

Pour chaque campagne, les traitements, ressources et diffusions sont regroupés dans le tableau de bord. Cette interface vous permet de gérer et d&#39;orchestrer des actions marketing.

Avec Adobe Campaign, vous pouvez mettre en place des processus collaboratifs pour la réalisation, mais aussi pour la validation des différentes étapes de vos campagnes : validation du budget, de la cible, du contenu, etc. Cette orchestration est présentée dans [cette section](marketing-campaign-approval.md).

![](assets/campaigns-dashboard-approval-tab.png)

>[!NOTE]
>
>Les composants disponibles dans une campagne dépendent de son modèle. Le paramétrage du modèle de campagne est présenté dans [cette section](marketing-campaign-templates.md#campaign-templates).

Une fois la campagne réalisée, utilisez le lien **[!UICONTROL Rapports]** pour accéder aux rapports de l&#39;opération.

![](assets/campaigns-reports-dashboard.png)

## Calendrier des campagnes {#campaign-calendar}

Le calendrier des campagnes affiche tous les programmes, plans, campagnes et diffusions.

Pour modifier un plan, un programme, une campagne ou une diffusion, accédez à son nom dans le calendrier, puis utilisez le lien **[!UICONTROL Ouvrir]**. Il s&#39;affiche alors dans un nouvel onglet, comme dans l&#39;image ci-dessous :

![](assets/campaign-calendar.png)

Vous pouvez filtrer les informations affichées dans le calendrier des campagnes. Pour cela, cliquez sur le lien **[!UICONTROL Filtrer]** et sélectionnez les critères de filtrage.

![](assets/campaign_planning_filter.png)

>[!NOTE]
>
>Lorsque vous filtrez sur une date, toutes les campagnes dont la date de début est postérieure à la date spécifiée et/ou dont la date de fin est antérieure à la date spécifiée sont affichées. Les dates sont sélectionnées à l&#39;aide des calendriers proposés à droite de chaque champ.

Vous pouvez également utiliser le champ **[!UICONTROL Rechercher]** pour filtrer les éléments affichés.

Les icônes associées à chaque élément vous permettent de visualiser son statut : terminé, en cours, en édition, etc.

Pour filtrer les opérations à afficher, cliquez sur le lien **[!UICONTROL Filtrer]** et sélectionnez le statut des opérations à afficher.

![](assets/calendar-filter-options.png)

En parcourant le calendrier, vous pouvez également créer un programme ou une campagne.

![](assets/campaign-create-from-calendar.png)

Lorsque vous créez une opération à partir de l&#39;onglet **[!UICONTROL Planning]** d&#39;un programme, la campagne est automatiquement rattachée au programme concerné. Le champ **[!UICONTROL Programme]** est alors masqué.


## Utiliser l&#39;interface web {#use-the-web-interface-}

Vous pouvez accéder aux écrans de la console Adobe Campaign par l&#39;intermédiaire d&#39;un navigateur Internet pour visualiser l&#39;ensemble des opérations et leurs diffusions, les rapports et les informations relatives aux profils de votre base. Cet accès ne vous permet pas de créer des enregistrements. Vous pouvez cependant consulter et, selon les permissions associées à votre profil d&#39;opérateur, agir sur les données de la base. Ainsi, vous pouvez par exemple valider les contenus et ciblages de vos opérations, relancer ou interrompre une diffusion, etc.

1. Connectez-vous comme vous le faites habituellement à l&#39;aide de l&#39;adresse https://`<your instance>:<port>/view/home`.
1. Utilisez les menus pour accéder aux vues d&#39;ensemble.

   ![](assets/web-access-campaigns.png)

Outre la navigation dans les campagnes et leur affichage, vous pouvez effectuer les tâches suivantes :

* Surveillance de l’activité sur une instance
* Participation aux processus de validation, par exemple, validation ou refus du contenu d’une diffusion
* Exécution d’autres actions rapides, par exemple mis en pause d’un workflow
* Accès à toutes les fonctionnalités de rapport
* Participation aux discussions de forum

Ce tableau résume les actions que vous pouvez effectuer sur les campagnes à partir d’un navigateur :

| Page  | Action |
| --- | --- |
| Liste des campagnes, diffusions, offres, etc. | Suppression d’un élément de liste |
| Campagne | Annulation d’une campagne |
| Diffusion | Valider le contenu et la cible de la diffusion<br/>Envoyer le contenu de la diffusion<br/>Confirmer une diffusion<br/>Mettre en pause et arrêter une diffusion |
| Application web | Créer une application web<br/>Modifier le contenu et les propriétés de l’application<br/>Enregistrer le contenu de l’application en tant que modèle<br/>Publier l’application |
| Offre | Valider le contenu et l’éligibilité de l’offre<br/>Désactiver une offre en ligne |
| Tâche | Terminer une tâche<br/>Annuler une tâche |
| Ressource marketing | Approuver une ressource<br/>Verrouiller et déverrouiller une ressource |
| Package de campagnes | Soumettre un package pour validation<br/>Valider ou refuser un package<br/>Annuler un package |
| Commande de campagne | Créer une commande<br/>Accepter ou refuser une commande |
| Stock | Supprimer des données de stock |
| Simulation d’offres | Démarrer et arrêter une simulation |
| Workflow de ciblage | Démarrer, mettre en pause et arrêter un workflow |
| Rapport | Enregistrer les données actives dans l’historique du rapport |
| Forum | Ajouter une discussion<br/>Répondre à un message dans une discussion<br/>Suivre une discussion et s’en désabonner |

### Gérer les validations

Les validations de la cible ou du contenu d&#39;une diffusion peuvent être réalisées par le biais d&#39;un accès web.

![](assets/web-access-approval.png)

Vous pouvez également utiliser le lien contenu dans les messages de notification. Pour plus d&#39;informations, consultez [cette section](marketing-campaign-approval.md#checking-and-approving-deliveries).


## Tutoriel vidéo {#video}

Cette vidéo explique comment créer un plan marketing, des programmes et des campagnes.

>[!VIDEO](https://video.tv.adobe.com/v/333810?quality=12)
