---
title: Notes de mise à jour de Campaign v8 (console) 2025
description: Liste des fonctionnalités et améliorations des versions 2025 de Campaign v8
feature: Release Notes
exl-id: 3f91d83e-594e-49ee-a898-606e3de00bf3
source-git-commit: 981fa2029528cac5806da7c39aec3a2e6de0bf56
workflow-type: tm+mt
source-wordcount: '3477'
ht-degree: 33%

---

# Notes de mise à jour 2025 {#2025-rn}

Cette page répertorie les nouvelles fonctionnalités, les améliorations et les correctifs des **versions 2025 de Campaign v8**. Pour connaître la version la plus récente, consultez [cette page](release-notes.md).

Pour toute nouvelle implémentation ou mise à niveau vers un environnement existant, installez [la dernière version](release-notes.md).

>[!BEGINSHADEBOX]

**Dans cette page**

* [Version 8.8.2](#release-8-8-2)
* [Version 8.6.5](#release-8-6-5)
* [Version 8.6.4](#release-8-6-4)
* [Version 8.7.4](#release-8-7-4)
* [Version 8.7.3](#release-8-7-3)


>[!ENDSHADEBOX]

## Version 8.8.2 {#release-8-8-2}

_9 octobre 2025_

>[!AVAILABILITY]
>
>Cette version est en **disponibilité limitée** (LA).

### Nouvelles fonctionnalités {#features-8-8-2}

Le **nouveau connecteur d’envoi de SMS** est désormais disponible pour les [déploiements Campaign FFDA](../architecture/enterprise-deployment.md). Consultez la [documentation détaillée](../send/sms/sms.md).

Cette version comprend également un ensemble de fonctionnalités disponibles dans l’interface utilisateur web de Campaign :

* [Enrichissement du profil dans les messages transactionnels](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html){target="_blank"}
* [Fonctionnalités multilingues pour les messages transactionnels, les notifications push et les SMS](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html){target="_blank"}

Reportez-vous aux notes de mise à jour de l’interface utilisateur web de Campaign [&#128279;](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=fr){target="_blank"}

### Correctifs {#fixes-8-8-2}

<!--
* Fixed an issue which prevented dynamic reporting from being available for transactional messages.
-->
* Correction d’un problème qui entraînait l’échec du workflow de nettoyage de la base de données. (NEO-87949)
* Correction d&#39;un problème dans le marketing distribué en raison duquel les données de tracking n&#39;étaient pas enregistrées pour les diffusions de campagnes collaboratives. (NEO-86836)
<!--
* Issue SMS2.0 with FFDA Continuous Deliveries (NEO-88785)
-->
* Correction d’un problème qui empêchait le bon fonctionnement de la personnalisation dans les fragments. (NEO-88161)
* Correction d’un problème, après la migration vers le nouveau connecteur ODBC Redshift, qui entraînait l’échec de l’activité de workflow Partage avec des erreurs SQL. (NEO-87466)
* Correction d’un problème qui entraînait des nombres d’exclusions inexacts dans les workflows. (NEO-89207)
* Correction d&#39;un problème qui entraînait des indicateurs de clic inexacts pour les notifications push. (NEO-89503)
* Correction d’un problème en raison duquel les logs de diffusion SMS n’étaient pas correctement mis à jour, empêchant la création de rapports d’état précis dans Adobe Campaign. (NEO-88479)
* Correction d’un problème en raison duquel les devis français étaient incorrectement convertis en devis anglais dans le contenu de la diffusion. (NEO-89631)
* Correction d’un problème en raison duquel le serveur en temps réel renvoyait un code de réponse incorrect pour les jetons IMS non valides. (NEO-87428)
* Correction d’un problème en raison duquel les statistiques de diffusion pour les e-mails et les SMS n’étaient pas entièrement recalculées, entraînant des indicateurs de succès inexacts. (NEO-88106)
* Correction d’un problème lié au nouveau connecteur d’envoi SMS en raison duquel les logs de diffusion attribuaient incorrectement le statut de diffusion pour un petit sous-ensemble de messages. (NEO-89581)
* Correction d’un problème lié au nouveau connecteur d’envoi SMS en raison duquel les diffusions de mesures de succès ne se mettaient pas correctement à jour sur les serveurs marketing et de mid-sourcing. (NEO-89850)
* Correction d’un problème de synchronisation entre les instances Real-Time et Marketing qui entraînait l’absence de logs de tracking et des rapports incorrects. (NEO-90247)
* Correction d’un problème d’enrichissement du workflow qui entraînait des erreurs lors de la sélection de champs sur deux liens 1-N consécutifs dans les schémas personnalisés. (NEO-87682)

## Version 8.8.1 {#release-8-8-1}

_jeudi 9 juillet 2025_

### Nouvelles fonctionnalités {#features-8-8-1}

Publiée précédemment pour un petit nombre de clients, la fonctionnalité suivante est désormais disponible pour tous les environnements FDA Campaign :

* **Nouveau connecteur d&#39;envoi de SMS** - Le connecteur d&#39;envoi de SMS a été modernisé et amélioré pour activer les connexions SMPP en mode émetteur-récepteur, activer les connexions SMPP persistantes et assurer une meilleure compatibilité. Un nouveau compte externe SMS est désormais disponible pour toutes les nouvelles implémentations SMS. Les implémentations existantes sont toujours prises en charge, mais il est recommandé de passer à ce nouveau connecteur moderne et étendu. Contactez Adobe si vous souhaitez effectuer une transition vers le nouveau connecteur. [En savoir plus](../send/sms/sms.md)

  >[!NOTE]
  >
  >Cette fonctionnalité n’est **pas** disponible pour les déploiements [Campaign FFDA](../architecture/enterprise-deployment.md).

<!-- (from ACC rn, aleady in the product, to remove?) -->

<!-- * **Enrichment in transactional messages** (to remove?) -->

<!--
* **Multilingual delivery creation** in the Web UI - You can now send multiple email deliveries in different languages in Adobe Campaign Web User Interface. The Multilingual delivery feature allows you to choose the default language of your delivery as well as the different languages in which the delivery can be sent. You can also preview these deliveries in the languages you have chosen. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/edit-content.html)

ACC - Multilingual deliveries - Starting Campaign Web User interface April release, you will be able to send multiple email deliveries in different languages, and access the related dynamic reports. This capability will only be available in Adobe Campaign Web User Interface at the end of April, and require a server update to Campaign v8.7.4.
-->

<!--
*  **Visual fragments** in the Web UI - You can now create, use and archive content fragments. Visual fragments are pre-defined visual blocks that you can reuse across multiple email deliveries, or in content templates. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/content/manage-reusable-content/fragments/fragments.html){target="_blank"}

(already available in console and web, to remove?) 
web - * Visual fragments - You can now archive visual content fragments. Learn more
-->

<!--
* **Delivery alerting** in the Web UI - The Delivery alerting feature is an alert management system that enables a group of users to automatically receive notifications containing information on the execution of their deliveries. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/delivery-alerting/delivery-alerting.html){target="_blank"}
-->

<!--
* **Landing pages improvements**  in the Web UI- The following improvements to landing pages are now available:

    * You can now reference a default subscription/unsubscription landing page when configuring a service. When designing an email, if you define a link to that landing page, users submitting the landing page form are automatically subscribed to or unsubscribed from this service. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/audiences/work-with-services/manage-services.html#create-service){target="_blank"}
    * A new option in the landing page configuration allows anonymous visitors to access the landing page. If you unselect this option, only identified users can access and submit the form. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html#create-landing-page){target="_blank"}
    * A new option in the landing page configuration allows to store additional internal data when the landing page is being submitted. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html#create-landing-page){target="_blank"}
    * A new option enables to use a landing page for several services, making it dynamic. When adding a link to an email, if you select a dynamic landing page, you can select any service. If you select a landing page that has a specific service associated, this service will be automatically used (you cannot select another one). [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html#define-actions-on-form-submission){target="_blank"}
    * Conditional content is now supported in landing pages. [Read more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/lp-content.html){target="_blank"}
    * You can link a landing page to a service, and send a confirmation message when users validate it. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/lp-content.html#lp-message){target="_blank"}
    * You can add captcha to protect your landing page from spam and abuse caused by bots. This is non-intrusive for your customers since it does not require any interaction from them and is based on interactions with your site. [Learn more](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/create-lp.html#captcha){target="_blank"}

web - * **Subscriptions with Landing pages** - You can now link a landing page to a service, and send a confirmation message when users validate it. [Learn more](../landing-pages/lp-content.md#lp-message){target="_blank"}.
Web - * **Captcha in landing pages** - You can now add captcha to protect your landing page from spam and abuse caused by bots. This is non-intrusive for your customers since it does not require any interaction from them and is based on interactions with your site. [Learn more](../landing-pages/create-lp.md#captcha)
-->

<!--
* (from ACC rn, already in product, to remove?) **Rich Push Notification (GA)** - You can now send rich push notifications. Rich push notification is an enhanced form of mobile notification that goes beyond simple text messages by incorporating multimedia elements such as images, interactive buttons, or other rich media content. With this version, a set of templates for rich push notifications are now available for your iOS and Android apps. [Read more](../send/rich-push-android.md). 
ACC * Rich Push Notification templates - You can now send rich push notifications via Android. Rich push notification is an enhanced form of mobile notification that goes beyond simple text messages by incorporating multimedia elements such as images, interactive buttons, or other rich media content. Read more.
-->

Publiée précédemment en disponibilité limitée, la fonctionnalité suivante est désormais disponible **à la demande** :

<!--
* **Dynamic Reporting** - You can now access Dynamic Reporting which provides fully customizable and real-time reports to measure the impact of your marketing activities. It adds access to profile data, enabling demographic analysis by profile dimensions such as gender, city and age in addition to functional email campaign data like opens and clicks. Dynamic reporting is also available for multilingual email deliveries and transactional messages. [Read more](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html){target="_blank"}

ACC **Dynamic Reporting for Transactional messages** - You can now monitor your transactional messages in the Dynamic Reporting user interface. These reports provide the ability to the marketer to view the all the reporting metrics and dimensions of transactional messages, breakdown of deliveries sent through a template in real time. [Read more](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/reporting/get-started-reporting){target="_blank"}
ACC - Dynamic Reporting - As a Campaign Standard migrated user, you can access Dynamic Reporting which provides fully customizable and real-time reports to measure the impact of your marketing activities. It adds access to profile data, enabling demographic analysis by profile dimensions such as gender, city and age in addition to functional email campaign data like opens and clicks. Read more
* **Dynamic Reporting for Multilingual** - Dynamic reporting is now available for multilingual email deliveries. For more information, refer to the [detailed documentation](../reporting/global-reports.md).
-->

* **API Rest** - Vous pouvez désormais utiliser les API Rest pour créer des intégrations pour Adobe Campaign et créer votre propre écosystème en interfaçant Adobe Campaign avec le panneau de technologies que vous utilisez. L’API REST de messagerie transactionnelle est également disponible pour le canal SMS. Lorsque le payload contient à la fois un e-mail et un téléphone mobile, vous pouvez utiliser le champ « wishedChannel » pour spécifier le canal. S’il n’est pas fourni, l’e-mail est utilisé par défaut, sauf si wishedChannel demande explicitement un SMS. Les API transactionnelles basées sur un événement sont également disponibles pour les e-mails. [En savoir plus](../dev/api/get-started-apis.md)

  >[!NOTE]
  >
  >Cette fonctionnalité n’est **pas** disponible pour les déploiements [Campaign FFDA](../architecture/enterprise-deployment.md).

* **List-Unsubscribe en un clic** - Les principaux FAI exigeant des expéditeurs qu’ils autorisent les destinataires à se désabonner instantanément d’un seul clic, vous pouvez désormais activer l’en-tête List-Unsubscribe en un clic dans l’interface utilisateur, directement à partir du modèle d’e-mail ou des propriétés de diffusion. Cette option est activée par défaut. [En savoir plus](../send/email-parameters.md#one-click-list-unsubscribe)

<!--
ACC - Rest APIs - As a Campaign Standard migrated user, you can use Rest APIs to create integrations for Adobe Campaign and build your own ecosystem by interfacing Adobe Campaign with the panel of technologies that you use. Read more
* **SMS REST API support (LA)** - The Transactional Messaging REST API is now available for the SMS channel. When both email and mobilePhone are present in the payload, you can use the "wishedChannel" field to specify the channel. If not provided, email will be used by default unless wishedChannel explicitly requests SMS. For more information, refer to the [detailed documentation](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/apis/managing-transactional-messages){target=_blank}.
ACC - SMS REST API support - The Transactional Messaging REST API is now available for the SMS channel. When both email and mobilePhone are present in the payload, you can use the "wishedChannel" field to specify the channel. If not provided, email will be used by default unless wishedChannel explicitly requests SMS.
ACC * **Transactional messaging REST APIs** - Event-based Transactional APIs are now available for Emails. [Read more](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/apis/managing-transactional-messages){target="_blank"}
-->

Outre les fonctionnalités répertoriées ci-dessus, cette version comprend également un ensemble de fonctionnalités disponibles dans l’interface utilisateur web de Campaign :

* [Création de diffusion multilingue](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/edit-content.html#multilingual-delivery){target="_blank"}
* [Alertes de diffusion](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/delivery-alerting/delivery-alerting.html){target="_blank"}
* [Améliorations des landing pages](https://experienceleague.adobe.com/docs/campaign-web/v8/landing-pages/get-started-lp.html){target="_blank"}
* [Rapports dynamiques](https://experienceleague.adobe.com/docs/campaign-web/v8/reports/dynamic-reporting/get-started-reporting.html){target="_blank"} (à la demande)
* [Valorisation de marque centralisée](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/conf/branding/branding-gs.html?lang=fr){target="_blank"} (à la demande, nouvelles mises en œuvre)

Reportez-vous aux notes de mise à jour de l’interface utilisateur web de Campaign [&#128279;](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=fr){target="_blank"}

### Améliorations générales {#improvements-8-8-1}

* Microsoft Fabrics est désormais pris en charge en tant que base de données externe avec Adobe Campaign Federated Data Access (FDA). [En savoir plus](../config/external-accounts.md#transfer-data-external-accounts)
* Campaign v8 prend désormais en charge Android 15 et iOS 18 pour les notifications push. [En savoir plus](../start/compatibility-matrix.md#MobileSDK)
* Les bases de données cloud sont désormais prises en charge en plus des bases de données on-premise pour la création de tunnels Secure Virtual Private Network. [En savoir plus](../config/enhanced-security.md#vpn-databases)
* Un nouvel ensemble de champs « ID du fournisseur » a été ajouté dans la section « Trafic entrant » du connecteur SMS 2.0. [En savoir plus](../send/sms/smpp-external-account.md#incoming-traffic)
* Les destinataires désabonnés via la méthode List-Unsubscribe « mailto » ne sont plus mis en quarantaine. Ils sont soit désabonnés du service associé à la diffusion, soit envoyés à l’adresse de place sur la liste bloquée (section « Ne plus contacter » du profil) si aucun service n’a été défini pour la diffusion. [En savoir plus](../send/quarantines.md)
* Une nouvelle version du rapport d’inbox rendering est désormais disponible dans la console cliente Adobe Campaign.
* Le fichier `setup-client.exe` a été remplacé par un fichier `ac-client.msi`, offrant ainsi une méthode plus simple aux administrateurs pour effectuer des mises à niveau en masse sans nécessiter l’intervention de l’utilisateur.

### Correctifs {#fixes-8-8-1}

* Correction d’un problème où les réponses automatiques n’étaient pas reçues en raison d’une période de validité non valide dans SMS 2.0. Cela garantit une diffusion correcte des messages après la migration. (NEO-88088)
* Correction d’un problème dans SMS 2.0 en raison duquel certains champs du tableau `inSms` n’étaient pas correctement mis à jour, afin de garantir une insertion de données précise pour les fonctionnalités SMS. (NEO-87906)
<!--
* NOOOO Addressed delivery preparation failures for IndiGo Aviation after upgrading to v7.4.2. This fix resolves personalization and deduplication-related errors, enabling smooth delivery workflows. (NEO-87693)
* NOOOO Corrected Redshift database function definitions in version 8.6.4, ensuring proper execution of functions like `AddDays`, `AddHours`, `AddMinutes`, and `AddSeconds`. (NEO-87305)
* Provided a silent installation mechanism for the client console to facilitate mass upgrades without user intervention. This resolves challenges with manual installations. (NEO-69772)
-->
* Correction des échecs de workflow de nettoyage de la base de données en raison de références de colonne manquantes ou incorrectes dans les requêtes SQL. Cela permet de purger correctement les journaux et les données des visiteurs. (NEO-86813)
* Correction d’un problème en raison duquel les dates des événements étaient manquantes dans les logs de diffusion. Ce correctif garantit l’exactitude du remplissage de la date d’événement, essentiel pour les déclencheurs et les workflows planifiés. (NEO-86708)
* Correction de problèmes d’insertion des logs de diffusion SMS dans SMS 2.0, en assurant une journalisation correcte dans la table `nmsBroadLogMid`. (NEO-86556)
* Résolution des problèmes d’extraction de fichiers avec le mode de diffusion externe dans les modèles de publipostage direct, en garantissant la compatibilité et la fonctionnalité. (NEO-86520)
* Résolution des problèmes de traitement des diffusions impliquant un routage partagé sur plusieurs instances MID, afin de garantir des mises à jour de statut et un débit de diffusion précis. (NEO-86500)
* Correction des données de tracking manquantes dans les rapports dynamiques après la migration de Campaign Standard vers Campaign v8, ce qui permet d’obtenir des rapports précis pour les logs de tracking des diffusions. (NEO-86419)
* Résolution des problèmes de déclenchement des workflows en raison desquels les workflows s’exécutaient deux fois, provoquant des violations de clés en double. Ce correctif garantit une gestion et une exécution correctes des événements. (NEO-86154)
* Correction de problèmes de compatibilité avec les fonctions SQL Redshift OOTB après déploiement, en assurant la bonne exécution de fonctions telles que `GetDate()` dans les workflows. (NEO-85834)
* Correction des problèmes de rendu dans les versions d’e-mail où les images disparaissaient lorsque des URL étaient jointes. Ce correctif garantit un affichage correct des images dans les aperçus de boîte de réception. (NEO-85716)
* Correction du rendu des guillemets fermés dans l’interface utilisateur web, assurant ainsi un affichage précis des caractères dans les diffusions e-mail. (NEO-85687)
* Correction de la fonctionnalité de lien de page miroir, qui assurait une navigation appropriée entre les variantes linguistiques dans les pages miroir. (NEO-85625)
* Résolution des problèmes de format de date dans les sélecteurs de date des applications web, en veillant à la compatibilité avec les formats de date japonais (`yyyy-mm-dd`). (NEO-85234)
* Correction de problèmes de workflow de post-traitement avec d’autres configurations de routage en midsourcing, assurant une exécution correcte du workflow. (NEO-85111)
* Amélioration du débit de diffusion d’Android lors de l’utilisation de vagues, en veillant à ce que les fragments de diffusion soient traités dans le bon ordre en fonction de la planification. (NEO-84324)
* Correction des échecs de préparation des diffusions en raison d’erreurs de traitement nulles dans `to_varchar` fonction, assurant ainsi le bon lancement des campagnes. (NEO-84108)
* Résolution des problèmes de connexion SFTP causés par des versions `libcurl` et `libssh2` obsolètes, en assurant la compatibilité avec les serveurs SFTP hébergés sur Azure. (NEO-84038)
* Correction de problèmes du connecteur FDA Snowflake impliquant des erreurs d’authentification de paire de clés, assurant la réussite des connexions à la base de données. (NEO-84024)
* Correction des problèmes de fonctionnalité des règles de typologie, en assurant une application correcte des règles de pression dans les diffusions PUSH. (NEO-84010)
* Correction des erreurs de requête BigQuery provoquées par des comparaisons de dates et d’horodatages incohérentes après la mise à niveau, assurant ainsi la compatibilité avec les conditions de filtrage. (NEO-83826)
* Correction d’un problème où les activités de diffusion échouaient lors de la reprise de diffusions en pause en raison d’erreurs de personnalisation. Ce correctif garantit des workflows de diffusion plus fluides et empêche les erreurs liées aux activités en pause. (NEO-83809)
* Correction d’un problème dans FFDA lors de l’utilisation de l’option « requête de chargement d’enregistrement cible ». Ajout de la prise en charge des clauses « order by » et « where ». (NEO-83793)
* Correction des échecs de diffusion récurrents causés par l’écriture de valeurs nulles dans des colonnes non nulles de la table broadLogRcp. Ce correctif améliore la fiabilité de la diffusion et empêche les erreurs lors des campagnes dynamiques. (NEO-83729)
* Correction d’un problème en raison duquel les adresses de contrôle étaient dupliquées lors de la préparation de la diffusion, ce qui entraînait des incohérences dans le nombre de messages. Ce correctif garantit un ciblage précis et empêche les erreurs de duplication. (NEO-83703)
* Correction d’un problème critique en raison duquel les diffusions de production étaient envoyées après leur période de validité, ce qui pouvait entraîner des problèmes juridiques. Les diffusions respectent désormais strictement les périodes de validité définies. (NEO-83350)
* Correction d’un problème d’espace lors du chargement de gros volumes de données dans les tables Teradata. Ce correctif optimise le traitement des données et résout les erreurs intermittentes dans les environnements de production. (NEO-83252)
* Correction d’une erreur de workflow technique liée aux erreurs SendMetricsToNewRelic, qui entraînait des retards dans le traitement des événements RT. Ce correctif garantit une exécution plus fluide des workflows et empêche les retards d’événements. (NEO-83143)
* Correction d&#39;un échec de workflow de nettoyage de la base de données dû à des problèmes de conversion ID vers UUID dans les instances d&#39;interaction FFDA. Cette mise à jour garantit des opérations de nettoyage correctes et réduit la charge du système. (NEO-83138)
* Résolution des échecs de diffusion provoqués par des contraintes sur les longueurs de noms internes des membres d’amorçage. Ce correctif permet des noms internes plus longs sans affecter la personnalisation de la diffusion. (NEO-83044)
* Correction d’un problème en raison duquel les diffusions étaient bloquées dans l’attente de personnalisation en raison d’erreurs aléatoires. Cette mise à jour garantit des processus de personnalisation plus fluides et une exécution fiable de la diffusion. (NEO-82781)
* Correction d’un problème en raison duquel les propositions d’offre ne pouvaient pas être examinées dans la console en raison d’erreurs d’API et de lenteur. Ce correctif améliore la réactivité de l’interface utilisateur et garantit une fonctionnalité d’offre appropriée. (NEO-82742)
* Résolution des blocages intermittents dans la console Adobe Campaign lors de l’utilisation d’objets de diffusion personnalisés. Ce correctif garantit la stabilité et la fiabilité lors de l’utilisation de workflows personnalisés. (NEO-82675)
* Correction des échecs de traitement lent et de workflow signalés après la migration de la v7 vers la v8. Cette mise à jour optimise les workflows de campagne et garantit leur exécution en temps voulu. (NEO-82665)

<!--
* Resolved an issue where sysfilters were generating incorrect SQL queries after upgrading to v8.6.3. This fix ensures proper query generation and restores sysfilter functionality. (NEO-82591)
-->

* Correction d’un problème critique en raison duquel les processus enfants du MTA étaient bloqués, bloquant les diffusions push et WhatsApp. Cette mise à jour garantit des workflows de communication plus fluides et empêche les goulots d’étranglement de diffusion. (NEO-82351)
* Correction d’un problème de migration des données en raison duquel les champs de chaîne des tables GCP provoquaient des erreurs lors des mises à jour de Teradata. Ce correctif élimine le besoin de solutions et améliore l’efficacité des workflows. (NEO-82260)
* Mise à jour de la logique de nettoyage de la base de données pour tenir compte des bases de données principales dans les instances FFDA, empêchant les tentatives inutiles de purger les tables inexistantes. Ce correctif optimise les opérations de nettoyage. (NEO-81879)
* Résolution des blocages de console causés par l’utilisation de sous-workflows en combinaison avec des champs d’énumération. Ce correctif garantit la stabilité lorsque vous utilisez des workflows enrichis. (NEO-81864)
* Correction d’un problème où les champs de sous-affinité dans les mappings de ciblage étaient incorrectement modifiés après la duplication de diffusion, ce qui provoquait des échecs de workflow. Cette mise à jour garantit la cohérence des valeurs de sous-affinité. (NEO-81809)
* Ajout de la prise en charge des caractères génériques dans les activités de transfert de fichiers de Adobe Campaign Classic v8, ce qui permet aux utilisateurs de charger des fichiers avec des noms dynamiques (par exemple, `abc_*`) dans les workflows. (NEO-81758)
* Ajout d’une option pour activer l’indicateur `content-available` dans les notifications push iOS pour Adobe Campaign Classic v8. Cette amélioration permet aux applications mobiles de stocker les notifications dans la boîte de réception et prend en charge les mises à jour en arrière-plan, résolvant les problèmes de rejet de diffusion causés par les limitations APNS. (NEO-81721)

<!--
* Updated the Campaign 7.4.1 release upgrade process to require manual installation of dependencies. Documentation has been provided to guide users on installing required libraries such as `epel-release`, `java-11-openjdk-headless`, and others. (NEO-81433)
-->

* Ajout d’une option de configuration de délai d’expiration pour les connexions BigQuery dans Adobe Campaign Classic v8. Cette amélioration permet aux utilisateurs et utilisatrices d’ajuster le délai d’expiration des requêtes, ce qui résout les problèmes liés aux échecs de requête en raison des limites de délai d’expiration par défaut. (NEO-81222)
* Correction d&#39;un problème intermittent en raison duquel les URL de page miroir échouaient pour les diffusions envoyées via les comptes externes de routage partagé et alternatif après la migration vers la v8. Les fragments de diffusion sous-jacents sont désormais correctement copiés dans `mirrorPageInfo`. (NEO-81105)

<!--
* Resolved an authentication failure issue with inMail caused by token expiration. Restarting the `nlserver` process now resolves the error. (NEO-80683)
-->

* Correction du bouton « Accéder à la nouvelle UI web » dans la console cliente pour pointer vers l’URL appropriée (`https://experience.adobe.com`) pour les instances d’exploitation. Cela résout les problèmes liés aux URL non valides dans les environnements de production. (NEO-80673)
* Correction d’un problème dans l’activité Partage en raison duquel l’utilisation simultanée du tri et de la taille (sous la forme d’un pourcentage du segment) provoquait des erreurs SQL. Cette fonctionnalité fonctionne désormais correctement. (NEO-80432)
* Correction d&#39;un problème de blocage dans les workflows à l&#39;aide de `CCurlAzureBlobStorage::UploadStream`. Les workflows s’exécutent désormais sans erreurs de segmentation lors des chargements de stockage Blob Azure. (NEO-79598)
* Correction d’un problème où les pages miroir n’étaient pas visibles à partir de la console cliente dans les environnements de production. Les liens de la page miroir fonctionnent désormais correctement en vue e-mail et console. (NEO-78946)
* Correction d’un problème de log de diffusion en raison duquel certains logs étaient incorrectement marqués comme « Diffusion annulée » malgré une diffusion réussie des messages. La cause principale liée aux incohérences de date de contact et de date d’événement a été traitée. (NEO-78933)
* Mise à jour de la bibliothèque `com.google.code.gson:gson` pour améliorer la sécurité. (NEO-78299)
* Résolution des erreurs de contrainte de clé en double dans les journaux de connexion FDA (`nmsconnectionlogs`) qui provoquaient des échecs de workflow. La logique d’insertion a été ajustée pour éviter les identifiants en double. (NEO-78050)
* Correction d’un problème où les adresses e-mail en quarantaine étaient incorrectement marquées comme mobiles dans le tableau d’adresses, ce qui provoquait des erreurs d’analyse de diffusion. La logique de réconciliation entre les objets de la diffusion a été corrigée. (NEO-76986)
* Correction d’un échec de préparation de diffusion lors de l’utilisation de populations témoins avec une base de données Oracle. La génération des requêtes SQL a été corrigée afin d&#39;assurer la compatibilité avec les bases de données Oracle. (NEO-76947)
* Résolution des échecs de diffusion causés par la création simultanée de dossiers lors des transitions du nouveau mois. La logique de création du dossier de diffusion a été adaptée pour éviter les violations de clés en double. (NEO-76824)
* Correction de problèmes de conversion de fuseau horaire incohérents dans les comptes externes Teradata. Les horodatages affichés s’alignent désormais correctement sur les paramètres de fuseau horaire configurés. (NEO-76716)
* Workflows de nettoyage de base de données améliorés pour gérer efficacement les jeux de données volumineux. Une nouvelle approche utilisant les identifiants de ligne et les variables de liaison a été mise en œuvre pour optimiser les performances de suppression. (NEO-76439)
* Correction d’un problème en raison duquel les diffusions externes avec le canal « Autre » ne généraient pas de fichiers de sortie. Les propriétés de la diffusion incluent désormais correctement le chemin d’accès aux fichiers générés. (NEO-75962)
* Correction d’erreurs dans le workflow `ffdaReplicateStagingData` en raison de mises à jour de données volumineuses. Les paramètres de délai d’expiration et la gestion de la taille du tableau ont été optimisés pour éviter les échecs de workflow. (NEO-75643)
* Correction d’un problème en raison duquel la prévisualisation des fichiers de sortie de publipostage direct entraînait le vidage des tableaux de bord. Le tableau de bord s’affiche désormais correctement après la prévisualisation des fichiers. (NEO-75359)
* Amélioration des indicateurs de tracking pour les notifications push afin d&#39;inclure les clics et les ouvertures. Des indicateurs tels que `@recipientClick`, `@personClick` et `@totalRecipientClick` prennent désormais en compte les clics sur les notifications mobiles. (NEO-75240)
* Correction d&#39;erreurs dans les workflows de nettoyage pour les diffusions avec des statuts externes en attente d&#39;annulation. La logique de récupération des enregistrements de la base de données a été corrigée. (NEO-74833)
* Résolution d&#39;un problème d&#39;incohérence de fuseau horaire en Russie (UTC+3:00 Moscou) où les heures de sortie `nlserver` étaient incorrectes. La logique de synchronisation temporelle a été mise à jour. (NEO-74754)
* Correction d’erreurs dans le workflow `defaultMidSourcingDlvStat` en raison d’une syntaxe SQL incorrecte pour les bases de données MSSQL. La logique de génération de requête a été ajustée pour des raisons de compatibilité. (NEO-74156)
* Correction de plusieurs blocages dans le processus web. (NEO-73174)
* Correction d’un problème en raison duquel les requêtes BigQuery échouaient lorsque des apostrophes étaient présentes dans les conditions . La logique de gestion des requêtes a été mise à jour afin d’interpréter correctement les caractères spéciaux. (NEO-72547)
* Correction d’un problème en raison duquel les règles de typologie avec des filtres d’exclusion ne fonctionnaient pas correctement. La génération de la requête SQL pour la préparation de la diffusion a été corrigée. (NEO-72292)
* Correction des incohérences dans les dates des événements et des contacts pour la gestion des bounces. La logique de gestion des fuseaux horaires a été améliorée. (NEO-72277)
* Amélioration de la gestion des caractères UTF-8 incorrectement convertis dans les diffusions de publipostage direct. Les caractères masqués sont désormais correctement traités afin d’éviter les échecs de diffusion. (NEO-72148)
* Correction d’erreurs dans l’activité de SMS entrant en raison desquelles les filtres provoquaient des problèmes d’enregistrement. Le workflow s’enregistre désormais correctement sans générer d’erreurs. (NEO-70427)
* Correction de la génération de la requête SQL pour les critères d&#39;éligibilité regroupés dans les emplacements. Des parenthèses manquantes dans les conditions SQL ont été ajoutées pour assurer un filtrage correct. (NEO-70425)

<!--
* Updated the public documentation link in the `ffdaUnicity` workflow email template to point to the correct page for key management in v8. (NEO-67996)
-->

* Correction d’erreurs intermittentes dans les workflows de chargement des données BigQuery provoquées par des problèmes de contenu HTTP ou de codage de transfert. La logique de gestion des connexions a été améliorée. (NEO-66989)

## Version 8.6.5 {#release-8-6-5}

_samedi 25 avril 2025_

>[!AVAILABILITY]
>
>Cette version est en **disponibilité limitée** (LA).

### Nouvelles fonctionnalités {#features-8-6-5}

**Nouveau connecteur d’envoi de SMS** : le connecteur d’envoi de SMS a été modernisé et amélioré afin d’activer les connexions SMPP en mode émetteur-récepteur, d’activer les connexions SMPP persistantes et d’assurer une meilleure compatibilité pour les environnements en transition depuis Adobe Campaign Standard. Un nouveau compte externe SMS est désormais disponible pour toutes les nouvelles implémentations SMS. L’implémentation existante est toujours prise en charge, mais il est recommandé de passer au nouveau connecteur moderne et étendu. [En savoir plus](../send/sms/sms.md).

### Améliorations générales {#improvements-8-6-5}

* Les performances de l’application ont été améliorées, dans le contexte d’un déploiement Grands comptes (FFDA), notamment l’envoi de BAT de diffusion et le nettoyage de la base de données.

* Pour accroître la sécurité de toutes les communications entre les applications, mTLS est désormais pris en charge pour les appels API externes.

* MTA (Mail Transfer Agent) : correction du blocage d’un enfant MTA orphelin au statut **[!UICONTROL Démarrage en attente]**.

### Correctifs {#fixes-8-6-5}

Les problèmes suivants ont également été corrigés dans cette version :

NEO-67620, NEO-71534, NEO-80245, NEO-81105, NEO-81758, NEO-81908, NEO-82351, NEO-82742, NEO-83044, NEO-83138, NEO-83350, NEO-83729, NEO-83793, NEO-83809, NEO-84038, NEO-84108, NEO-85269, NEO-86121, NEO-86556, NEO-86739

## Version 8.7.4 {#release-8-7-4}

_vendredi 10 avril 2025_

>[!AVAILABILITY]
>
>Cette version est en **disponibilité limitée** (LA). Elle est limitée aux personnes effectuant la migration **depuis Adobe Campaign Standard vers Adobe Campaign v8** et ne peut pas être déployée dans un autre environnement.
>
>Si vous êtes un utilisateur ou une utilisatrice de Campaign Standard et que vous passez à Campaign v8, apprenez-en plus sur cette transition dans la [documentation sur l’interface d’utilisation d’Adobe Campaign Web v8](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nouvelles fonctionnalités {#features-8-7-4}

* **Prise en charge de l’API REST SMS** : l’API REST de messagerie transactionnelle est désormais disponible pour le canal SMS. Lorsque le payload contient à la fois un e-mail et un téléphone mobile, vous pouvez utiliser le champ « wishedChannel » pour spécifier le canal. S’il n’est pas fourni, l’e-mail est utilisé par défaut, sauf si wishedChannel demande explicitement un SMS.

* **Diffusions multilingues** : à compter de la version d’avril de l’interface d’utilisation de Campaign Web, vous pourrez envoyer plusieurs diffusions par e-mail dans différentes langues et accéder aux rapports dynamiques associés. Cette fonctionnalité ne sera disponible dans l’interface d’utilisation d’Adobe Campaign Web qu’à la fin du mois d’avril et nécessite une mise à jour du serveur vers la version 8.7.4 de Campaign.

### Correctifs {#fixes-8-7-4}

Les problèmes suivants ont été corrigés dans cette version :

NEO-80245, NEO-83559

## Version 8.7.3 {#release-8-7-3}

_14 février 2025_

>[!AVAILABILITY]
>
>Cette version est en **disponibilité limitée** (LA). Elle est limitée aux personnes effectuant la migration **depuis Adobe Campaign Standard vers Adobe Campaign v8** et ne peut pas être déployée dans un autre environnement.
>
>Si vous êtes un utilisateur ou une utilisatrice de Campaign Standard et que vous passez à Campaign v8, apprenez-en plus sur cette transition dans la [documentation sur l’interface d’utilisation d’Adobe Campaign Web v8](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nouvelles fonctionnalités {#features-8-7-3}

* **Rapports dynamiques pour les messages transactionnels** : vous pouvez désormais surveiller vos messages transactionnels dans l’interface d’utilisation des rapports dynamiques. Ces rapports permettent aux professionnelles et professionnels du marketing de visualiser toutes les mesures et dimensions de rapports des messages transactionnels, ainsi que la répartition des diffusions envoyées via un modèle en temps réel. [En savoir plus](https://experienceleague.adobe.com/docs/campaign-web/v8/reports/dynamic-reporting/get-started-reporting.html){target="_blank"}

* **API REST de messagerie transactionnelle** : les API transactionnelles basées sur un événement sont désormais disponibles pour les e-mails. [En savoir plus](../dev/api/get-started-apis.md)

### Correctifs {#fixes-8-7-3}

Les problèmes suivants ont été corrigés dans cette version :

NEO-79373, NEO-81908, NEO-83081

## Version 8.6.4 {#release-8-6-4}

_15 janvier 2025_

### Améliorations générales {#improvements-8-6-4}

* La stabilité de l’application Campaign a été améliorée lors de l’analyse de la diffusion dans le contexte d’un [déploiement Grands comptes (FFDA)](../../v8/architecture/enterprise-deployment.md).
* Cette version s’accompagne de mécanismes d’architecture FFDA améliorés et renforcés, notamment la gestion des clés, l’évaluation et la réplication de données.
* De nouveaux workflows techniques ont été introduits pour le [déploiement Grands comptes (FFDA)](../../v8/architecture/enterprise-deployment.md). Ces workflows répliquent la diffusion et les données associées en centralisant les demandes de réplication parallèles sur les tables correspondantes. Ces workflows commencent par `Replicate nms`. [En savoir plus](../architecture/replication.md)
* Une nouvelle option **Activer le superviseur de surveillance pour que le workflow continue à fonctionner en permanence** est désormais disponible dans les propriétés du workflow. Lorsque cette option est activée, les workflows redémarrent automatiquement après une erreur. Par défaut, le redémarrage se produit toutes les 30 secondes si le workflow rencontre toujours une erreur. Pour ajuster cet intervalle, vous pouvez créer une nouvelle option `XtkWorkflow_WatchdogRestartTimerTimeout` et définir un type de données Entier pour spécifier le nouveau délai. Cette option ne doit être activée que dans les workflows techniques. [En savoir plus](../../automation/workflow/workflow-properties.md#execution)

### Améliorations de la sécurité {#security-8-6-4}

Amélioration du traitement des requêtes HTTP dans le module web Apache afin de renforcer la sécurité et d’empêcher les vulnérabilités potentielles de gestion des requêtes. (NEO-85824)

La connexion aux solutions et applications Adobe par le biais du compte externe **[!UICONTROL Adobe Experience Cloud]** a été mise à jour pour renforcer la sécurité.

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### Mises à jour de compatibilité {#comp-8-6-4}

Les connecteurs FDA suivants ont été ajoutés. Voir cette [page](compatibility-matrix.md#FederatedDataAccessFDA).

* Databricks est désormais pris en charge en tant que base de données externe avec Adobe Campaign Federated Data Access (FDA).

* Un nouveau connecteur ODBC FDA Amazon Redshift est désormais disponible. Il offre une connectivité améliorée, une maintenance plus facile et une meilleure compatibilité. Cette nouvelle version apporte les améliorations suivantes :

   * Le nouveau connecteur repose sur l’interface ODBC qui s’aligne sur nos connecteurs FDA les plus récents. Cela garantit une prise en charge à long terme.
   * Il introduit également un nouveau mécanisme de chargement de données à l’aide de compartiments s3, ce qui améliore considérablement les performances.

  Le connecteur hérité peut toujours être utilisé. Si vous souhaitez tester la nouvelle version, contactez votre représentant ou représentante Adobe.

### Correctifs {#fixes-8-6-4}

Les problèmes suivants ont été corrigés dans cette version :

NEO-48232, NEO-67814, NEO-71388, NEO-74855, NEO-75643, NEO-75962, NEO-76132, NEO-76958, NEO-76986, NEO-77162, NEO-77452, NEO-78946, NEO-79373, NEO-80243, NEO-80314, NEO-81127, NEO-81209, NEO-81223, NEO-81287, NEO-81290, NEO-81312, NEO-81512, NEO-81520, NEO-81566, NEO-81704, NEO-81908, NEO-82195, NEO-82591, NEO-82592, NEO-82640, NEO-82665, NEO-82781, NEO-82920, NEO-83081, NEO-83096, NEO-83137, NEO-83143.

