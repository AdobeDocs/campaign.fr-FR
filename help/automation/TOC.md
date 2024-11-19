---
audience: user
user-guide-title: Guide d'automatisation des campagnes
user-guide-description: Guide d'automatisation des campagnes
feature: Overview
source-git-commit: 8ff207246bea1f476b37b1d4f2c79498362e7481
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 100%

---


# Guides d&#39;automatisation des campagnes {#automation}

+ [Guide d&#39;automatisation des campagnes](home.md)
+ Automatisation à l’aide de workflows {#workflows}
   + Prise en main des workflows {#introduction}
      + [À propos des workflows](workflow/about-workflows.md)
      + Types de workflows {#wf-type}
         + [Les workflows de ciblage](workflow/targeting-workflows.md)
         + [Les workflows de campagne](workflow/campaign-workflows.md)
         + [Workflows techniques](workflow/technical-workflows.md)
      + [Créer un workflow](workflow/build-a-workflow.md)
      + [Bonnes pratiques](workflow/workflow-best-practices.md)
      + [Utiliser les données d&#39;un workflow](workflow/use-workflow-data.md)
   + Exécution d’un workflow {#executing-a-workflow}
      + [Démarrer un workflow](workflow/start-a-workflow.md)
      + [Cycle de vie d&#39;un workflow](workflow/workflow-life-cycle.md)
      + [Configurer les validations](workflow/define-approvals.md)
   + Surveillance des workflows {#monitoring-workflows}
      + [Surveillance de l’exécution des workflows](workflow/monitor-workflow-execution.md)
      + [Surveillance des workflows techniques](workflow/monitor-technical-workflows.md)
      + [Carte thermique des workflows](workflow/heatmap.md)
   + Activités de workflow {#wf-activities}
      + [Commencer avec les activités](workflow/activities.md)
      + Activités de ciblage {#targeting-activities}
         + [Liste des activités de ciblage](workflow/targeting-activities.md)
         + [Cellules](workflow/cells.md)
         + [Modifier la source de données](workflow/change-data-source.md)
         + [Changement de dimension](workflow/change-dimension.md)
         + [Connecteur CRM](workflow/crm-connector.md)
         + [Déduplication](workflow/deduplication.md)
         + [Composition de diffusion](workflow/delivery-outline.md)
         + [Modifier le schéma](workflow/edit-schema.md)
         + [Enrichissement](workflow/enrichment.md)
         + [Exclusion](workflow/exclusion.md)
         + [Requête incrémentale](workflow/incremental-query.md)
         + [Intersection](workflow/intersection.md)
         + [Mise à jour de liste](workflow/list-update.md)
         + [Offres par cellule](workflow/offers-by-cell.md)
         + [Moteur d&#39;offres](workflow/offer-engine.md)
         + [Requête](workflow/query.md)
         + [Lecture de liste](workflow/read-list.md)
         + [Partage](workflow/split.md)
         + [Services d&#39;abonnements](workflow/subscription-services.md)
         + [Union](workflow/union.md)
         + [Mise à jour de données](workflow/update-data.md)
      + Activités de contrôle de flux {#flow-control-activities}
         + [Liste des activités d&#39;ordonnancement](workflow/flow-control-activities.md)
         + [Alerte](workflow/alert.md)
         + [Rendez-vous](workflow/and-join.md)
         + [Validation](workflow/approval.md)
         + [Signal externe](workflow/external-signal.md)
         + [Branchement](workflow/fork.md)
         + [Saut (départ et arrivée)](workflow/jump-start-point-and-end-point.md)
         + [Début et Fin](workflow/start-and-end.md)
         + [Planificateur](workflow/scheduler.md)
         + [Sous-workflow](workflow/sub-workflow.md)
         + [Test](workflow/test.md)
         + [Contrainte horaire](workflow/time-constraint.md)
         + [Attente](workflow/wait.md)
      + Activités d&#39;action {#action-activities}
         + [Liste des activités d’action](workflow/action-activities.md)
         + [Gestion de contenu](workflow/content-management.md)
         + [Diffusion au fil de l&#39;eau](workflow/continuous-delivery.md)
         + [Diffusions cross-canal](workflow/cross-channel-deliveries.md)
         + [Extraction (fichier)](workflow/extraction-file.md)
         + [Chargement (fichier)](workflow/data-loading-file.md)
         + [Chargement (SGBD)](workflow/data-loading-rdbms.md)
         + [Diffusion](workflow/delivery.md)
         + [Agir sur une diffusion](workflow/delivery-control.md)
         + [Validation en local](workflow/local-approval.md)
         + [Chargement (SOAP)](workflow/loading-soap.md)
         + [Module nlserver](workflow/nlserver-module.md)
         + [Diffusion récurrente](workflow/recurring-delivery.md)
         + [Code SQL et code JavaScript](workflow/sql-code-and-javascript-code.md)
         + [Gestion des données SQL](workflow/sql-data-management.md)
         + [Mise à jour d&#39;agrégat](workflow/update-aggregate.md)
      + Activités événementielles {#event-activities}
         + [Liste des activités d&#39;événement](workflow/event-activities.md)
         + [Collecteur de fichiers](workflow/file-collector.md)
         + [Envoi de fichier](workflow/file-transfer.md)
         + [Réception d&#39;emails](workflow/inbound-emails.md)
         + [Réception de SMS](workflow/inbound-sms.md)
         + [Téléchargement Web](workflow/web-download.md)
   + Cas pratiques {#use-cases}
      + [À propos des cas pratiques de workflows](workflow/workflow-use-cases.md)
      + Diffusions {#deliveries}
         + [Utilisation de l’activité de validation en local](workflow/local-approval-activity.md)
         + [Envoi d’un email d’anniversaire](workflow/send-a-birthday-email.md)
         + [Chargement du contenu de la diffusion](workflow/load-delivery-content.md)
         + [Workflow de diffusion cross-canal](workflow/cross-channel-delivery-workflow.md)
         + [Enrichissement des emails avec des champs de date personnalisés](workflow/email-enrichment-with-custom-date-fields.md)
      + Surveillance {#monitoring}
         + [Envoi d’un rapport à une liste](workflow/send-a-report-to-a-list.md)
         + [Supervision de vos workflows](workflow/workflow-supervision.md)
         + [Envoi d’alertes personnalisées aux opérateurs](workflow/send-alerts-to-operators.md)
      + Gestion des données {#data-management}
         + [Coordination des mises à jour de données](workflow/coordinate-data-updates.md)
         + [Création d’une liste récapitulative](workflow/create-a-summary-list.md)
         + [Enrichissement des données](workflow/enrich-data.md)
         + [Utilisation d’agrégats](workflow/using-aggregates.md)
         + [Utilisation de la fonctionnalité de fusion de l’activité de déduplication](workflow/deduplication-merge.md)
         + [Configuration d’un workflow d’import récurrent](workflow/recurring-import-workflow.md)
      + Requêtes de conception {#designing-queries}
         + [Mise à jour de la liste trimestrielle à l’aide d’une requête incrémentielle](workflow/quarterly-list-update.md)
      + Requête et filtre {#designing-queries}
         + [Requête de la table des destinataires](workflow/querying-recipient-table.md)
         + [Informations sur la diffusion de requêtes](workflow/query-delivery-info.md)
         + [Calculer les agrégats](workflow/compute-aggregates.md)
         + [Requête avec gestion des regroupements](workflow/query-grouping-management.md)
         + [Requête avec une relation multiple-à-multiple](workflow/query-many-to-many-relationship.md)
         + [Ajout d’un champ calculé de type Énumérations](workflow/adding-enumeration-type-calculated-field.md)
         + [Créer un filtre](workflow/create-a-filter.md)
         + [Filtrage des destinataires dupliqués](workflow/filter-duplicated-recipients.md)
   + Paramètres avancés {#advanced-management}
      + [Propriétés de workflow](workflow/workflow-properties.md)
      + [Paramètres avancés](workflow/advanced-parameters.md)
      + [Scripts et modèles JavaScript](workflow/javascript-scripts-and-templates.md)
      + [Exemples de code JavaScript dans les workflows](workflow/javascript-in-workflows.md)
      + [Accès à une base de données externe](workflow/accessing-an-external-database-fda.md)
      + [Gestion des autorisations](workflow/managing-rights.md)
      + [Modification des images d’activité](workflow/change-activity-images.md)
      + [Gérer les fuseaux horaires](workflow/managing-time-zones.md)
+ Orchestration des campagnes {#campaign-orchestration}
   + [Prise en main des campagnes marketing](campaigns/set-up-campaigns.md)
   + [Créer les programmes et les campagnes](campaigns/marketing-campaign-create.md)
   + [Création et configuration de modèles](campaigns/marketing-campaign-templates.md)
   + [Ajout de diffusions](campaigns/marketing-campaign-deliveries.md)
   + [Sélection de l’audience](campaigns/marketing-campaign-target.md)
   + [Gestion des documents et des ressources](campaigns/marketing-campaign-assets.md)
   + [Configuration et gestion des validations](campaigns/marketing-campaign-approval.md)
   + [Campagnes récurrentes et périodiques](campaigns/recurring-periodic-campaigns.md)
   + [Surveillance de vos campagnes](campaigns/marketing-campaign-monitoring.md)
   + [Prestataires, stocks et budgets](campaigns/providers-stocks-and-budgets.md)
+ Optimisation des campagnes (module complémentaire){#campaign-optimization}
   + [Prise en main des typologies de campagne](campaign-opt/campaign-typologies.md)
   + [Règles de filtrage](campaign-opt/filtering-rules.md)
   + [Règles de contrôle](campaign-opt/control-rules.md)
   + [Règles de pression](campaign-opt/pressure-rules.md)
   + [Règles de cohérence](campaign-opt/consistency-rules.md)
   + [Application de règles](campaign-opt/apply-rules.md)
   + [Simulation de campagnes](campaign-opt/campaign-simulations.md)
+ Marketing Resource Management (module complémentaire){#mrm}
   + [Prise en main de la gestion des ressources marketing](mrm/about-marketing-resource-management.md)
   + [Création et gestion de tâches](mrm/creating-and-managing-tasks.md)
   + [Contrôler les coûts](mrm/controlling-costs.md)
   + [Gérer des ressources marketing](mrm/managing-marketing-resources.md)
   + [Forums de discussion](mrm/discussion-forums.md)
+ Marketing distribué (module complémentaire) {#distributed-marketing}
   + [Prise en main du marketing distribué](distributed-marketing/about-distributed-marketing.md)
   + [Création d’une campagne locale](distributed-marketing/creating-a-local-campaign.md)
   + [Création d’une opération collaborative](distributed-marketing/creating-a-collaborative-campaign.md)
   + [Publication du kit d’opération](distributed-marketing/publishing-the-campaign-package.md)
   + [Accès aux campagnes](distributed-marketing/accessing-campaigns.md)
   + [Suivi d’une campagne](distributed-marketing/tracking-a-campaign.md)
   + [Cas pratiques](distributed-marketing/examples.md)
+ [&lt; Retour à la documentation de Campaign v8](https://experienceleague.adobe.com/fr/docs/campaign/campaign-v8/campaign-home)
