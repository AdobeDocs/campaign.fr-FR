---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '34'
ht-degree: 26%
---
# ExecCommand

Exécute une commande sur une diffusion.

```text
Number newState = ExecCommand ( String deliveryId, String command )
```

## Paramètres

Identifiant de diffusion **deliveryId**

**command** Nom de la commande (&#39;play&#39;, &#39;pause&#39; ou &#39;stop&#39;)

## Valeur(s) renvoyée(s)

**newState** État de la diffusion après l&#39;exécution de la commande

## Fonctionnalités

**Schéma :** [nms:delivery](s-nms-delivery.md)

**Statique :**

Oui
