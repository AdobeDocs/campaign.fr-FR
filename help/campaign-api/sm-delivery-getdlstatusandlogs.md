---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '42'
ht-degree: 33%
---
# GetDlStatusAndLogs

Demande les derniers logs du journal ainsi que l&#39;état de la diffusion.

```text
[ Number deliveryState, XML returnLogs ] = GetDlStatusAndLogs ( Number deliveryId, Number lastLogId )
```

## Paramètres

Identifiant de diffusion **deliveryId**

**lastLogId** Identifiant de la dernière entrée de journal renvoyée lors de l&#39;appel précédent

## Valeur(s) renvoyée(s)

**deliveryState** État de la diffusion

**returnLogs** Messages du journal

## Fonctionnalités

**Schéma :** [nms:delivery](s-nms-delivery.md)

**Statique :**

Oui
