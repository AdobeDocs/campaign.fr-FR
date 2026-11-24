---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 33%
---
# GetTrackingInfo

Permet à un serveur de tracking distant de télécharger les informations concernant une diffusion.

```text
XML document = GetTrackingInfo ( String instance, String dbId, String deliveryId )
```

## Paramètres

**nom de l’instance**

Identifiant de base de données **dbId** pour le client effectuant une diffusion

**deliveryId** ID de diffusion.

## Valeur(s) renvoyée(s)

**document** Document contenant les informations de tracking pour cette diffusion

## Fonctionnalités

**Schéma :** [nms:remoteTracking](s-nms-remotetracking.md)

**Statique :**

Oui
