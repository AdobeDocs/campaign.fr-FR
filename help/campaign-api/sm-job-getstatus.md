---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 4%
---
# GetStatus

Obtenez des informations sur la progression du traitement des tâches. Avertissement : cette API ne garantit pas le renvoi d&#39;une liste d&#39;entrées de journal uniques (l&#39;appelant doit les dédupliquer en utilisant leur identifiant ).

```text
[ Number status, XML returnLogs, XML properties ] = GetStatus ( String id, Number lastLogId, Number maxLogCount )
```

## Paramètres

Identifiant du traitement **id**

**lastLogId** Identifiant de la dernière entrée de journal renvoyée lors de l&#39;appel précédent

**maxLogCount** nombre maximal d’entrées de journal à envoyer

## Valeur(s) renvoyée(s)

**statut** statut de la tâche

**returnLogs** Messages du journal

**propriétés** Propriétés (progression...)

## Fonctionnalités

**Schéma :** [xtk:job](s-xtk-job.md)

**Statique :**

Oui
