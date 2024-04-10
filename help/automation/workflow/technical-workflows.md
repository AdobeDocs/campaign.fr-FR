---
product: campaign
title: Workflows techniques
description: En savoir plus sur les workflows techniques disponibles avec Campaign
feature: Workflows
role: User, Admin
exl-id: 2693856c-80b2-4e35-be8e-2a9760f8311f
source-git-commit: d4e28ddf6081881f02042416aa8214761ea42be9
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 98%

---

# Workflows techniques{#about-technical-workflows}

Adobe Campaign s’accompagne d’un ensemble de workflows techniques intégrés. Ils gèrent les opérations et traitements planifiés pour une exécution périodique sur le serveur. Ils vous permettent d&#39;effectuer la maintenance de la base de données, de transmettre les informations de tracking des diffusions ou de mettre en place des traitements provisoires des diffusions. Les workflows techniques sont configurés via le nœud **[!UICONTROL Administration > Exploitation > Workflows techniques]**.

![](assets/navtree.png)

Des modèles natifs sont disponibles pour créer des workflows techniques. Ils peuvent être paramétrés selon vos besoins.

Le sous-dossier **[!UICONTROL Processus de campagne]** centralise les workflows nécessaires à l&#39;exécution des traitements dans les opérations : notification des tâches, gestion des stocks, calcul des coûts, etc.

![](assets/campaign-processes-wf.png)


>[!NOTE]
>
>La liste des workflows techniques installés avec chaque module est disponible dans une [section dédiée](technical-workflows.md).

Vous pouvez créer d&#39;autres workflows techniques dans le noeud **[!UICONTROL Administration > Exploitation > Workflows techniques]** de l&#39;arborescence. Cette manipulation est toutefois réservée à des utilisateurs experts.

Les activités proposées sont les mêmes que pour les workflows de ciblage. [En savoir plus](targeting-workflows.md)

Les workflows présentés dans cette section sont installés avec les différents packages intégrés d’Adobe Campaign. Ces packages, ainsi que les workflows techniques associés, dépendent de votre contrat de licence.

Par défaut, les workflows techniques sont disponibles dans un sous-dossier du nœud suivant : **[!UICONTROL Administration]** > **[!UICONTROL Exploitation]** > **[!UICONTROL Workflows techniques]**.

Notez que les workflows techniques ne peuvent être démarrés et modifiés que par les opérateurs disposant de droits d&#39;administration.

>[!NOTE]
>
>Les workflows techniques associés au module Message Center module sont disponibles par défaut dans le nœud **[!UICONTROL Administration]** > **[!UICONTROL Exploitation]** > **[!UICONTROL Message Center]** > **[!UICONTROL Workflows techniques]**.

Découvrez comment surveiller les workflows techniques dans cette [section dédiée](monitor-technical-workflows.md).


## Liste des workflows techniques {#list-technical-workflows}

