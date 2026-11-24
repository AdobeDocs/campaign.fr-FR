---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 10%
---
# GetQuarantaines

Récupère les dernières mises en quarantaine et les dernières sorties de quarantaine.

```text
[ XML result, Date nextDate, Boolean hasMore ] = GetQuarantines ( Date startDate, String pointerName, Number quarantineCount, Date callerDate )
```

## Paramètres

**startDate** Récupérez les quarantaines modifiées depuis cette date. Lorsqu’elle est vide, la valeur du pointeur est utilisée.

**pointerName** Récupérez les quarantaines modifiées depuis ce pointeur (facultatif).

**quarantineCount** Nombre maximal de quarantaines à récupérer, à condition qu&#39;elles n&#39;aient pas été mises à jour dans la même seconde.

**callerDate** Date de référence de l&#39;appelant. Permet de modifier le référentiel de date des quarantaines (facultatif).

## Valeur(s) renvoyée(s)

**document de sortie**, liste des quarantaines.

**nextDate** Date de la première quarantaine non récupérée (strictement supérieure à startDate).

**hasMore** Si tel est le cas, il reste des quarantaines à récupérer.

## Fonctionnalités

**Schéma :** [nms:address](s-nms-address.md)

**Statique :**

Oui
