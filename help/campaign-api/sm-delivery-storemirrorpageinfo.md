---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 23%
---
# StoreMirrorPageInfo

Ajoute les informations pour la génération des pages miroir pour tout un ensemble de fragments de diffusion.

```text
[ Number fatalError, String fatalErrorMsg ] = StoreMirrorPageInfo ( Number deliveryId, Number partsCount, Number firstPartId, Number lastPartId )
```

## Paramètres

Identifiant de diffusion **deliveryId**

**partsCount** Nombre de parties

**firstPartId** Identifiant du premier fragment

**lastPartId** Identifiant du dernier fragment

## Valeur(s) renvoyée(s)

**fatalError** renvoie un code d&#39;erreur empêchant l&#39;appelant d&#39;effectuer des reprises. Dans le cas contraire, l’erreur peut être temporaire.

Message d&#39;erreur **fatalErrorMsg** associé au code d&#39;erreur &#39;fatalError&#39;.

## Fonctionnalités

**Schéma :** [nms:delivery](s-nms-delivery.md)

**Statique :**

Oui
