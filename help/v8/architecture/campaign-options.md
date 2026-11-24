---
title: Options de Campaign
description: Découvrez les options de Campaign, où elles sont stockées et comment utiliser les options documentées pour Campaign v8
feature: Architecture
role: Admin, Developer
level: Intermediate
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: bae31391-3416-5fbd-bc4b-2cdcae2922db
    internal-label: Architecture
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 36111995a9a550d5089107bbc1f734c204db8aff
workflow-type: tm+mt
source-wordcount: '2836'
ht-degree: 4%
---
# Options de Campaign {#campaign-options}

Les options sont des paramètres qui contrôlent le comportement de votre instance Campaign, par exemple la limite de taille par défaut des images dans les e-mails, le nombre de workflows qui s’exécutent en même temps ou le fournisseur de routage par défaut des modèles de diffusion. Certaines options sont intégrées et d’autres sont créées si nécessaire. Les options disponibles dépendent des packages installés sur votre instance. En savoir plus sur les [packages natifs](built-in-packages.md).

>[!CAUTION]
>
>Ne modifiez que les options documentées dans la documentation de Campaign, et uniquement comme décrit. Les options non documentées sont internes et ne doivent pas être modifiées. La modification des options est réservée à des utilisateurs experts.

## Emplacement de stockage des options {#where-options-are-stored}

Les options sont stockées dans la base de données Campaign, dans la table **xtkOption** (schéma **xtk:option**). Dans l&#39;Explorateur Campaign, ils sont disponibles sous **[!UICONTROL Administration]** > **[!UICONTROL Plateforme]** > **[!UICONTROL Options]**. Dans l’interface utilisateur web de Campaign, ils sont disponibles sous **[!UICONTROL Administration]** > **[!UICONTROL Options]**. Les deux listes sont identiques. En savoir plus dans la section [Configurer les options de Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/options){target="_blank"}.

## Utilisation des options {#use-options}

1. Dans l&#39;Explorateur Campaign, accédez à **[!UICONTROL Administration]** > **[!UICONTROL Plateforme]** > **[!UICONTROL Options]**.
1. Sélectionnez l’option puis mettez à jour sa valeur. Si l’option n’existe pas, créez-la avec le nom exact donné dans la documentation.
1. Définissez une valeur du type attendu par la documentation. Il peut s’agir, par exemple, d’une option texte pour la date de synchronisation du CRM ou d’une option entière pour le délai de redémarrage du workflow.

