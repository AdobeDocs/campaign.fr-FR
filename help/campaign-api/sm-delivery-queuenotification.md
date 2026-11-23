---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 23%
---
# QueueNotification

Demande de mise en file d&#39;attente d&#39;une création et soumission d&#39;une notification depuis un modèle

```text
QueueNotification ( String scenarioName, XML target )
```

## Paramètres

**scenarioName** Nom interne du modèle

**cible** Population cible de la diffusion

## Valeur(s) renvoyée(s)

Aucune.

## Remarques

Cette API peut uniquement être utilisée dans le contexte d’applications web/questionnaires en ligne. Contrairement à SubmitNotification, QueueNotification utilise un thread dédié pour les notifications en file d’attente.

## Fonctionnalités

**Schéma :** [nms:delivery](s-nms-delivery.md)

**Statique :**

Oui
