---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '36'
ht-degree: 27%
---
# Validation de la diffusion

Validation d&#39;une diffusion dans une opération.

```text
DeliveryValidation ( Number deliveryId, Number type, Boolean refused, String comment )
```

## Paramètres

Identifiant de diffusion **deliveryId**

**type** Type de validation (ciblage=0, contenu=1, budget=2, extraction=3)

**refusé** Rejet

**commentaire**

## Valeur(s) renvoyée(s)

Aucune.

## Fonctionnalités

**Schéma :** [nms:operation](s-nms-operation.md)

**Statique :**

Oui
