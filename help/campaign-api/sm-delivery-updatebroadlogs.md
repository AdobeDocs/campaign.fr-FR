---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 31%
---
# UpdateBroadLogs

Met à jour l&#39;état des logs de diffusion, effectue le traitement des erreurs et met à jour les compteurs de la diffusion.

```text
UpdateBroadLogs ( Number deliveryId, XML logs, Boolean deliveryMustExist )
```

## Paramètres

Identifiant de diffusion **deliveryId**

**logs** Collection contenant les enregistrements nms:broadLog à mettre à jour (@id, @status, @eventDate et @lastModified doivent être spécifiés)

**deliveryMustExist** Indique s’il faut générer une erreur pour un identifiant de diffusion non valide.

## Valeur(s) renvoyée(s)

Aucune.

## Fonctionnalités

**Schéma :** [nms:delivery](s-nms-delivery.md)

**Statique :**

Oui