| Workflow technique | Package | Description |
|------|--------|-----------|
| **Gestion des alias** (aliasCleansing) | Installé par défaut | Ce workflow réalise l’uniformisation des valeurs des énumérations. Par défaut, il se déclenche tous les jours à 3h00. |
| **Facturation** (billing) | Installé par défaut | Ce workflow transmet par email le rapport d&#39;activité du système à l&#39;opérateur &#39;billing&#39;. Il est déclenché le 25 de chaque mois sur l&#39;instance Marketing. |
| **Traitements de la campagne** (operationMgt) | Installé par défaut | Ce workflow gère les traitements sur les opérations marketing (démarrage du ciblage, extraction des fichiers, etc.). Il crée également les workflows relatifs aux opérations récurrentes et périodiques. |
| **Collecter les données pour le service Carte thermique** (collectDataHeatMapService) | Installé par défaut | Ce workflow récupère les données requises par le service Carte thermique. |
| **Collecter les demandes d&#39;accès à des informations personnelles** (collectPrivacyRequests) | Règlement sur la protection des informations personnelles | Ce workflow génère les données du destinataire stockées dans Adobe Campaign et les met à disposition sur l’écran de la demande d’accès. |
| **Calcul des coûts** (budgetMgt) | Installé par défaut | Ce workflow lance le calcul des lignes de dépenses et des coûts sur les budgets, les plans, programmes, opérations, diffusions et tâches. |
| **Nettoyage de la base de données** (cleanup) | Installé par défaut | Ce workflow est le workflow d’entretien de la base de données : il procède aux différents calculs des statistiques et traitements, et supprime les données obsolètes de la base de données selon le paramétrage défini dans l’assistant de déploiement. Par défaut, il se déclenche tous les jours à 4 h 00. |
| **Nettoyage des utilisateurs LINE bloqués** (deleteBlockedLineUsersV2) | Canal LINE | Ce workflow assure la suppression des données des utilisateurs LINE V2 s’ils ont bloqué le compte officiel LINE pendant 180 jours. |
| **Supprimer les données des demandes d’accès à des informations personnelles** (deletePrivacyRequestsData) | Règlement sur la protection des informations personnelles | Ce workflow supprime les données du destinataire stockées dans Adobe Campaign. |
| **Indicateurs de diffusion** (deliveryIndicators) | Plateforme de Mid-sourcing | Ce workflow met à jour les indicateurs de tracking des diffusions. Par défaut, ce workflow se déclenche toutes les heures. |
| **Traitements sur le marketing distribué** (centralLocalMgt) | Marketing central/local (Marketing distribué) | Ce workflow exécute les traitements relatifs à l&#39;utilisation du module de marketing distribué. Il lance la création des opérations en local et gère les notifications relatives aux commandes et à la mise à disposition des kits d&#39;opération. |
| **Purge des événements** (webAnalyticsPurgeWebEvents) | Connecteurs Web Analytics | Ce workflow permet de supprimer du champ de la base tous les événements selon la période paramétrée dans le champ Durée de vie. |
| **Export d’audiences vers Adobe Experience Cloud** (exportSharedAudience) | Intégration avec Adobe Experience Cloud | Ce workflow permet d’exporter des audiences en tant qu’audiences/segments partagés. Ces audiences peuvent être exploitées dans les différentes solutions d’Adobe Experience Cloud que vous utilisez. |
| **Prévisionnel** (forecasting) | Diffusion | Ce workflow effectue l’analyse des diffusions enregistrées dans le calendrier prévisionnel (création des logs prévisionnels). Par défaut, il se déclenche tous les jours à 1h00. |
| **Calcul de l&#39;agrégat full (cube propositionrcp)** (agg_nmspropositionrcp_full) | Moteur d’offres (Interaction) | Ce workflow met à jour l&#39;agrégat Complet (full) du cube Proposition d&#39;offre. Par défaut, il se déclenche tous les jours à 6H00. Cet agrégat capture les dimensions suivantes : Canal, Diffusion, Offre marketing et Date. Le cube Proposition d’offre est ensuite utilisé pour générer des rapports basés sur les offres. En savoir plus sur les cubes dans  [cette section](../../v8/reporting/gs-cubes.md). |
| **Identification des contacts convertis** (webAnalyticsFindConverted) | Connecteurs Web Analytics | Ce workflow répertorie les visiteurs du site ayant concrétisé leur achat après une campagne de remarketing. Les données récupérées par ce workflow sont accessibles dans le rapport Efficacité du remarketing (voir cette page). |
| **Import d’audiences depuis Adobe Experience Cloud** (importSharedAudience) | Intégration avec Adobe Experience Cloud | Ce workflow permet d’importer dans Adobe Campaign des audiences/segments provenant de différentes solutions d’Adobe Experience Cloud. |
| **Traitements sur les diffusions dans les opérations** (deliveryMgt) | Installé par défaut | Ce workflow démarre les diffusions validées et lance les post-traitements du prestataire pour une diffusion externe. Il envoie également des notifications de validation et des rappels. |
| **Traitements sur les prestataires** (supplierMgt) | Installé par défaut | Ce workflow démarre les traitements du prestataire (e-mail au routeur et post-traitement) une fois que les diffusions ont été validées. |
| **Migration du MID vers l’identifiant utilisateur Line** (MIDToUserIDMigration) | Canal LINE | Ce workflow génère les ID des utilisateurs LINE V2 pour la migration de LINE V1 vers LINE V2. |
| **Message Center &lt;nom_compte_externe>** (mcSynch_&lt;nom_compte_externe>) | Contrôle des messages transactionnels (Message Center - Pilotage) | Ce workflow : <ul><li>récupère la liste des événements traités par la ou les opérations,</li><li>se synchronise avec la table NmsBroadLogMsg afin de récupérer les qualifications des messages de diffusion,</li><li>récupère les logs de diffusion d&#39;événements dès que la synchronisation avec la table NmsBroadLogMsg est terminée,</li><li>se synchronise avec la table NmsTrackingUrl afin de récupérer le tracking des URL de diffusion,</li><li>récupère les URL de tracking des événements dès que la synchronisation avec la table NmsTrackingUrl est terminée,</li><li>permet de récupérer toutes les adresses email mises en quarantaine toutes les trois heures après l&#39;envoi d&#39;une diffusion.</li></ul> |
| **Calcul de l&#39;agrégat intégral de MessageCenter** (agg_messageCenter_full) | Contrôle des messages transactionnels (Message Center - Pilotage) | Ce workflow met à jour l’agrégat intégral du cube Message Center. Il est déclenché tous les jours à 3h du matin par défaut. Cet agrégat capture les dimensions suivantes : Canal, Date, Statut et Type d&#39;événement. Le cube Message Center est ensuite utilisé pour générer des rapports basés sur des événements. Pour plus d&#39;informations sur les cubes, consultez |
| **Mid-sourcing (compteurs des diffusions)** (defaultMidSourcingDlv) | Emission vers Mid-sourcing | Ce workflow collecte les informations de comptage des diffusions sur le serveur de midsourcing. Les informations de comptage comprennent les indicateurs généraux de diffusion tels que le nombre de diffusions envoyées, etc. Les informations de tracking comme les ouvertures ne sont pas incluses. Par défaut, il se déclenche toutes les dix minutes. |
| **Mid-sourcing (logs de diffusion)** (defaultMidSourcingLog) | Emission vers Mid-sourcing | Ce workflow collecte les logs des diffusions sur le serveur de mid-sourcing. Par défaut, il se déclenche toutes les heures. |
| **Gestion des opt-out NMAC** (mobileAppOptOutMgt) | Canal Des Applications Mobiles (Push) | Ce workflow met à jour les désinscriptions aux notifications sur les appareils mobiles. Par défaut, il se déclenche toutes les 6 heures entre 1 h 00 et minuit. |
| **Notification d&#39;offre** (offerMgt) | Installé par défaut | Toutes les heures, ce workflow déploie les offres validées sur l&#39;environnement en ligne, ainsi que toutes les catégories contenues dans le catalogue d&#39;offres. |
| **Nettoyage des workflows en pause** (cleanupPausedWorkflows) | Installé par défaut | Ce workflow analyse les workflows en pause dont le niveau de priorité est défini sur normal et déclenche des avertissements et des notifications lorsqu&#39;ils sont en pause depuis trop longtemps. Après un mois, les workflows techniques en pause sont arrêtés de manière inconditionnelle. Par défaut, ce workflow est déclenché tous les lundis à 5h00. Pour plus d’informations, voir [Gérer les workflows en pause](monitor-workflow-execution.md#handling-of-paused-workflows). |
| **Nettoyage des demandes d&#39;accès à des informations personnelles** (cleanupPrivacyRequests) | Règlement sur la protection des informations personnelles | Ce workflow supprime les fichiers de demande d’accès qui ont plus de 90 jours. |
| **Traitement des événements batch** (batchEventsProcessing) | Exécution des messages transactionnels (Message Center - Exécution) | Ce workflow permet de répartir les événements batch dans une file d&#39;attente avant qu&#39;ils ne soient associés à un modèle de message. |
| **Traitement des événements temps réel** (rtEventsProcessing) | Exécution des messages transactionnels (Message Center - Exécution) | Ce workflow permet de répartir les événements temps réel dans une file d&#39;attente avant qu&#39;ils ne soient associés à un modèle de message. |
| **Synchronisation des propositions** (propositionSynch) | Contrôle du moteur d’offres avec l’instance d’exécution | Ce workflow synchronise les propositions entre les instances marketing et d’exécution utilisées pour les interactions. |
| **Récupération des événements web** (webAnalyticsGetWebEvents) | Connecteurs Web Analytics | Toutes les heures, ce workflow télécharge les segments portant sur le comportement des internautes sur un site donné, les inclut dans la base de données Adobe Campaign et lance le workflow de re-marketing. |
| **Agrégats du reporting** (reportingAggregates) | Diffusion | Ce workflow met à jour les agrégats utilisés dans les rapports. Par défaut, il se déclenche tous les jours à 2H00. |
| **Envoi des indicateurs et des attributs de campagne** (webAnalyticsSendMetrics) | Connecteurs Web Analytics | Ce workflow permet d&#39;envoyer les indicateurs des campagnes par e-mail d&#39;Adobe Campaign vers Adobe Experience Cloud Suite via le connecteur Adobe® Analytics. Les indicateurs concernés sont les suivants : Envoyé (iSent), Nombre total d&#39;ouvertures (iTotalRecipientOpen), Nombre total de destinataires ayant cliqué (iTotalRecipientClick), Erreurs (iError), Opt-Out (opt-out) (iOptOut). |
| **Stock : commandes et alertes** (stockMgt) | Installé par défaut | Ce workflow lance le calcul des stocks sur les lignes de commande et gère les seuils d&#39;alerte. |
| **Synchroniser les applications mobiles à partir de la collecte de données Adobe Experience Platform** (syncWithLaunch) | Installé par défaut, à partir de la version 8.5 | Ce workflow synchronise automatiquement les propriétés mobiles avec Adobe Campaign à partir de la collecte de données. |
| **Suivi** (suivi) | Installé par défaut | Ce workflow réalise la récupération et la consolidation des informations de tracking. Il assure également le re-calcul des statistiques de tracking et de diffusions, notamment celles utilisées par les workflows d&#39;archivage de Message Center. Par défaut, il se déclenche toutes les heures. |
| **Mise à jour du statut des événements** (updateEventsStatus) | Exécution des messages transactionnels (Message Center - Exécution) | Ce workflow permet d&#39;attribuer un statut à l&#39;événement. Les statuts d&#39;un événement sont les suivants :<ul><li>En attente : l&#39;événement se trouve dans la file d&#39;attente. Aucun modèle de message ne lui a encore été associé.</li><li>En attente de diffusion : l&#39;événement est dans la file d&#39;attente, un modèle de message lui a été associé et il est en cours de traitement par la diffusion.</li><li>Envoyé : ce statut est copié depuis les logs de diffusion. Il signifie que la diffusion a été envoyée.</li><li>Ignoré par la diffusion : ce statut est copié depuis les logs de diffusion. Il signifie que la diffusion a été ignorée.</li><li>Erreur de diffusion : ce statut est copié depuis les logs de diffusion. Il signifie que la diffusion a échoué.</li><li>Evénement non pris en charge : l&#39;association de l&#39;événement à un modèle de message a échoué. L&#39;événement ne sera pas retraité.</li></ul> |
| **Mettre à jour pour la délivrabilité** (deliverabilityUpdate) | Installé par défaut | Une fois le package Supervision de la délivrabilité (Email Deliverability) installé, ce workflow s’exécute de nuit et gère les règles de qualification des e-mails rejetés, ainsi que la liste des domaines et des MX. Pour ce faire, le port HTTPS doit être ouvert sur la plateforme. |