Vous pouvez également créer vos propres options, par exemple pour stocker les données intermédiaires d’un workflow. Saisissez un nom, sélectionnez le type de données et définissez la valeur. En savoir plus dans la section [Configurer les options de Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/options#create){target="_blank"}.

Certaines options contiennent des informations d’identification. Chiffrez les secrets avec la fonction `cryptString`, comme décrit dans [Utilisation des pages de destination de Campaign et Adobe Experience Platform](../connect/ac-aep-landing-pages.md). Lorsque vous faites pivoter les informations d’identification, faites également pivoter celles stockées dans les options . En savoir plus dans le [guide de rotation des informations d’identification](../../technotes/security/credential-rotation-guide.md#ac-options-credentials).

## Utilisation des options dans les workflows et la personnalisation {#use-options-in-processes}

Vous pouvez lire et écrire des valeurs d’option à partir du code JavaScript, de la personnalisation et des requêtes.

* **Code JavaScript**, tel qu’une activité de workflow de code JavaScript : `getOption('OptionName')` renvoie la valeur d’une option et `setOption('OptionName', value, 'description')` la définit. Par exemple, `getOption('IMS_ORG_ID')`. En savoir plus dans [getOption](../../campaign-api/f-getoption.md) et [setOption](../../campaign-api/f-setoption.md).
* **Personnalisation de la diffusion** : `<%@ include option='OptionName' %>` insère la valeur d&#39;une option. Par exemple, `<%@ include option='NmsServer_URL' %>` inclut l’URL du serveur dans un lien vers une application web dans un message LINE. En savoir plus sur la section [Envoyer des messages LINE directs avec Adobe Campaign](../send/line/line.md).
* **Éditeur de requêtes** : saisissez `$(options:OPTION_NAME)` dans le champ **Valeur** pour utiliser la valeur d’une option. En savoir plus sur les [requêtes de conception](../start/design-queries.md).

## Options disponibles {#available-options}

Les tableaux ci-dessous répertorient les options disponibles dans Campaign v8, regroupées par zone. Lorsqu’une autre page de la documentation décrit une option, le tableau fournit des liens vers celle-ci.

### Diffusions {#delivery-options}

Ces options contrôlent la manière dont les diffusions sont préparées et envoyées. Ils couvrent les limites d’image et de pièce jointe, le fournisseur de routage par défaut, le seuil de partage de midsourcing, le script de tracking des ouvertures, l’URL du serveur public, la validité de la diffusion, la gestion des doublons et des diffusions retardées, ainsi que les codes à barres. En savoir plus sur [Ajout de fichiers](../send/attaching-files.md), [Paramètres d’e-mail](../send/email-parameters.md), [Bonnes pratiques de diffusion](../start/delivery-best-practices.md), [Prise en main de l’architecture de Campaign](architecture.md#split), [Conseils concernant les pixels de suivi des e-mails](../start/cnil-pixel-tracking.md) et [Envoi direct de messages LINE](../send/line/line.md).

| Option | Description |
|---|---|
| NmsDelivery_MaxDownloadedImageSize | Taille maximale, en octets, d’une image téléchargée à partir d’une URL personnalisée et jointe à un email. La valeur par défaut est de 100 000 octets (100 Ko). [En savoir plus](../send/attaching-files.md) |
| NmsDelivery_MaxRecommendedAttachments | Nombre maximal de pièces jointes dans un e-mail ou un modèle d’e-mail transactionnel avant l’affichage d’un avertissement. La valeur par défaut est 1. [En savoir plus](../send/attaching-files.md) |
| NmsEmail_DefaultErrorAddr | Adresse e-mail d&#39;erreur par défaut de l&#39;instance, utilisée lorsque la diffusion laisse l&#39;adresse d&#39;erreur vide. [En savoir plus](../send/email-parameters.md) |
| XtkEmail_Characters | Caractères valides pour une adresse email. [En savoir plus](../start/delivery-best-practices.md) |
| NmsBroadcast_DefaultProvider | Fournisseur de routage par défaut des nouveaux modèles de diffusion. Définissez-la sur le nom d’un compte externe partagé pour utiliser la diffusion partagée par défaut. [En savoir plus](architecture.md#split) |
| NmsDelivery_MultiMidSplitThreshold | Taille à partir de laquelle une diffusion est répartie entre plusieurs instances de mid-sourcing. La valeur par défaut est de 100 000. [En savoir plus](architecture.md#split) |
| NmsTracking_OpenFormula | Script de calcul de l’URL de tracking des ouvertures. Définissez une option par objectif de pixel. [En savoir plus](../start/cnil-pixel-tracking.md) |
| NmsServer_URL | URL de base du serveur applicatif web public. Utilisé, par exemple, pour inclure un lien d’application web dans un message LINE. [En savoir plus](../send/line/line.md) |
| NmsBroadcast_MsgValidityDuration | Période de validité par défaut d’une diffusion, en secondes. |
| NmsBroadcast_RemoveDuplicatesRecipients | Définissez-le sur 1 pour ignorer automatiquement les destinataires en double. |
| NmsDelivery_ImageServerTimeout | Timeout, en secondes, pour obtenir une réponse du serveur lors de la récupération d&#39;une image téléchargée à partir d&#39;une URL personnalisée et jointe à un email. Si le délai d’expiration est dépassé, le message ne peut pas être envoyé. La valeur par défaut est de 60 secondes. |
| NmsDeliveryWizard_ShowDeliveryWeight | Affiche le poids du message dans l&#39;assistant de diffusion. |
| NmsMTA_Alert_Delay | Délai, en minutes, au delà duquel une diffusion est considérée comme retardée. La valeur par défaut est de 30 minutes. |
| NmsServer_MirrorPageUrl | URL du serveur de pages miroir. Il s’agit de la valeur par défaut des diffusions e-mail lorsque la définition de routage ne spécifie aucune URL. Par défaut, elle est identique à l’URL du serveur de tracking. |
| XtkBarcode_SpecialChar | Active ou désactive la prise en charge des caractères spéciaux pour les codes à barres Code128. |
| XtkSecurity_Restrict_EditXML | Ajoutez-la avec la valeur 0 pour désactiver l&#39;édition du code XML des diffusions (Editer XML source ou Ctrl+F4). |
| NMS_ActivateOwnerConfirmation | Définissez-la sur 1 afin que l’opérateur ou l’opératrice en charge de la diffusion puisse confirmer l’envoi, lorsqu’un opérateur ou un groupe spécifique est désigné pour démarrer la diffusion. Définissez-le sur 0 pour le désactiver : seul l’opérateur ou le groupe désigné, ou un administrateur, peut alors confirmer l’envoi. |
| NmsDelivery_senderAddressMask | Liste séparée par des virgules des adresses expéditeur autorisées dans le champ E-mail de l’expéditeur des diffusions par e-mail. Lorsque l’option comporte une valeur, le champ devient une liste déroulante. La restriction est globale : elle s&#39;applique à chaque marque et modèle de diffusion et ne prend en charge que les adresses statiques. [En savoir plus](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/options#restrict-sender-address){target="_blank"} |

### Campagnes et workflows {#campaign-workflow-options}

Ces options contrôlent l’exécution des campagnes et des workflows. Ils couvrent la confirmation du propriétaire d’un envoi, le nombre de traitements traités en même temps, ainsi que la vérification et le redémarrage automatique des workflows. Ils couvrent également la protection des activités SQL, la validité par défaut de la campagne et le logo des rapports exportés. En savoir plus sur [les diffusions de campagnes marketing](../../automation/campaigns/marketing-campaign-deliveries.md), [les bonnes pratiques relatives aux workflows](../../automation/workflow/workflow-best-practices.md), [la surveillance de l&#39;exécution des workflows](../../automation/workflow/monitor-workflow-execution.md), [les propriétés des workflows](../../automation/workflow/workflow-properties.md) et [le code SQL et le code JavaScript](../../automation/workflow/sql-code-and-javascript-code.md#important-notes).

| Option | Description |
|---|---|
| NmsCampaign_Activate_OwnerConfirmation | Créez-la et définissez-la sur 1 afin que le propriétaire de la campagne puisse confirmer l’envoi, même si des réviseurs sont définis. Définissez-le sur 0 pour le désactiver. [En savoir plus](../../automation/campaigns/marketing-campaign-deliveries.md) |
| NmsOperation_LimitConcurrency | Nombre maximum de traitements de diffusion, de workflow, d’hypothèses et de simulation qu’une campagne peut traiter en même temps. La valeur par défaut est 10. [En savoir plus](../../automation/workflow/workflow-best-practices.md) |
| NmsServer_PausedWorkflowPeriod | Nombre de jours entre deux vérifications pour les workflows en pause. [En savoir plus](../../automation/workflow/monitor-workflow-execution.md) |
| XtkWorkflow_WatchdogRestartTimerTimeout | Créez-le en tant qu’option de nombre entier pour modifier l’intervalle de 30 secondes auquel les workflows sont vérifiés et redémarrés automatiquement. [En savoir plus](../../automation/workflow/workflow-properties.md) |
| XtkSecurity_FeatureFlag_SqlSensitive | Définissez-le sur 0 pour désactiver la protection des activités de code SQL contre les méthodes SQL bloquées. [En savoir plus](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) |
| XtkSecurity_SqlSensitive_Methods | Liste des méthodes SQL bloquées ou mises en garde par les activités SQL. [En savoir plus](../../automation/workflow/sql-code-and-javascript-code.md#important-notes) |
| NmsOperation_Duration | Période de validité par défaut d’une campagne, en secondes. |
| NmsOperation_TimeRange | Période temporelle des conditions de ciblage et d&#39;extraction en mode planifié. |
| NmsOperation_OperationMgtDebug | Définissez-le sur 1 pour consigner les informations d’exécution du workflow technique operationMgt dans les journaux d’audit des workflows. |
| NmsOperation_DeliveryPreparationWindow | Nombre de jours au-dessus duquel les diffusions présentant un statut incohérent sont exclues du décompte des diffusions en cours d&#39;exécution par le workflow technique operationMgt. La valeur par défaut est 7. |
| Workflow_AnalysisThreshold | Nombre d&#39;enregistrements modifiés à partir duquel une mise à jour des statistiques sera déclenchée automatiquement |
| XtkReport_Logo | Logo affiché dans le coin supérieur droit des rapports exportés. |

### Paramètres par défaut des e-mails {#email-default-options}

Ces options définissent les adresses et libellés d’expéditeur et de réponse par défaut de vos e-mails. Campaign les utilise lorsqu&#39;une diffusion laisse le champ correspondant vide. En savoir plus sur les [paramètres d’e-mail](../send/email-parameters.md) et [Utilisation de modèles de diffusion](../send/create-templates.md).

| Option | Description |
|---|---|
| NmsEmail_DefaultFromAddr | Adresse de l’expéditeur par défaut de l’instance, utilisée lorsque la diffusion la laisse vide. |
| NmsEmail_FromName | Libellé De par défaut de l&#39;instance, utilisé lorsque la diffusion la laisse vide. |
| NmsEmail_DefaultReplyToAddr | Adresse de réponse par défaut de l’instance, utilisée lorsque la diffusion la laisse vide. |
| NmsEmail_ReplyToName | Libellé Réponse par défaut de l’instance, utilisé lorsque la diffusion la laisse vide. |
| NmsEmail_DefaultErrorAddr | Adresse d’erreur par défaut de l’instance, utilisée lorsque la diffusion la laisse vide. [En savoir plus](../send/email-parameters.md) |
| NmsDelivery_FromAddressMasks | Syntaxe de l&#39;adresse Expéditeur utilisée pour l&#39;envoi du message. |
| NmsDelivery_ErrorAddressMasks | Syntaxe de l&#39;adresse d&#39;erreur lors de la réponse à un message. |
| NmsEmail_ExpOrganization | Nom courant de votre organisation, utilisé dans certains messages d’avertissement affichés aux destinataires. |

### Erreurs soft et mise en quarantaine {#error-options}

Ces options définissent le moment où un destinataire est mis en quarantaine à la suite d&#39;erreurs soft, qui sont des échecs de diffusion temporaires. En savoir plus sur la [gestion des quarantaines dans Campaign](../send/quarantines.md#soft-error-management) et les [diffusions en échec dans Campaign](../send/delivery-failures.md#retries).

| Option | Description |
|---|---|
| NmsNPAI_EmailMaxError | Nombre maximum d&#39;erreurs soft acceptées sur le canal email avant que le destinataire ne soit mis en quarantaine. |
| NmsNPAI_EmailSignificativeErrorDelay | Temps minimum qui doit s’écouler après la précédente erreur soft sur le canal email avant qu’une nouvelle erreur soft ne soit prise en compte. |
| NmsNPAI_MobileMaxError | Nombre maximum d&#39;erreurs soft acceptées sur le canal mobile avant que le destinataire ne soit mis en quarantaine. |
| NmsNPAI_MobileSignificativeErrorDelay | Durée minimale devant s’écouler après la précédente erreur soft sur le canal mobile avant qu’une nouvelle erreur soft ne soit prise en compte. |

### Canaux {#channel-options}

Ces options définissent l’adresse d’expéditeur du publipostage direct, les paramètres des canaux LINE et SMS, ainsi que les adresses de transfert autorisées des e-mails entrants. Pour en savoir plus, consultez les sections [Envoyer des courriers avec Adobe Campaign](../send/direct-mail.md), [Envoyer des messages LINE directs avec Adobe Campaign](../send/line/line.md) et [Envoyer des SMS avec Adobe Campaign](../send/sms/sms.md).

| Option | Description |
|---|---|
| NmsPaper_SenderLine1, NmsPaper_SenderLine3, NmsPaper_SenderLine4, NmsPaper_SenderLine6, NmsPaper_SenderLine7 | Lignes 1, 3, 4, 6 et 7 de l’adresse de l’expéditeur des diffusions de publipostage direct. |
| NmsLine_AESKey | Clé AES utilisée par le servlet lineImage pour coder les URL dans le canal LINE. |
| NmsLine_MessageCenterURL | URL du serveur Message Center utilisée pour envoyer des messages de bienvenue dans le canal LINE. |
| NmsSMS_Priority | Priorité des SMS envoyés, transmise à la passerelle SMS. |
| NmsInmail_AllowlistEmails | Adresses email de transfert autorisées du module de traitement des mails entrants, séparées par des virgules. Utilisez * pour autoriser toutes les adresses. |

### Seuils Message Center {#message-center-options}

Ces options définissent les seuils qui déclenchent un avertissement ou une alerte lorsque le traitement des événements temps réel, qui déclenchent les messages transactionnels, se dégrade. Chaque mesure comporte un seuil d’avertissement et un seuil d’alerte. Le nom de l’option se termine par Warning ou Alert, par exemple MC_RtEventErrorWarning et MC_RtEventErrorAlert. En savoir plus sur les [paramètres des messages transactionnels de Campaign](../send/transactional.md) et [paramètres des messages transactionnels de Campaign](../config/transactional-msg-settings.md).

| Préfixe du nom de l’option | Mesure |
|---|---|
| MC_RtEventAvgDeliveryTime | Temps moyen d’envoi des événements temps réel. |
| MC_RtEventAvgProcessTime | Temps moyen de traitement des événements temps réel. |
| MC_RtEventAvgQueueTime | Temps moyen des événements temps réel dans la file. |
| MC_RtEventAvgQueue | Nombre moyen d’événements temps réel en file. |
| MC_RtEventMaxQueue | Nombre maximum d’événements temps réel en file. |
| MC_RtEventMinQueue | Nombre minimum d’événements temps réel en file. |
| MC_RtEventQueue | File d’événements en temps réel en attente. Le seuil d’alerte est la condition critique. |
| MC_RtEventError | Erreurs de traitement des événements temps réel. |
| MC_RtEventThroughput | Débit des événements temps réel. |

### Conservation des données et base de données {#database-options}

Le workflow de nettoyage purge les anciens enregistrements pour empêcher la croissance de la base de données. Ces options définissent la durée pendant laquelle Campaign conserve chaque type de données. Une option de délai de purge est créée automatiquement lorsque vous modifiez le délai dans l’interface. Si vous le modifiez dans la liste des options, exprimez la valeur en secondes. En savoir plus sur l’[architecture générale](general-architecture.md) et les [instructions de sécurité](../config/security.md#consent).

| Option | Description |
|---|---|
| NmsCleanup_BroadLogPurgeDelay | Délai après lequel les logs de diffusion (broadlogs) sont effacés. |
| NmsCleanup_TrackingLogPurgeDelay | Délai après lequel les logs de tracking sont effacés. |
| NmsCleanup_TrackingStatPurgeDelay | Délai après lequel les statistiques de tracking sont effacées. |
| NmsCleanup_EventPurgeDelay | Délai après lequel les événements sont effacés. |
| NmsCleanup_EventHistoPurgeDelay | Délai après lequel l’historique des événements est effacé. |
| NmsCleanup_EventStatPurgeDelay | Délai après lequel les statistiques des événements sont effacées. |
| NmsCleanup_PropositionPurgeDelay | Délai au delà duquel les propositions sont effacées. |
| NmsCleanup_QuarantineMailboxFull | Délai après lequel les quarantaines sont effacées. |
| NmsCleanup_RecycledDeliveryPurgeDelay | Délai après lequel les diffusions recyclées sont effacées. |
| NmsCleanup_RejectsPurgeDelay | Délai après lequel les rejets sont effacés. |
| NmsCleanup_VisitorPurgeDelay | Délai après lequel les visiteurs sont effacés. |
| NmsCleanup_WorkflowResultPurgeDelay | Délai après lequel les résultats du workflow sont effacés. |
| XtkCleanup_NoStats | Définissez-le sur 1 afin que le workflow de nettoyage ne mette pas à jour les statistiques de la base de données. |
| WdbcKillSessionPolicy | Comportement de l’arrêt inconditionnel des workflows sur PostgreSQL. 0 (par défaut) : arrête le processus du workflow sans impact sur la base de données. 1 : arrête le processus et annule la requête (pg_cancel_backend). 2 : arrête le processus et termine la requête (pg_terminate_backend). |
| XtkSequence_AutoGeneration | S’applique aux schémas personnalisés créés après la définition de cette option, avec autopk=« true » et aucun attribut pkSequence : Campaign génère automatiquement la séquence. |

### Personnalisation de Message Center {#message-center-customization}

Ces options vous permettent de personnaliser la manière dont Campaign enrichit et achemine les événements temps réel et par lots. En savoir plus sur les [paramètres des messages transactionnels de Campaign](../send/transactional.md) et [paramètres des messages transactionnels de Campaign](../config/transactional-msg-settings.md).

| Option | Description |
|---|---|
| MC_EnrichissementCustomJs | Bibliothèque JavaScript qui enrichit les événements. Il doit implémenter enrichRtEvents(aiEventId) pour les événements en temps réel et enrichBatchEvents(aiEventId) pour les événements par lots. Les deux fonctions enrichissent les événements et les enregistrent dans la base de données. |
| MC_RoutingCustomJs | Bibliothèque JavaScript qui achemine les événements. Il doit implémenter dispatchRtEvent(iEventId) et dispatchBatchEvent(iEventId), qui renvoient le nom interne du message transactionnel sélectionné pour l’événement en temps réel ou par lots. |
| NmsMessageCenter_RoutingBatchSize | Taille des groupes utilisés pour le routage des événements. |
| NmsTracking_RT_ClickFormula, NmsTracking_RT_OpenFormula | Formules utilisées pour le suivi des clics et des ouvertures des diffusions en temps réel (RT) lorsque le branding est activé. Ils sont configurés sur l’instance de pilotage RT. [En savoir plus](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/branding/branding-configure){target="_blank"} |
| Branding_RT_ListXtkOptions_toPublish | Liste des options, séparées par des virgules, qui contiennent vos formules de tracking personnalisées, afin que les diffusions RT puissent les appliquer. [En savoir plus](https://experienceleague.adobe.com/en/docs/campaign-web/v8/administration/branding/branding-configure){target="_blank"} |

### Interaction (gestion des offres) {#interaction-options}

Ces options s’appliquent à Campaign Interaction, le module de gestion des offres. Ils contrôlent la manière dont les propositions sont écrites et dont les instances de pilotage et d&#39;exécution sont synchronisées. En savoir plus dans [Interaction de Campaign - Gestion des offres](../interaction/interaction.md) et dans les [options de maintenance](../interaction/interaction-architecture.md#maintenance-options) de l&#39;architecture d&#39;Interaction.

| Option | Description |
|---|---|
| NmsInteraction_UseDaemon | Définissez-la sur 1 pour activer l’écriture asynchrone des propositions, ou sur 0 pour la désactiver. |
| NmsInteraction_MapWorkflowId | Liste de tous les workflows de synchronisation générés. Option de maintenance de l’instance de pilotage. |
| NmsExecutionInstanceId | Identifiant de l&#39;instance d&#39;exécution. Disponible sur les instances d&#39;exécution. |

Les options suivantes sont également des options de maintenance de l&#39;instance de pilotage :

* **`NmsInteraction_LastOfferEnvSynch_<offerEnvId>_<executionInstanceId>`** : date de dernière synchronisation d&#39;un environnement sur une instance donnée.
* **`NmsInteraction_LastPropositionSynch_<propositionSchema>_<executionInstanceIdSource>_<executionInstanceIdTarget>`** : date de dernière synchronisation des propositions d&#39;un schéma d&#39;une instance vers une autre.

>[!CAUTION]
>
>N’utilisez les options de maintenance que pour des cas de maintenance spécifiques.

Les options suivantes s’appliquent aux coupons, qui ne sont pas disponibles dans les déploiements Enterprise (FFDA). En savoir plus sur les [Coupons personnalisés](../send/personalized-coupons.md).

| Option | Description |
|---|---|
| NmsModule_CouponsEnabled | Active les coupons. |
| NmsCoupons_MaxPerTransact | Nombre de coupons mis à jour par transaction SQL. |

### Demandes d&#39;accès à des informations personnelles {#privacy-options}

Ces options contrôlent la manière dont Campaign traite les demandes d’accès à des informations personnelles, telles que la confirmation des suppressions, le nombre d’erreurs autorisées et la durée de conservation des données de la demande. En savoir plus sur la section [Gérer les demandes d’accès à des informations personnelles dans Campaign](../start/privacy.md).

| Option | Description |
|---|---|
| Privacy_Request_ConfirmDeletePending | Définissez-la sur 1 pour confirmer manuellement chaque suppression dans l’interface lors d’une seconde étape. Dans le cas contraire, les données sont supprimées sans confirmation. |
| Privacy_Request_ConfirmDeletePendingDelay | Délai au delà duquel une demande en attente de confirmation de suppression est annulée. |
| Privacy_Request_MaxErrorAllowed | Nombre maximum d’erreurs autorisées lors du traitement ou de la suppression d’une demande d’accès à des informations personnelles. |
| Privacy_Request_PurgeDelay | Délai entre la création d’une demande dans la file et la suppression de ses données. |
| realtimeReporting_collectPII | Choix de l’accord relatif aux informations d’identification personnelle pour les rapports dynamiques. La valeur 1 correspond à Me demander plus tard, 2 à Refuser et 3 à Accepter. [En savoir plus](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reporting/dynamic-reporting/pii-agreement){target="_blank"} |

### Journal d’audit {#audit-trail-options}

Le journal d&#39;audit enregistre les modifications apportées aux entités de Campaign. Utilisez ces options pour l&#39;activer ou le désactiver pour une entité, par exemple pour économiser de l&#39;espace dans la base de données. Définissez la valeur sur 1 pour activer le journal d’audit et sur 0 pour le désactiver. En savoir plus sur le [journal d’audit](../reporting/audit-trail.md#enable-disable-audit-trail).

| Option | Entité contrôlée |
|---|---|
| XtkAudit_Workflows | Workflows |
| XtkAudit_DataSchema | Schémas |
| XtkAudit_Option | Options |
| XtkAudit_Delivery | Diffusions |
| XtkAudit_ExtAccount | Comptes externes |
| XtkAudit_DeliveryMapping | Mappages de diffusion |
| XtkAudit_WebApp | Applications web |
| XtkAudit_Offer | Offres |
| XtkAudit_Operator | Opérateurs |
| XtkAudit_Enable_All | Toutes les entités |

### Intégrations et questionnaires {#integration-options}

Ces options stockent les paramètres des intégrations et des questionnaires : les informations d&#39;identification Adobe Developer Console pour les landing pages, la date de dernière synchronisation de l&#39;activité Connecteur CRM et la sauvegarde par défaut des réponses au questionnaire. En savoir plus dans [Mise à jour des profils Adobe Experience Platform à partir des pages de destination Adobe Campaign](../connect/ac-aep-landing-pages.md), [Synchronisation des données des connecteurs CRM](../connect/crm-data-sync.md) et [Gestion des réponses](../dev/surveys/managing-answers.md).

| Option | Description |
|---|---|
| IMS_CLIENT_ID, IMS_CLIENT_SECRET, IMS_ORG_ID, IMS_CLIENT_API_KEY | Informations d’identification Adobe Developer Console utilisées pour les pages de destination avec Adobe Experience Platform. [En savoir plus](../connect/ac-aep-landing-pages.md) |
| LASTIMPORT_ suivi du nom interne de l&#39;instance et du nom de l&#39;activité | Date de la dernière synchronisation de l&#39;activité Connecteur CRM générique. Créez-le manuellement en tant qu&#39;option de texte, au format `yyyy/MM/dd hh:mm:ss`. [En savoir plus](../connect/crm-data-sync.md) |
| NmsWebApp_XmlBackup | Créez-la et définissez-la sur 1 pour enregistrer une copie des réponses brutes par défaut pour tous les questionnaires. [En savoir plus](../dev/surveys/managing-answers.md) |
| AEMResourceTypeFilter. | Types de ressources Adobe Experience Manager pouvant être utilisées dans Campaign, séparées par des virgules. [En savoir plus](../connect/ac-aem.md) |
| nmsPipeline_config | Configuration des triggers Adobe Experience Cloud au format JSON. Créez-le en tant qu’option de texte long. [En savoir plus](../connect/ac-triggers.md) |
| TNT_EdgeServer | Serveur Adobe Target utilisé pour l’intégration, défini par défaut. Il s’agit du serveur de domaine Adobe Target suivi de /m2, par exemple tt.omtrdc.net/m2. [En savoir plus](../connect/ac-at.md) |
| Nom_Client_TNT | Nom de l’organisation Adobe Target (client). [En savoir plus](../connect/ac-at.md) |
| AAM_DataSourceId, AAM_DestinationId | Identifiants utilisés par l’intégration avec Adobe Audience Manager. [En savoir plus](../start/shared-audiences.md) |
| WdbcCapabilities_AzureDw | Options du connecteur Azure Synapse (Azure SQL Data Warehouse). [En savoir plus](../connect/fda.md) |

## Rubriques connexes {#related-topics}

* [Packages natifs](built-in-packages.md)
* [Principes généraux](general-architecture.md)
* [Guide de rotation des informations d’identification](../../technotes/security/credential-rotation-guide.md)
