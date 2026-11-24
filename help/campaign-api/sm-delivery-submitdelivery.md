---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 32%
---
# SubmitDelivery

Création et soumission d&#39;une diffusion depuis un modèle (renseigné par son nom interne).

```text
Number deliveryId = SubmitDelivery ( String scenarioName, XML content )
```

## Paramètres

**scenarioName** Nom interne du modèle de diffusion

Contenu XML **content** à ajouter au modèle

## Valeur(s) renvoyée(s)

**deliveryId** Identifiant de la nouvelle diffusion (renvoyé même si l&#39;analyse échoue)

## Fonctionnalités

**Schéma :** [nms:delivery](s-nms-delivery.md)

**Statique :**

Oui
