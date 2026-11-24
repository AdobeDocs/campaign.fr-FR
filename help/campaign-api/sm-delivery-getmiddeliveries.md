---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 19%
---
# GetMidDeliveries

Récupère l&#39;état des dernières diffusions mises à jour en mode midsourcing.

```text
[ XML result, Date nextDate ] = GetMidDeliveries ( Date startDate, Number maxCount, Date emitterDate )
```

## Paramètres

**startDate** Récupérez les modifications depuis cette date (sur le serveur de mid-sourcing).

**maxCount** Nombre maximal de diffusions à récupérer, à condition qu&#39;elles n&#39;aient pas été mises à jour dans la même seconde.

**emitterDate** Date de référence du serveur émetteur. Permet d’ajuster les dates de diffusion.

## Valeur(s) renvoyée(s)

Document de sortie **result**, liste des diffusions mises à jour.

**nextDate** Date de début du prochain appel.

## Fonctionnalités

**Schéma :** [nms:delivery](s-nms-delivery.md)

**Statique :**

Oui
