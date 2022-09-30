---
audience: end-user
user-guide-title: Campaign v8
description: Documentation Campaign v8
breadcrumb-title: Présentation de Campaign
title: Documentation Campaign v8
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 98%

---


# Documentation Adobe Campaign v8 {#campaign-v8}

+ [Documentation Campaign v8](campaign-home.md)
+ Nouveautés{#new}
   + [Fonctionnalités principales](start/whats-new.md)
   + [Notes de mise à jour](start/release-notes.md)
   + [Barrières de sécurité](start/ac-guardrails.md)
   + [Problèmes connus](start/known-issues.md)
   + [Classic v7 à v8](start/v7-to-v8.md)
+ Démarrage {#start}
   + [Prise en main](start/get-started.md)
   + [Composants et processus](start/ac-components.md)
   + Interface utilisateur de Campaign {#ac-ui}
      + [Découverte de l&#39;interface de Campaign](start/campaign-ui.md)
      + [Personnalisation de l&#39;interface de Campaign](start/customize-ui.md)
   + [Utilisation des audiences](start/audiences.md)
   + [Gestion des demandes d’accès à des informations personnelles](start/privacy.md)
   + [Importation de données](start/import.md)
   + [Création de campagnes](start/campaigns.md)
   + [Envoi de messages](start/create-message.md)
   + [Gestion des abonnements](start/subscriptions.md)
   + [Suivi et surveillance](start/tracking.md)
   + [Mesures et rapports](start/reporting.md)
   + [FAQ](start/campaign-faq.md)
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
   + [Directives de sécurité](config/security.md)
   + [Conception de formulaires et d&#39;applications web](dev/webapps.md)
   + [Bonnes pratiques relatives aux modèles de données](dev/datamodel-best-practices.md)
+ Déploiement {#deploy}
   + [Matrice de compatibilité](start/compatibility-matrix.md)
   + [Connexion à Campaign](start/connect.md)
   + [Autorisations](start/permissions.md)
   + [Panneau de contrôle](config/self-service.md)
+ Profils et audiences {#profiles-and-audiences}
   + [Prise en main](audiences/gs-audiences.md)
   + [Accès aux profils](audiences/view-profiles.md)
   + Ajout de profils {#add-profiles}
      + [Création manuelle de profils](audiences/create-profiles.md)
      + [Importer des profils depuis un fichier](audiences/import-profiles.md)
      + [Utilisation de profils externes](audiences/external-profiles.md)
      + [Collecte de données de profil dans des formulaires web](audiences/collect-profiles.md)
      + [Utiliser les mappings de ciblage](audiences/target-mappings.md)
   + Création d&#39;audiences {#create-audiences}
      + [Créer une liste de contacts](audiences/create-audiences.md)
      + [Créer et gérer des filtres](audiences/create-filters.md)
   + [Gérer les dossiers et les vues](audiences/folders-and-views.md)
   + [Bonnes pratiques](audiences/audiences-best-practices.md)
+ Envoi de messages{#send}
   + E-mails {#emails}
      + [Concevoir et valider des e-mails](send/email.md)
      + [Envoyer et surveiller des e-mails](send/send.md)
   + [SMS](send/sms.md)
   + [Notifications push](send/push.md)
   + [Messagerie LINE](send/line.md)
   + [Courrier](send/direct-mail.md)
   + [Twitter](send/twitter.md)
   + [Messages transactionnels](send/transactional.md)
   + [Optimisation de l&#39;heure d&#39;envoi](send/predictive.md)
   + Échecs, retours et mises en quarantaine{#failures}
      + [Quarantaines](send/quarantines.md)
      + [Diffusions en échec](send/delivery-failures.md)
+ Interaction en temps réel{#interaction}
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
+ Configuration {#config}
   + [Automatisation à l&#39;aide de workflows](config/workflows.md)
   + [Paramètres d&#39;e-mail](config/email-settings.md)
   + [Paramètres de messagerie transactionnelle](config/transactional-msg-settings.md)
   + [Intégration des SDK Campaign avec votre application](config/push-config.md)
   + [Comptes externes](config/external-accounts.md)
+ Connexion {#connect}
   + [Connexion à d&#39;autres solutions](connect/integration.md)
   + [Campaign + Adobe Experience Platform](connect/ac-aep.md)
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
+ Ressources de développement {#developer}
   + [Modèle de données Campaign](dev/datamodel.md)
   + Schémas et formulaires {#shemas-forms}
      + [Utilisation des schémas](dev/schemas.md)
      + [Création de schémas](dev/create-schema.md)
      + [Extension de schémas](dev/extend-schema.md)
      + [Filtrage des schémas](dev/filter-schema.md)
      + [Structure d&#39;un schéma](dev/schema-structure.md)
      + [Mapping de la base de données](dev/database-mapping.md)
      + [Limitation de l&#39;affichage des PI](dev/restrict-pi-view.md)
      + [Utilisation d’une table des destinataires personnalisée](dev/custom-recipient.md)
      + [Mise à jour de la base de données](dev/update-database-structure.md)
      + [Formulaires de saisie](dev/forms.md)
   + [API Campaign](dev/api.md)
+ [Panneau de contrôle Campaign](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=fr)
+ [Guide d’automatisation de Campaign](https://experienceleague.adobe.com/docs/campaign/automation/home.html?lang=fr)
