---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 15%
---
# FinalizeMidPreparation

Finalise l&#39;analyse d&#39;une diffusion en mode mid-sourcing.

```text
[ Number fatalError, String fatalErrorMsg ] = FinalizeMidPreparation ( Number deliveryId, Number errorCode, XML properties, Boolean retry )
```

## Paramètres

Identifiant de diffusion **deliveryId**

**errorCode** Code d’erreur renvoyé par l’analyse sur la base de données marketing (le code d’erreur au niveau de la méthode n’est pas utilisé pour cela)

**propriétés** Propriétés de diffusion à mettre à jour

**retry** Indique s’il s’agit d’une nouvelle tentative pour l’appel de méthode.

## Valeur(s) renvoyée(s)

**fatalError** renvoie un code d&#39;erreur empêchant l&#39;appelant d&#39;effectuer des reprises. Dans le cas contraire, l’erreur peut être temporaire.

Message d&#39;erreur **fatalErrorMsg** associé au code d&#39;erreur &#39;fatalError&#39;.

## Fonctionnalités

**Schéma :** [nms:delivery](s-nms-delivery.md)

**Statique :**

Oui
