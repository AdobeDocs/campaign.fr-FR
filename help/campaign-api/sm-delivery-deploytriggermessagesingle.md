---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 6%
---
# DeployTriggerMessageSingle

Publiez le message transactionnel sur les instances d&#39;exécution. Renvoie true si la publication a réussi, false dans le cas contraire.

```text
Boolean isSuccess = DeployTriggerMessageSingle ( Number deliveryId, Boolean localPublish )
```

## Paramètres

**deliveryId** ID de la diffusion à déployer

**localPublish** Sur l&#39;instance de pilotage uniquement ?

## Valeur(s) renvoyée(s)

Publication de **isSuccess** terminée

## Fonctionnalités

**Schéma :** [nms:delivery](s-nms-delivery.md)

**Statique :**

Oui
