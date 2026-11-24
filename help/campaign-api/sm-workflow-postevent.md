---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 2%
---
# PostEvent

Génère un événement à partir d’une activité quelconque.

```text
PostEvent ( String workflowId, String activity, String transition, XML parameters, Boolean complete )
```

## Paramètres

**workflowId** Identifiant ou nom interne du workflow.

**activity** Nom de l’activité d’où l’événement doit partir

**transition** Nom de la transition à activer. Si ce nom est vide, l’événement sera émis lors de la première transition valide (les événements de type expiration sont ignorés).

**parameters** Les paramètres de l’événement sous la forme d’un élément XML. Le nom de l’élément doit être une variable. Si vous ne souhaitez pas transmettre de variable, vous pouvez utiliser un élément vide &lt;variables/> ou une chaîne vide « ».

**terminé** Toutes les tâches en attente sur l&#39;activité spécifiée sont terminées.

## Valeur(s) renvoyée(s)

Aucune.

## Remarques

* La commande est exécutée en mode asynchrone et n’a pas d’effet immédiat après le retour de la méthode.
* Le workflow cible doit être démarré lorsque cette méthode est appelée. S’il n’est pas lancé, une erreur est consignée dans le fichier journal correspondant.
* Si le workflow cible est suspendu lors de l’appel de la méthode , la commande reste dans la file d’attente jusqu’à la reprise du workflow.
* Il n&#39;y a aucune restriction sur l&#39;activité : il n&#39;est pas nécessaire qu&#39;elle ait une tâche en cours ou même terminée.

## Fonctionnalités

**Schéma :** [xtk:workflow](s-xtk-workflow.md)

**Statique :**

Oui
