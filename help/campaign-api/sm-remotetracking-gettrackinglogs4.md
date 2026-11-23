---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 18%
---
# GetTrackingLogs4

Permet de récupérer les logs de tracking générés par le service de redirection et de tracking web. Version post 4.00

```text
[ String pointer, Number logCount, String logs, Date srvDate ] = GetTrackingLogs4 ( String instance, String dbId, String pointer, Number logCount )
```

## Paramètres

Identifiant court de **instance**

Identifiant de base de données **dbId** pour le client effectuant une diffusion

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
