---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 13%
---
# AppendDeliveryPart

Ajoute un fragment à une diffusion en préparation.

```text
[ Number deliveryPartId, Number fatalError, String fatalErrorMsg ] = AppendDeliveryPart ( XML deliveryPart, Boolean retry )
```

## Paramètres

**deliveryPart** Document représentant le fragment de diffusion (ou une collection de fragments de diffusion).

**retry** Indique s&#39;il s&#39;agit d&#39;une nouvelle tentative d&#39;envoi de ce fragment de diffusion.

## Valeur(s) renvoyée(s)

**deliveryPartId** Identifiant du fragment de diffusion dans la base de données (s&#39;il ne s&#39;agit pas d&#39;une collection).

**fatalError** renvoie un code d&#39;erreur empêchant l&#39;appelant d&#39;effectuer des reprises. Dans le cas contraire, l’erreur peut être temporaire.

Message d&#39;erreur **fatalErrorMsg** associé au code d&#39;erreur &#39;fatalError&#39;.

## Fonctionnalités

**Schéma :** [nms:delivery](s-nms-delivery.md)

**Statique :**

Oui
