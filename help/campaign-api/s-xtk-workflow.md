---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 5%
---
# workflow

Définitions des workflows

## Méthodes

| Méthode | Description |
| --- | --- |
| [Nettoyage](sm-workflow-cleanup.md) | Purge l’historique d’un workflow. |
| [SupprimerRésultat](sm-workflow-deleteresult.md) | Efface les resultats d’une ou plusieurs activités. |
| [Exécuter](sm-workflow-execute.md) | Exécute immédiatement un workflow et attend sa fin. |
| [ExecuteInstance](sm-workflow-executeinstance.md) | Exécute immédiatement un workflow et attend sa fin. |
| [GetLogin](sm-workflow-getlogin.md) | Retourne les informations du compte d&#39;exécution. |
| [GetValidationParameters](sm-workflow-getvalidationparameters.md) | Retourne les paramètres d’une tâche de validation en cours. |
| [Tuer](sm-workflow-kill.md) | Arrête inconditionnellement un workflow. |
| [Pause](sm-workflow-pause.md) | Suspend l’exécution d’un workflow en cours. |
| [PostEvent](sm-workflow-postevent.md) | Génère un événement à partir d’une activité quelconque. |
| [Répondre](sm-workflow-reply.md) | Répond à une tâche en cours de type validation. |
| [Redémarrer](sm-workflow-restart.md) | Enchaîne un arrêt et un démarrage du workflow. |
| [RedémarrerLa Tâche](sm-workflow-restarttask.md) | Force le redémarrage d’une ou plusieurs tâches terminées. |
| [SetLogin](sm-workflow-setlogin.md) | Change le compte d&#39;exécution. |
| [Simuler](sm-workflow-simulate.md) | Démarre un workflow en mode simulation. |
| [SimulerAvecParamètres](sm-workflow-simulatewithparameters.md) | Démarre un workflow en mode simulation en lui passant des paramètres. |
| [Génération](sm-workflow-spawn.md) | Crée une instance de workflow à partir d’un modèle, applique un patch puis démarre ce workflow. |
| [Paramètre(S) D&#39;Initialisation](sm-workflow-spawnwithparameters.md) | Crée une instance de workflow à partir d&#39;un modèle puis invoque la méthode [StartWithParameters](sm-workflow-startwithparameters.md) sur cette instance. |
| [SpawnWithParametersEx](sm-workflow-spawnwithparametersex.md) | Crée une instance de workflow à partir d’un modèle et appelle la méthode [StartWithParameters](sm-workflow-startwithparameters.md) ou [SimulateWithParameters](sm-workflow-simulatewithparameters.md) sur cette instance. |
| [Début](sm-workflow-start.md) | Démarre ou reprend l’exécution d’un workflow. |
| [StartWithParameters](sm-workflow-startwithparameters.md) | Démarre un workflow et lui fournit des paramètres. |
| [Stopper](sm-workflow-stop.md) | Arrête un workflow en cours. |
| [Réveil](sm-workflow-wakeup.md) | Force le traitement anticipé de toutes les tâches en attente. |
| [TâcheRéveil](sm-workflow-wakeuptask.md) | Force le traitement anticipé d&#39;une ou plusieurs tâches en attente. |

## Méthodes génériques

| Méthode | Description |
| --- | --- |
| [créer](f-create.md) | Crée une nouvelle entité correspondant à un schéma donné. |
| [charger](f-load.md) | Charge et retourne une entité correspondant à un schéma et une clé donnés. |
| [enregistrer](m-entity-save.md) | Enregistre une entité dans la base de données. |
