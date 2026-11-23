---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 59%
---
# traitement

Traitements par lots effectués sur le serveur applicatif

## Méthodes

| Méthode | Description |
| --- | --- |
| [Annuler](sm-job-cancel.md) | Annule un traitement |
| [CheckIfJobInProcess](sm-job-checkifjobinprocess.md) | Vérifie si le traitement est en cours |
| [Exécuter](sm-job-execute.md) | Exécute un traitement de manière synchrone (dans ce mode les informations de progression et l&#39;annulation ne sont pas disponibles). |
| [FilesExist](sm-job-filesexist.md) | Vérifie si des fichiers sont déjà présents sur le serveur (ou dans la table des ressources). |
| [GetJobsInProcess](sm-job-getjobsinprocess.md) | Retourne les traitements non externes en cours |
| [GetStatus](sm-job-getstatus.md) | Obtenez des informations sur la progression du traitement des tâches. Avertissement : cette API ne garantit pas le renvoi d&#39;une liste d&#39;entrées de journal uniques (l&#39;appelant doit les dédupliquer en utilisant leur identifiant ). |
| [HasWarning](sm-job-haswarning.md) | Demande si des avertissements ou des erreurs ont été générés pour un traitement |
| [Pause](sm-job-pause.md) | Mettre en pause un traitement |
| [Envoyer](sm-job-submit.md) | Soumet un traitement pour une exécution asynchrone |
| [SubmitFromModel](sm-job-submitfrommodel.md) | Soumet un traitement à partir d&#39;un modèle |
| [SubmitSoapCall](sm-job-submitsoapcall.md) | Soumet un traitement pour une exécution asynchrone |
| [AttenteTâcheAnnulée](sm-job-waitjobcancelled.md) | Attend que l&#39;annulation du traitement soit effective |

## Méthodes génériques

| Méthode | Description |
| --- | --- |
| [créer](f-create.md) | Crée une nouvelle entité correspondant à un schéma donné. |
| [charger](f-load.md) | Charge et retourne une entité correspondant à un schéma et une clé donnés. |
| [enregistrer](m-entity-save.md) | Enregistre une entité dans la base de données. |
