---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 5%
---
# EvaluateTargetFromId

Évalue le ciblage pour chaque diffusion de la campagne associée à une commande. Cette évaluation sera effectuée lors de la commande en utilisant les droits de l&#39;opérateur et avant que la campagne locale ne soit créée.

```text
XML result = EvaluateTargetFromId ( Number orderId )
```

## Paramètres

**orderId** ID de commande.

## Valeur(s) renvoyée(s)

**résultat** Résultat des comptages pour chacune des diffusions de la campagne.

## Fonctionnalités

**Schéma :** [nms:localOrder](s-nms-localorder.md)

**Statique :**

Oui
