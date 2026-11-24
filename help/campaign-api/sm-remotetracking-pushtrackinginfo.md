---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 32%
---
# PushTrackingInfo

Permet de charger sur le serveur de tracking distant toutes les informations concernant une diffusion.

```text
PushTrackingInfo ( String instance, String dbId, String jobId, XML document )
```

## Paramètres

**nom de l’instance**

Identifiant de base de données **dbId** pour le client effectuant une diffusion

**jobId** ID de diffusion.

**document** Document contenant les informations de tracking pour cette diffusion

## Valeur(s) renvoyée(s)

Aucune.

## Fonctionnalités

**Schéma :** [nms:remoteTracking](s-nms-remotetracking.md)

**Statique :**

Oui
