---
audience: end-user
user-guide-title: Campaign v8
title: Documentation Adobe Campaign v8
description: Documentation Campaign v8
breadcrumb-title: Présentation de Campaign
source-git-commit: 4f3e6227193fc607a968f9170484017e551fa560
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 97%

---


# Documentation Adobe Campaign v8 {#campaign-v8}

+ [Documentation Campaign v8](campaign-home.md)
+ Versions et dernières mises à jour {#releases}
   + [Notes de mise à jour anticipées](start/e-release-notes.md)
   + [Notes de mise à jour](start/release-notes.md)
   + Notes de mise à jour précédentes {#previous-rn}
      + [2022](start/release-notes-2022.md)
      + [2021](start/release-notes-2021.md)
   + [Mécanismes de sécurisation](start/ac-guardrails.md)
   + [Problèmes connus](start/known-issues.md)
   + [Matrice de compatibilité](start/compatibility-matrix.md)
+ Prise en main {#new}
   + [Prise en main d’Adobe Campaign ](start/get-started.md)
   + [Fonctionnalités principales](start/whats-new.md)
   + [Composants et processus](start/ac-components.md)
   + [Se connecter à Campaign](start/connect.md)
   + [Interface Campaign](start/campaign-ui.md)
   + [De Classic v7 à v8](start/v7-to-v8.md)
   + [Questions fréquentes](start/campaign-faq.md)
+ Campaign Management {#campaigns}
   + [Prise en main des campagnes](start/campaigns.md)
   + [Orchestration des campagnes >](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/set-up-campaigns.html?lang=fr)
   + Envoyer des messages{#send}
      + [Prise en main des messages](start/create-message.md)
      + [Utiliser des modèles de diffusion](send/create-templates.md)
      + E-mails {#emails}
         + [Concevoir et valider des e-mails](send/email.md)
         + [Lien vers la page miroir](send/mirror-page.md)
         + [Définition de paramètres d’email supplémentaires](send/email-parameters.md)
         + [Envoyer et surveiller des e-mails](send/send.md)
      + [SMS](send/sms.md)
      + Notifications push {#push}
         + [Création et envoi de notifications push](send/push.md)
         + [Configuration du canal de notification push](send/push-settings.md)
         + [Configuration des notifications push avec la collecte de données](send/push-data-collection.md)
      + [Messagerie LINE](send/line.md)
      + [Courrier](send/direct-mail.md)
      + [Twitter](send/twitter.md)
      + Messages transactionnels {#real-time}
         + [Prise en main des messages transactionnels](send/transactional.md)
         + [Créer et publier votre modèle](send/transactional-template.md)
         + Gestion des événements {#event}
         + [Collecter et traiter les événements](send/event-processing.md)
         + [Comprendre la description des événements](send/event-description.md)
         + [Envoyer et surveiller des messages](send/delivery-execution.md)
      + Échecs, retours et mises en quarantaine{#failures}
         + [Quarantaines](send/quarantines.md)
         + [Diffusions en échec](send/delivery-failures.md)
      + [Optimisation de l’heure d&#39;envoi](send/predictive.md)
      + [Gérer les abonnements](start/subscriptions.md)
      + Personnaliser le contenu {#personalize}
         + [Prise en main de la personnalisation](send/personalize.md)
         + [Données de personnalisation](send/personalization-data.md)
         + [Ajouter des champs de personnalisation,](send/personalization-fields.md)
         + [Utiliser les blocs de personnalisation](send/personalization-blocks.md)
         + [Créer des conditions](send/conditions.md)
      + Valider votre diffusion {#validate}
         + [Prévisualiser et créer des BAT](send/preview-and-proof.md)
         + [Analyse des diffusions](send/delivery-analysis.md)
      + [Configuration et envoi de la diffusion](send/configure-and-send.md)
+ Gestion des profils et de l’audience {#audience}
   + [Prise en main des profils et des audiences](audiences/gs-audiences.md)
   + [Utiliser les audiences](start/audiences.md)
   + [Accès aux profils](audiences/view-profiles.md)
   + Ajout de profils {#add-profiles}
      + [Création manuelle de profils](audiences/create-profiles.md)
      + [Importer des profils depuis un fichier](audiences/import-profiles.md)
      + [Utilisation de profils externes](audiences/external-profiles.md)
      + [Collecte de données de profil dans des formulaires web](audiences/collect-profiles.md)
      + [Utiliser les mappings de ciblage](audiences/target-mappings.md)
      + [Créer des profils de test](audiences/test-profiles.md)
   + Création d&#39;audiences {#create-audiences}
      + [Créer une liste de contacts](audiences/create-audiences.md)
      + [Créer et gérer des filtres](audiences/create-filters.md)
   + [Partager les audiences avec les solutions Adobe](start/shared-audiences.md)
   + [Bonnes pratiques](audiences/audiences-best-practices.md)
+ Gestion de contenu {#content}
   + [Concevoir des formulaires et des applications web](dev/webapps.md)
+ Gestion de la confidentialité et de la sécurité {#privacy}
   + [Gérer les demandes d’accès à des informations personnelles](start/privacy.md)
   + [Directives de sécurité](config/security.md)
+ Gestion des décisions {#offers}
   + [Prise en main des interactions en temps réel](interaction/interaction.md)
   + [Environnements et architecture](interaction/interaction-architecture.md)
   + [Bonnes pratiques](interaction/interaction-best-practices.md)
   + Définition des paramètres{#interaction-settings}
      + [Création d&#39;opérateurs](interaction/interaction-operators.md)
      + [Création d&#39;environnements](interaction/interaction-env.md)
      + [Création de filtres prédéfinis](interaction/interaction-predefined-filters.md)
      + [Création d&#39;emplacements](interaction/interaction-offer-spaces.md)
   + [Création d&#39;un catalogue d&#39;offres](interaction/interaction-offer-catalog.md)
   + [Création d&#39;une offre](interaction/interaction-offer.md)
   + [Envoi d&#39;une offre    (sortante)](interaction/interaction-send-offers.md)
   + Présentation dʼune offre (entrante){#inbound}
      + [Contexte](interaction/interaction-present-offers.md)
      + [Appel dʼune offre dans une page web](interaction/interaction-integration.md)
      + [Gestion des interactions anonymes](interaction/anonymous-interactions.md)
   + [Rapports et historique](interaction/interaction-tracking.md)
   + [Cas pratiques](interaction/interaction-use-cases.md)
+ Rapports et analyses {#analytics}
   + [Suivre et surveiller](start/tracking.md)
   + Utiliser des rapports{#reports}
      + [Commencer avec les rapports](reporting/gs-reporting.md)
      + Créer des cubes{#cubes}
         + [Comencer avec les cubes](reporting/gs-cubes.md)
         + [Créer un cube](reporting/cube-indicators.md)
         + [Utiliser des cubes pour créer des rapports](reporting/cube-tables.md)
         + [Personnaliser vos cubes](reporting/customize-cubes.md)
      + Rapports intégrés{#ac-reports}
         + [Liste des rapports intégrés](reporting/built-in-reports.md)
         + [Rapports globaux](reporting/global-reports.md)
         + [Rapports de diffusion](reporting/delivery-reports.md)
         + [Calcul des mesures intégrées](reporting/metrics-calculation.md)
      + [Rapports personnalisés](reporting/custom-reports.md)
+ Data Management {#data}
   + [Prise en main des workflows](config/workflows.md)
   + [Importer des données](start/import.md)
   + [Documentation des workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=fr)
+ Intégrations {#connect}
   + [Connecter des campagnes à d’autres solutions](connect/integration.md)
   + [Campaign + Experience Platform](connect/ac-aep.md)
   + [Campaign + Journey Optimizer](connect/ac-ajo.md)
   + [Campaign + Analytics](connect/ac-aa.md)
   + [Campaign + Experience Manager](connect/ac-aem.md)
   + [Campaign + Target](connect/ac-at.md)
   + [Campaign + triggers Experience Cloud](connect/ac-triggers.md)
   + [Campaign + Twitter](connect/ac-tw.md)
   + [Campaign + base de données externe](connect/fda.md)
   + Campaign + votre CRM   {#ac-crm}
      + [Prise en main des connecteurs CRM](connect/crm.md)
      + [Utilisation de Campaign et SFDC](connect/ac-sfdc.md)
      + [Utilisation de Campaign et Microsoft Dynamics](connect/ac-ms-dyn.md)
      + [Synchroniser les données](connect/crm-data-sync.md)
+ Administration {#admin}
   + Utilisateurs et autorisations {#permissions}
      + [Prise en main des autorisations](start/gs-permissions.md)
      + [Gérer les autorisations utilisateur](start/manage-permissions.md)
      + [Ajouter des autorisations aux dossiers](start/folder-permissions.md)
   + [Panneau de contrôle](config/self-service.md)
+ Architecture et configuration {#config}
   + Architecture {#architecture}
      + [Principes généraux](architecture/general-architecture.md)
      + [Architecture](architecture/architecture.md)
      + Déploiement de FDA Snowflake {#fda}
         + [Qu’est-ce que FDA-Snowflake ?](architecture/fda-deployment.md)
      + Déploiement d’Entreprise (FFDA) {#ffda}
         + [Qu’est-ce que Campaign FFDA ?](architecture/enterprise-deployment.md)
         + Caractéristiques {#ffda-characteristics}
            + [Gestion des clés et unicité](architecture/keys.md)
            + [Nouvelles API](architecture/new-apis.md)
            + [Mécanisme d&#39;évaluation des API](architecture/staging.md)
            + [Mécanisme de réplication](architecture/replication.md)
   + Implémentation {#implement}
      + [Étapes d&#39;implémentation](start/implement.md)
      + [Personnaliser votre instance](dev/customize.md)
      + [Bonnes pratiques relatives aux modèles de données](dev/datamodel-best-practices.md)
   + Paramètres et configuration {#configuration}
      + [Paramètres de l’interface utilisateur](config/ui-settings.md)
      + [Gérer les dossiers et les vues](audiences/folders-and-views.md)
      + [Paramètres d’e-mail](config/email-settings.md)
      + [Paramètres de messagerie transactionnelle](config/transactional-msg-settings.md)
      + [Intégrer les SDK Campaign à votre application - PAGE OBSOLÈTE](config/push-config.md)
      + [Comptes externes](config/external-accounts.md)
+ Ressources de développement {#developer}
   + [Modèle de données Campaign](dev/datamodel.md)
   + Schémas et formulaires {#shemas-forms}
      + [Utilisation des schémas](dev/schemas.md)
      + [Création de schémas](dev/create-schema.md)
      + [Extension de schémas](dev/extend-schema.md)
      + [Filtrage des schémas](dev/filter-schema.md)
      + [Structure d&#39;un schéma](dev/schema-structure.md)
      + [Mapping de la base de données](dev/database-mapping.md)
      + [Limiter l’affichage des PI](dev/restrict-pi-view.md)
      + [Utilisation d’une table des destinataires personnalisée](dev/custom-recipient.md)
      + [Mise à jour de la base de données](dev/update-database-structure.md)
      + [Formulaires de saisie](dev/forms.md)
   + [API Campaign](dev/api.md)
+ [Panneau de contrôle de Campaign >](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=fr)
+ [Guide d’automatisation de Campaign >](https://experienceleague.adobe.com/docs/campaign/automation/home.html?lang=fr)
