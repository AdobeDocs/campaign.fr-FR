---
product: Adobe Campaign
title: Gestion et automatisation des processus avec les workflows Adobe Campaign
description: Prise en main des workflows
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
source-git-commit: 41ea85bc3c616ed7cdd0718ff3368aab971a5352
workflow-type: tm+mt
source-wordcount: '1189'
ht-degree: 35%

---

# Gestion et automatisation des processus

Configurez Campaign afin de tirer parti de ses puissantes fonctionnalités d’automatisation des campagnes marketing.

Ce que vous pouvez configurer :

* Workflows
* Opérations récurrentes
* Cycle de validation de bout en bout
* Alertes
* Envoi automatique de rapports
* Événements déclenchés

## Conception et utilisation de workflows{#gs-ac-wf}

Utilisez les workflows d’Adobe Campaign pour améliorer la vitesse et l’échelle relatives à chaque aspect de vos campagnes marketing, de la création de segments à la préparation des messages, en passant par leur diffusion.

Découvrez comment concevoir des workflows dans ces [cas pratiques de bout en bout](#end-to-end-uc).

Pour en savoir plus sur l’interface utilisateur et l’exécution des workflows, consultez la documentation de Campaign Classic v7 :

[!DNL :arrow_upper_right:]  [Prise en main des workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=fr#automating-with-workflows)
* Activités de workflow:
   * [Activités de ciblage](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html?lang=fr) : Requête, Lecture de Liste, Enrichissement, Union, etc.
   * [Activités](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/about-flow-control-activities.html?lang=fr) de contrôle de flux : Planificateur, branchement, alerte, signal externe, etc.
   * [Activités d&#39;action](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html?lang=fr) : Diffusions cross-canal, code JavaScript, activités CRM, Mise à jour d’agrégat, etc.
   * [Activités événementielles](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html) : Transfert de fichiers, téléchargement Web, etc.
      [!DNL :arrow_upper_right:]  [Création d’une audience dans un workflow de campagne marketing](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=fr#building-the-main-target-in-a-workflow)

      [!DNL :arrow_upper_right:]  [Bonnes pratiques relatives aux workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/workflow-best-practices.html?lang=fr)
      [!DNL :arrow_upper_right:] [Workflows techniques natifs](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html?lang=fr)
      [!DNL :arrow_upper_right:] [Surveillance d’exécution des workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html?lang=fr)


## Configuration de campagnes récurrentes

Concevez un workflow récurrent et créez une instance de diffusion à chaque exécution du workflow. Par exemple, si votre workflow est conçu pour s’exécuter une fois par semaine, 52 diffusions seront créées en une année. Cela signifie également que les logs seront séparés par chaque instance de diffusion.

[!DNL :arrow_upper_right:] Découvrez comment créer une campagne récurrente dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=fr#recurring-and-periodic-campaigns).


## Utilisation d’événements Trigger

Utilisez la messagerie transactionnelle de Campaign pour automatiser les messages générés à partir d’événements déclenchés depuis des systèmes d’information. Ces messages transactionnels peuvent notamment être une facture, une confirmation de commande, une confirmation d’expédition, une modification de mot de passe, une notification d’indisponibilité du produit, un relevé de compte ou la création d’un compte sur un site web. Ces messages peuvent être envoyés individuellement ou par lots par email, SMS ou notifications push.

[!DNL :bulb:] Pour en savoir plus sur les fonctionnalités des messages transactionnels, voir  [cette section](../send/transactional.md).

Connectez Adobe Campaign et Adobe Analytics pour récupérer les actions utilisateur et envoyer des messages personnalisés en temps quasi réel.

[!DNL :bulb:] Découvrez comment intégrer Campaign à d&#39;autres solutions dans  [cette section](../start/connect.md)


## Cas d’utilisation de bout en bout de workflow{#end-to-end-uc}

Cette section présente différents cas pratiques utilisant des fonctionnalités de workflows dans Campaign. Ces cas pratiques sont créés dans Adobe Campaign Classic v7 et s’appliquent à Adobe Campaign v8.

### Diffusions {#deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

* [A/B testing](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/a-b-testing/use-case/a-b-testing-use-case.html)

   Découvrez comment comparer deux contenus de diffusion email via un workflow de ciblage. Le message et le texte sont identiques dans les deux diffusions : seule la mise en page change. La population ciblée est divisée en trois : deux groupes de test et la population restante. Une version différente de la diffusion est envoyée à chaque groupe de test.

* [Envoyer un email d&#39;anniversaire](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/sending-a-birthday-email.html)

   Ce cas pratique présente comment planifier l&#39;envoi d&#39;un email récurrent à une liste de destinataires le jour de leur anniversaire.

* [Charger le contenu d&#39;une diffusion](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/loading-delivery-content.html)

   Lorsque le contenu de votre diffusion est disponible dans un fichier HTML se trouvant sur un serveur distant, vous pouvez facilement charger ce contenu dans les diffusions Adobe Campaign.

* [Workflow de diffusion cross-canal](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/cross-channel-delivery-workflow.html)

   Découvrez comment créer un workflow de diffusion cross-canal. L&#39;objectif est de segmenter une audience des destinataires de votre base de données en différents groupes et d&#39;envoyer un email au premier groupe et un SMS à l&#39;autre.

* [Enrichissement des emails avec des champs de date personnalisés](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/deliveries/email-enrichment-with-custom-date-fields.html)

   Découvrez comment envoyer un email avec des champs de données personnalisés aux profils qui célèbrent leur anniversaire ce mois-ci. L&#39;email contiendra un coupon valide une semaine avant et après leur anniversaire.

* [Automatisation de la création, de l’édition et de la publication de contenu](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/content-management/automating-via-workflows.html)

   Découvrez comment automatiser la création et la diffusion d&#39;un bloc de contenu avec le module complémentaire de gestion de contenu de Campaign.


### Contrôle            {#monitoring}

<img src="assets/do-not-localize/icon_monitoring.svg" width="60px">

* [Envoi d’un rapport à une liste](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-a-report-to-a-list.html)

   Découvrez comment générer un rapport mensuel intégré des Indicateurs de tracking au format PDF et l&#39;envoyer à une liste d&#39;opérateurs Campaign.

* [Supervision de vos workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/supervising-workflows.html)

   Découvrez comment créer un workflow qui vous permet de surveiller l&#39;état d&#39;un ensemble de workflows en pause, arrêtés ou en erreur.

* [Envoi d’alertes personnalisées aux opérateurs](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-personalized-alerts-to-operators.html)

   Découvrez comment envoyer une alerte à un opérateur qui contiendra le nom des profils ayant ouvert une newsletter mais n’ayant pas cliqué sur le lien qu’il contient.

### Gestion des données {#management}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

* [Coordination des mises à jour de données](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/coordinating-data-updates.html)

   Découvrez comment vérifier que le processus de mise à jour est terminé avant d’exécuter une autre opération de mise à jour. Pour ce faire, nous allons configurer une variable d’instance et laisser le workflow tester si l’instance est en cours d’exécution afin de décider si elle doit continuer l’exécution du workflow et effectuer la mise à jour.

* [Création d’une liste récapitulative](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/creating-a-summary-list.html)

   Découvrez comment créer un workflow qui, après la collecte de fichiers et plusieurs enrichissements, permet de créer une liste récapitulative. L’exemple est basé sur une liste de contacts qui ont effectué des achats dans un magasin.

* [Enrichissement des données](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/enriching-data.html)

   Découvrez comment envoyer des diffusions personnalisées aux profils ayant participé au dernier jeu-concours en fonction de leur score.

* [Utilisation d’agrégats](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/using-aggregates.html)

   Découvrez comment identifier les derniers destinataires ajoutés à la base de données.

* [Mise à jour de la liste trimestrielle à l’aide d’une requête incrémentale](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/quarterly-list-update.html)

   Découvrez comment utiliser une requête incrémentale pour mettre automatiquement à jour une liste de destinataires.

* [Configuration d’un workflow d’import récurrent](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/recurring-import-workflow.html)

   Découvrez comment concevoir un workflow qui pourra être réutilisé pour importer des profils en provenance d&#39;un CRM dans la base de données Adobe Campaign.

### Ciblage {#designing-queries}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

* [Requête de la table des destinataires](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-recipient-table.html)

   Découvrez comment récupérer les noms et les emails des destinataires dont le domaine d&#39;email est &quot;orange.co.uk&quot; et qui ne vivent pas à Londres.

* [Informations sur la diffusion de requêtes](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-delivery-information.html)

   Découvrez comment définir des requêtes sur les informations de diffusion pour récupérer le comportement du profil.

* [Calculer les agrégats](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/performing-aggregate-computing.html)

   Découvrez comment compter le nombre de profils vivant à Londres, en fonction du genre.

* [Requête avec une relation multiple-à-multiple](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/designing-queries/querying-using-many-to-many-relationship.html)

   Découvrez comment trouver des profils qui n’ont pas été contactés au cours des 7 derniers jours.

* [Appeler une variable d’instance dans une requête](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/javascript-scripts-and-templates.html?lang=en#example)

   Découvrez comment utiliser une variable d’instance pour calculer dynamiquement le pourcentage de partage à appliquer à une population.

