---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 4%
---
# EvaluateContentFromId

Evalue le contenu d&#39;une diffusion de la diffusion associée à une commande. Cette évaluation sera effectuée lors de la commande en utilisant les droits de l&#39;opérateur et avant que la campagne locale ne soit créée.

```text
XML result = EvaluateContentFromId ( Number orderId, Number deliveryId, String contentType, Number seedMemberId )
```

## Paramètres

**orderId** ID de commande.

**deliveryId** ID de la diffusion à évaluer.

**contentType** Type du contenu à renvoyer (html ou texte pour un email ; chaîne vide pour les autres canaux).

**seedMemberId** Identifiant d’adresse de contrôle utilisé pour la personnalisation du contenu.

## Valeur(s) renvoyée(s)

**résultat** Contenu évalué.

## Fonctionnalités

**Schéma :** [nms:localOrder](s-nms-localorder.md)

**Statique :**

Oui
