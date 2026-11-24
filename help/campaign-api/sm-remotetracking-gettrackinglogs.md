---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 15%
---
# GetTrackingLogs

Permet de récupérer les logs de tracking générés par le service de redirection et de webtracking.

```text
[ String pointer, Number logCount, String logs, Date srvDate ] = GetTrackingLogs ( String instance, String dbId, Number version, String pointer, Number logCount )
```

## Paramètres

Identifiant court de **instance**

Identifiant de base de données **dbId** pour le client effectuant une diffusion

**version** Version du log de tracking

**pointeur** Identifiant (int64 sérialisé) du log à partir duquel les logs doivent être récupérés.

**logCount** Nombre de logs à récupérer pour la requête (0 signifie valeur par défaut), nombre de logs renvoyés par la réponse.

## Valeur(s) renvoyée(s)

**pointeur** Identifiant (int64 sérialisé) du log à partir duquel les logs doivent être récupérés.

**logCount** Nombre de logs à récupérer pour la requête (0 signifie valeur par défaut), nombre de logs renvoyés par la réponse.

**logs** journaux récupérés

**srvDate** GMT heure du serveur au moment de la demande de récupération du journal

## Fonctionnalités

**Schéma :** [nms:remoteTracking](s-nms-remotetracking.md)

**Statique :**

Oui
