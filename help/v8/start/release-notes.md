---
title: Notes de mise à jour de Campaign v8
description: Dernière version de Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 4a3e6cf15b1877e6eb4e13fdee056356eab267c5
workflow-type: tm+mt
source-wordcount: '1754'
ht-degree: 6%

---

# Dernières versions {#latest-release}

Cette page répertorie les nouvelles fonctionnalités, les améliorations et les correctifs des **dernières versions** de Campaign v8 (console). Pour en savoir plus sur les publications, les versions et les mises à niveau de Campaign, consultez [cette page](upgrades.md). Les autres versions sont répertoriées dans la section Versions précédentes de cette documentation.

## Version 8.9.2 {#release-8-9-2}

>[!CAUTION]
>
> La mise à niveau de la console cliente est obligatoire. Découvrez comment mettre à niveau votre console cliente sur cette [page](../start/connect.md#upgrade-ac-console).

_3 mai 2026_

### Améliorations de la sécurité {#security-8-9-2}

* Pour maintenir une sécurité, une stabilité et une conformité optimales, toutes les instances ont été mises à niveau vers Debian 13 et PostgreSQL 17.

### Correctifs {#fixes-8-9-2}

>[!NOTE]
>
> Les correctifs répertoriés ci-dessous ont été progressivement déployés sur plusieurs versions 8.9.2 successives. Accédez au **[!UICONTROL menu Aide > À propos...]** [&#128279;](upgrades.md#version) pour vérifier que vous disposez de la version 8.9.2 (11d1c68) la plus récente. Pour plus d’informations, contactez votre représentant Adobe.

* Correction d’un problème où les dates d’événement dans les événements transactionnels étaient incorrectement définies en raison d’un problème de conversion de type de données, ce qui provoquait des dates incorrectes dans les rapports dynamiques. (NEO-93923)
* Correction d’un problème en raison duquel les notifications push silencieuses d’Android et d’iOS échouaient lors de la préparation de la diffusion lorsque les champs de titre et de corps étaient vides. (NEO-93739)
* Correction d’un problème qui empêchait la capture du champ de langue pour les jetons d’enregistrement de l’application Android en raison de clés de réconciliation incorrectes. (NEO-93100)
* Correction d’un problème en raison duquel la préparation de diffusion échouait lors de l’application de règles de typologie personnalisées avec des règles de pression. (NEO-94457)
* Correction d’un problème en raison duquel la console cliente pouvait rencontrer des échecs de traitement des requêtes HTTP. (NEO-94071)

<!-- BUILD 8.9.2.9829.9669833 -->

* La surveillance FDA est désormais désactivée par défaut pour éviter les erreurs d’insertion de journaux de connexion. (NEO-94841)
* Correction d&#39;un problème en raison duquel les appels SOAP Interaction utilisés pour le rachat d&#39;offres pouvaient échouer avec une erreur de résolution d&#39;espace de noms. (NEO-94787)
<!-- infra * Fixed an issue where Snowflake connections using private key authentication could fail on ARM64 architectures. (NEO-94350) -->
* Correction d’un problème où les champs de chaîne de longueur 1 pouvaient entraîner des erreurs SQL dans les tables temporaires de workflow sur PostgreSQL 17. (NEO-94487)
<!-- linked to previous build * Fixed an issue where the server could fail to restart after a Debian 13 build upgrade due to a missing dependency. (NEO-94598) -->

<!-- BUILD 8.9.2.9829.c90aa36 -->

* Correction d’un problème en raison duquel l’option **Afficher la page miroir** dans la console cliente et l’interface utilisateur web pouvait renvoyer une erreur « Page miroir incorrecte ». (NEO-93303)

<!-- BUILD 8.9.2.9830.4a6f868 -->

* Correction d’un problème en raison duquel le workflow technique prêt à l’emploi **Tracking** pouvait échouer après l’installation d’un package multivarié dans les déploiements FFDA. (NEO-94972)
* Correction d’un problème en raison duquel la préparation de la diffusion pouvait ne pas ajouter de destinataires à la cible lorsque le modèle de diffusion utilisait une formule de poids faisant référence à la diffusion actuelle. (NEO-94892)
<!-- hotfix -->
* Correction d’un problème en raison duquel les enrichissements de workflow à l’aide de jointures sur deux liens 1-N consécutifs pouvaient échouer avec des erreurs SQL après une mise à niveau. (NEO-94893)

<!-- BUILD 8.9.2.9831.f53d3d2 -->

* Correction d’un problème dans le pipeline d’e-mail qui entraînait une consommation excessive de mémoire au fil du temps. (NEO-95088)
* Correction d’un problème en raison duquel la règle de typologie des e-mails en conflit pouvait exclure de manière incorrecte les destinataires non dupliqués d’une cible de diffusion lors de l’utilisation d’adresses de contrôle ou de BAT. (NEO-95026)
* Correction d&#39;un problème en raison duquel le workflow technique prêt à l&#39;emploi **Notification d&#39;offre** pouvait échouer après une mise à niveau. (NEO-95064)
* Le processus d’installation de packages multivariés a été amélioré afin d’éviter les échecs de workflow de suivi lors des mises à niveau de build. (NEO-95018)

<!-- BUILD 8.9.2.9831.11d1c68 -->

* Correction d’un problème en raison duquel le serveur se bloquait à plusieurs reprises, provoquant des pannes d’instance. (NEO-95304)
* Correction d’un problème en raison duquel le suivi et les liens de page miroir ne parvenaient pas à charger les diffusions. (NEO-95239)
* Correction d’un problème qui entraînait une boucle de redirection lors de la connexion aux applications web de Campaign protégées par l’authentification unique IMS. (NEO-95188)
* Correction d’un problème en raison duquel la date de création de diffusion était absente des fichiers d’extraction de diffusion après l’enregistrement de la diffusion. (NEO-95010)
* Correction d’un problème en raison duquel les workflows enfants générés dans un volume élevé pouvaient rester bloqués à l’état **En édition**, ce qui réduisait la capacité des workflows transactionnels. (NEO-95131)
* Correction d&#39;un problème en raison duquel l&#39;activité **Lecture de liste** pouvait remplacer les modèles de liste prédéfinis par des structures de liste générées par des workflows, provoquant des échecs dans les workflows en aval. (NEO-95103)
* Correction d’un problème en raison duquel la gestion des commentaires sur les notifications push entraînait le blocage du serveur lors du traitement de diffusions en masse. (NEO-95150)
* Correction d’un problème en raison duquel l’ouverture de l’onglet **Data** sur le schéma `xtk:workflow` dans l’explorateur de schémas pouvait déclencher un message d’erreur. (NEO-94923)
<!-- hotfixes -->
* Correction d’un problème en raison duquel l’activité **Enrichissement** ne pouvait plus récupérer les attributs de sortie des activités **Sous-workflow** en amont, ce qui entraînait l’échec des workflows. (NEO-95151)
* Correction d’un problème d’ingestion des données de tracking qui empêchait les mises à jour de l’état des diffusions et bloquait le traitement des messages en aval. (NEO-94666)
* Correction d’un problème en raison duquel certaines actions de la console cliente liées aux propositions d’offre pouvaient déclencher des requêtes de longue durée sur les bases de données Snowflake, provoquant des verrous et de la lenteur. (NEO-92936)
* Correction d’un problème en raison duquel les options personnalisées de stockage des clés chiffrées ne pouvaient pas être configurées sur les comptes externes Snowflake. (NEO-93302)

<!-- 
Internal/non-customer-facing:
* Internal test automation task added to cover NEO-94893. (NEO-94990) — autotest only
Customer-specific hotfixes:
* Fixed an issue affecting WhatsApp delivery preparation. (NEO-92480) — HeroMotoCorp only
* Added a feature-flagged optimization to use dynamic shared memory in Customer Targeting Audience (CTA) processing. (NEO-93542) — DerTour only
* Fixed an issue where the delivery alerting workflow could fire incorrect "long start pending" notifications even when deliveries were sent within the configured threshold. (NEO-93434) — non-ZDT hotfix, NORC only
* Added a new parameter in the mobile SDK to allow identification of the source instance for push notifications. (NEO-94650) — ICICI only
* Fixed an issue with the custom send time feature on the Web UI where deliveries waited until the contact date and time to execute instead of executing at the equivalent local time per recipient timezone, breaking parity with Campaign Standard behavior. (NEO-94762) — H&M only (in progress at time of writing)
-->

## Version 8.9.1 {#release-8-9-1}

_27 janvier 2026_

>[!CAUTION]
>
> La mise à niveau de la console cliente est obligatoire. Découvrez comment mettre à niveau votre console cliente sur cette [page](../start/connect.md#upgrade-ac-console).

### Nouvelles fonctionnalités {#new-8-9-1}

Le **nouveau connecteur d&#39;envoi de SMS** est désormais disponible pour tous les clients (GA). Consultez la [documentation détaillée](../send/sms/sms.md).

Cette version est fournie avec un ensemble de fonctionnalités disponibles dans l’interface utilisateur web de Campaign :

* [Fonctionnalités de diffusion multilingue (GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html){target="_blank"}
* [Enrichissement du profil dans les messages transactionnels (GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html){target="_blank"}
* [Adobe Experience Manager Live et copies de langue](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-multilingual.html){target="_blank"}
* [Expériences de contenu - Tests AB](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/ab-testing.html){target="_blank"}
* [Activité de diffusion au fil de l&#39;eau](https://experienceleague.adobe.com/docs/campaign-web/v8/wf/design-workflows/continuous-delivery.html){target="_blank"}
* [Gestion de la validation des campagnes](https://experienceleague.adobe.com/docs/campaign-web/v8/campaigns/campaign-approvals.html){target="_blank"}

Reportez-vous aux notes de mise à jour de l’interface utilisateur web de Campaign [&#128279;](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=fr){target="_blank"}

### Améliorations de la sécurité {#security-8-9-1}

* Les comptes externes Snowflake prennent désormais en charge l’authentification OAuth2, fournissant des méthodes d’authentification modernes et sécurisées pour les connexions d’accès aux données fédérées. (NEO-87013) [En savoir plus](../config/external-accounts.md#snowflake-external-accounts)
* Les comptes externes de briques de données prennent désormais en charge l’authentification OAuth2 via le principal de service (flux d’informations d’identification client non interactif), fournissant des méthodes d’authentification sécurisées pour les connexions d’accès aux données fédérées. L’authentification OAuth2 interactive sera disponible dans une version ultérieure. (NEO-87422) [En savoir plus](../config/external-accounts.md#databricks-external-accounts)
* Correction de vulnérabilités d’accès aux fichiers de workflow en limitant les opérations aux répertoires autorisés, en empêchant l’accès non autorisé et l’exécution potentielle de code à distance. (NEO-88460)
* Ajout de contrôles d’URL FTP aux activités de code de JavaScript de workflow, limitant les connexions FTP sortantes aux adresses autorisées uniquement. (NEO-89083)

### Autres changements {#changes-8-9-1}

* Amélioration de la gestion de la mémoire de conteneur en implémentant la limitation automatique des workflows dans des conditions de mémoire élevée, avec des fonctionnalités intelligentes de redémarrage des workflows et des mécanismes de sécurisation de la mémoire pour les processus non critiques. (NEO-89041)
* Ajout de la prise en charge des fonctions de chiffrement et de déchiffrement asymétriques dans les workflows Campaign. (NEO-80257)
* Amélioration des performances de l’agent de réplication et de la résilience de la mémoire pour les chargements de données volumineux dans les déploiements FFDA. (NEO-88430)
* Les activités de workflow **[!UICONTROL Code SQL]** et **[!UICONTROL Gestion des données SQL]** ont été améliorées afin de mieux protéger les bases de données PostgreSQL et de garantir le bon fonctionnement de vos workflows lorsque du code SQL personnalisé est exécuté à partir de Campaign. Reportez-vous aux sections [Gestion des données SQL](../../automation/workflow/sql-data-management.md#important-notes) et [Code SQL](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) pour plus d’informations et de bonnes pratiques. (NEO-86540)


### Correctifs {#fixes-8-9-1}

* Correction d’un problème en raison duquel la structure de la base de données ne pouvait pas être mise à jour après les modifications de sysFilter. (NEO-93306)
* Correction d’un problème en raison duquel les données du rapport dynamique étaient manquantes après la migration. (NEO-92962)
* Correction d&#39;un problème en raison duquel le statut de la diffusion ne se mettait pas à jour correctement. (NEO-92908)
* Correction d’un problème lié à la restriction Catalogue d’utilisation FDA des briques de données . (NEO-92900)
* Correction d&#39;un problème qui entraînait des erreurs de mise en page HTML dans Outlook Windows Desktop. (NEO-92611)
* Correction d’un problème d’intégrité des données en raison duquel les clés primaires de diffusion étaient dupliquées sur l’instance mid après une mise à niveau. (NEO-92424)
* Correction d’un problème en raison duquel les liens ne pouvaient pas être désactivés dans la boîte de dialogue Tracking et images d’une diffusion. (NEO-92381)
* Correction d’un problème en raison duquel la fonction nms.subscription.RecipientSubscribe() ne fonctionnait pas pour l’abonnement en bloc. (NEO-92308)
* Correction d’un problème en raison duquel des fragments de diffusion étaient manquants après une mise à niveau. (NEO-92278)
* Correction d&#39;un problème dans le workflow de tracking en raison duquel les erreurs de statut en double et les erreurs de syntaxe SQL empêchaient la mise à jour des indicateurs de tracking. (NEO-92239)
* Correction d’un problème en raison duquel les libellés des champs d’énumération étaient manquants ou affichés incorrectement dans les listes créées via le workflow lors de l’utilisation des champs dbEnum. (NEO-91158)
* Correction d’un problème en raison duquel la boîte de dialogue de publication/dépublication RT ne se fermait pas et ne se figeait pas. (NEO-91038)
* Correction d&#39;un problème qui se produisait pour les destinataires avec le statut « Pris en compte par le fournisseur de services ». (NEO-90927)
* Correction d’un problème en raison duquel l’origine d’abonnement ou de désabonnement était manquante pour les liens d’opt-out. (NEO-90714)
* Correction d’un problème en raison duquel l’ajout de coupons échouait dans la préparation de la diffusion. (NEO-90547)
* Correction d’un problème en raison duquel le nombre d’insertions et de rejets n’était pas reflété précisément dans l’onglet Audit. (NEO-90318)
* Correction d’un problème de sécurité qui entraînait un déni de service de l’application. (NEO-89984)
* Correction d’un problème en raison duquel le PDF téléchargé du rapport Hotclick était endommagé. (NEO-89954)
* Correction d’une erreur SSL qui se produisait après une mise à niveau, provoquant un EOF inattendu lors de la lecture des erreurs. (NEO-89108)
* Correction d’un problème en raison duquel les données ne pouvaient pas être interrogées dans un schéma de données après une mise à niveau. (NEO-88663)
* Correction d’une erreur qui se produisait lors de la concaténation d’un champ « char » dans PostgreSQL 15. (NEO-88028)
* Correction d’un problème en raison duquel l’ordre des variables du modèle de diffusion changeait lors de l’enregistrement ou de la duplication du modèle. (NEO-87845)
* Correction d’un problème en raison duquel la création d’un schéma de bibliothèque de données entraînait le blocage de l’interface web. (NEO-87816)
* Correction d’un problème en raison duquel avec les ensembles de compléments dans l’activité Déduplication . (NEO-87711)
* Correction d’une demande de package d’installation sans dépendance X11. (NEO-87471)
* Correction d’un problème en raison duquel les codes segment ne pouvaient pas être utilisés dans les rapports dynamiques. (NEO-87276)
* Correction d’un problème en raison duquel les workflows étaient bloqués dans l’activité Mise à jour de données . (NEO-87252)
* Correction d’un problème en raison duquel BigQuery utilisait un fuseau horaire incorrect. (NEO-86622)
* Correction d’une erreur JavaScript qui se produisait lors de l’évaluation du script « mcSynch_mcExec1/jsReplicateUrl ». (NEO-86553)
* Correction d’un problème où des événements en double s’affichaient dans la table eventHisto en raison d’une méthode de calcul d’identifiant incorrecte. (NEO-86544)
* Correction d’un problème en raison duquel l’onglet Avancé ne s’affichait pas pour la notification push iOS lors de la copie. (NEO-86231)
* Correction d’un problème en raison duquel le workflow de réplication des tables de référence échouait dans la réplication du schéma nms:delivery. (NEO-85884)
* Correction d’un problème en raison duquel les erreurs de domaine null correspondant aux adresses MXIP s’affichaient dans les journaux d’erreurs lors de l’envoi de diffusions. (NEO-85238)
* Correction d’un problème en raison duquel les modèles de diffusion techniques n’étaient pas actualisés après les modifications apportées aux options. (NEO-84149)
* Correction d’une erreur dans le workflow de facturation prêt à l’emploi. (NEO-83624)
* Correction d&#39;un problème d&#39;exclusion des doublons basée uniquement sur la clé primaire des enregistrements ciblés. (NEO-82910)
* Correction d’incohérences dans les rapports de l’interface utilisateur web de Campaign où les statistiques de tracking affichaient des valeurs différentes par rapport à la console. (NEO-82339)
* Correction d&#39;un problème en raison duquel la date de dernière modification était modifiée même si l&#39;enregistrement ne devait pas être mis à jour dans l&#39;activité Mise à jour de données . (NEO-82002)
* Correction d’un problème en raison duquel l’ajout de nouveaux attributs dans une liste entraînait l’échec des workflows qui lisaient la liste. (NEO-80258)
* Correction d’un problème en raison duquel le rapport des indicateurs de tracking affichait des valeurs incorrectes pour des ouvertures distinctes. (NEO-79466)