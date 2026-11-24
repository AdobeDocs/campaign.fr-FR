---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 15%
---
# GetMidBroadLogs

Récupère les derniers logs mis à jour des diffusions en mode midsourcing.

```text
[ XML result, Date nextDate ] = GetMidBroadLogs ( Date startDate, Number logCount, Date emitterDate )
```

## Paramètres

**startDate** Récupérez les journaux modifiés depuis cette date (sur le serveur de mid-sourcing).

**logCount** Nombre maximal de journaux à récupérer, dans la mesure où ils n’ont pas été mis à jour dans la même seconde.

**emitterDate** Date de référence du serveur émetteur. Permet d’ajuster les dates des logs de diffusion.

## Valeur(s) renvoyée(s)

Document de sortie **result**, liste des logs de diffusion.

**nextDate** Date du premier log récupéré (postérieure à startDate).

## Fonctionnalités

**Schéma :** [nms:delivery](s-nms-delivery.md)

**Statique :**

Oui
