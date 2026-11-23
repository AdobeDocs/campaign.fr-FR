---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 77%
---
# diffusion

Ce schéma représente une diffusion ou un modèle.

Un modèle est un modèle de diffusion rassemblant tous les paramètres nécessaires. Un modèle de diffusion peut être exécuté manuellement à partir de la console cliente ou exécuté sur un événement (lancement à partir du planificateur ou par programmation à partir d&#39;un appel SOAP).

## Méthodes

| Méthode | Description |
| --- | --- |
| [AppendDeliveryPart](sm-delivery-appenddeliverypart.md) | Ajoute un fragment à une diffusion en préparation. |
| [BuildForward](sm-delivery-buildforward.md) | Construit la page HTML. |
| [BuildMirror](sm-delivery-buildmirror.md) | Construit la page miroir HTML. |
| [BuildMirrorEx](sm-delivery-buildmirrorex.md) | Construit la page miroir HTML. |
| [BuildPreview](sm-delivery-buildpreview.md) | Construit l&#39;aperçu d&#39;un contenu à diffuser ou d&#39;une ligne du fichier de sortie (en mode externe). |
| [BuildPreviewFromId](sm-delivery-buildpreviewfromid.md) | Construit l&#39;aperçu d&#39;un contenu à diffuser ou d&#39;une ligne du fichier de sortie (en mode externe). |
| [BuildTargetDataSchema](sm-delivery-buildtargetdataschema.md) |  |
| [NettoyageDes Diffusions](sm-delivery-cleanupdeliveries.md) | Indique au serveur de mid-sourcing de détruire certaines diffusions. |
| [CollectLogs](sm-delivery-collectlogs.md) | Crée une table avec l&#39;ensemble des messages de log de diffusion d&#39;une liste de diffusions |
| [CreateFromModel](sm-delivery-createfrommodel.md) | Création d&#39;une diffusion depuis un modèle (renseigné par son nom interne). |
| [DéployerTriggerMessageSingle](sm-delivery-deploytriggermessagesingle.md) | Publiez le message transactionnel sur les instances d&#39;exécution. Renvoie true si la publication a réussi, false dans le cas contraire. |
| [MessagesDéployerDéclencheur](sm-delivery-deploytriggermessages.md) | Publier les messages transactionnels sélectionnés sur les instances d&#39;exécution |
| [DiagnostiquerHTML](sm-delivery-diagnosehtml.md) | Lance le diagnostic du contenu Html |
| [DispatchImages](sm-delivery-dispatchimages.md) | Indique au serveur applicatif d&#39;envoyer les images au serveur de mid-sourcing. |
| [ExecCommand](sm-delivery-execcommand.md) | Exécute une commande sur une diffusion. |
| [ExecuteJob](sm-delivery-executejob.md) | Exécute un traitement sur une diffusion de manière synchrone. |
| [FinalizeMidPreparation](sm-delivery-finalizemidpreparation.md) | Finalise l&#39;analyse d&#39;une diffusion en mode mid-sourcing. |
| [GetDeviceList](sm-delivery-getdevicelist.md) |  |
| [GetDlStatusAndLogs](sm-delivery-getdlstatusandlogs.md) | Demande les derniers logs du journal ainsi que l&#39;état de la diffusion. |
| [GetFilesToDownload](sm-delivery-getfilestodownload.md) | Retourne la liste des fichiers présents sur le serveur concernant la diffusion. |
| [GetMidBroadLogs](sm-delivery-getmidbroadlogs.md) | Récupère les derniers logs mis à jour des diffusions en mode midsourcing. |
| [GetMidDeliveries](sm-delivery-getmiddeliveries.md) | Récupère l&#39;état des dernières diffusions mises à jour en mode midsourcing. |
| [GetMidXtkKey](sm-delivery-getmidxtkkey.md) | Retourne la clef Xtk du server mid |
| [GetMirrorURL](sm-delivery-getmirrorurl.md) | Obtient l&#39;URL d&#39;une page miroir HTML. |
| [GetSeedList](sm-delivery-getseedlist.md) |  |
| [HtmlToText](sm-delivery-htmltotext.md) | Convertit du contenu Html en texte simple |
| [Publication d’images](sm-delivery-imagepublishing.md) | Effectue les post-traitements : déplacement de l&#39;image dans un dossier spécifique et mise en ligne effective |
| [InstallTransactionalMessage](sm-delivery-installtransactionalmessage.md) | Installer un modèle de message transactionnel sur l&#39;instance d&#39;exécution. |
| [InvalidateDeliveryCache](sm-delivery-invalidatedeliverycache.md) | Doit être appelé à la fin de la préparation des messages sauf dans le cas du mode mid-sourcing. (méthode privée) |
| [LaunchFCP](sm-delivery-launchfcp.md) | Lance un BAT sur une diffusion. |
| [LoadExpandedContents](sm-delivery-loadexpandedcontents.md) | Charge une liste composants pour le pré-traitement avec leurs dépendances (blocs de personnalisation, options, objets de script additionnels...). |
| [Pause](sm-delivery-pause.md) | Suspend une diffusion en cours. |
| [Lecture](sm-delivery-play.md) | Démarre une diffusion. |
| [Préparer](sm-delivery-prepare.md) | Analyse la diffusion : ciblage et personnalisation |
| [Préparer Et Démarrer](sm-delivery-prepareandstart.md) | Analyse la diffusion avec démarrage dans la foulée si aucune erreur ne s&#39;est produite |
| [PrepareFromId](sm-delivery-preparefromid.md) | Analyse une diffusion. |
| [PréparerMessage](sm-delivery-preparemessage.md) | Personnalisation des messages |
| [PréparerMessageImpl](sm-delivery-preparemessageimpl.md) | Personnalisation des messages |
| [PréparerMultipartRelated](sm-delivery-preparemultipartrelated.md) | Enregistre les images à inclure dans l&#39;email dans la base de données |
| [PréparerNotification](sm-delivery-preparenotification.md) | Analyse d&#39;une notification venant s&#39;ajouter à une diffusion existante |
| [Préparer l&#39;épreuve](sm-delivery-prepareproof.md) | Analyse d&#39;une diffusion en vue de la génération d&#39;un BAT |
| [Préparer Target](sm-delivery-preparetarget.md) | Comptage et arbitrage de la cible de la diffusion |
| [PréparerTargetImpl](sm-delivery-preparetargetimpl.md) | Comptage et arbitrage de la cible de la diffusion |
| [AperçuExtraction](sm-delivery-previewextraction.md) | Aperçu du fichier d&#39;extraction |
| [PrioritizeLogs](sm-delivery-prioritizelogs.md) | Priorise les logs de diffusions d&#39;une liste de diffusions |
| [PrioriseTarget](sm-delivery-prioritizetarget.md) | Arbitrage de la cible de la diffusion |
| [QueueNotification](sm-delivery-queuenotification.md) | Demande de mise en file d&#39;attente d&#39;une création et soumission d&#39;une notification depuis un modèle |
| [RecomputeStats](sm-delivery-recomputestats.md) | Mise à jour des statistiques d&#39;envoi et de tracking pour une diffusion. |
| [SaveUrlInfo](sm-delivery-saveurlinfo.md) | Sauvegarde les URL de cette diffusion en tant que modèles d&#39;URL. |
| [Stopper](sm-delivery-stop.md) | Termine une diffusion en cours. |
| [StoreMirrorPageInfo](sm-delivery-storemirrorpageinfo.md) | Ajoute les informations pour la génération des pages miroir pour tout un ensemble de fragments de diffusion. |
| [StoreMirrorPageInfoEx](sm-delivery-storemirrorpageinfoex.md) | Ajoute les informations pour la génération des pages miroir pour tout un ensemble de fragments de diffusion. |
| [SoumettreDiffusion](sm-delivery-submitdelivery.md) | Création et soumission d&#39;une diffusion depuis un modèle (renseigné par son nom interne). |
| [SubmitDeliveryById](sm-delivery-submitdeliverybyid.md) | Création et soumission d&#39;une diffusion depuis un modèle (renseigné par son identifiant interne). |
| [TâcheEnvoyer](sm-delivery-submitjob.md) | Soumet un traitement sur un diffusion pour une exécution asynchrone |
| [SubmitMidSourcing](sm-delivery-submitmidsourcing.md) | Soumet une diffusion en mode mid-sourcing. |
| [SoumettreNotification](sm-delivery-submitnotification.md) | Création et soumission d&#39;une notification depuis un modèle de diffusion |
| [UpdateBroadLogs](sm-delivery-updatebroadlogs.md) | Met à jour l&#39;état des logs de diffusion, effectue le traitement des erreurs et met à jour les compteurs de la diffusion. |
| [UpdateCachedDelivery](sm-delivery-updatecacheddelivery.md) | Doit être appelé chaque fois que la diffusion a été modifié en mémoire afin d&#39;avoir une représentation à jour dans les autres threads (méthode privée) |
| [UpdateImageConfig](sm-delivery-updateimageconfig.md) | Modifie le noeud imageConfig afin de prendre en compte les images qui sont déjà sur le serveur. |
| [ValidateWavesDefinition](sm-delivery-validatewavesdefinition.md) | Valide la cohérence des informations saisies pour la définition des vagues. |

## Méthodes génériques

| Méthode | Description |
| --- | --- |
| [créer](f-create.md) | Crée une nouvelle entité correspondant à un schéma donné. |
| [charger](f-load.md) | Charge et retourne une entité correspondant à un schéma et une clé donnés. |
| [enregistrer](m-entity-save.md) | Enregistre une entité dans la base de données. |
