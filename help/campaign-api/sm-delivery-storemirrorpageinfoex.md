---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '67'
ht-degree: 22%
---
# StoreMirrorPageInfoEx

Ajoute les informations pour la génération des pages miroir pour tout un ensemble de fragments de diffusion.

```text
[ Number fatalError, String fatalErrorMsg ] = StoreMirrorPageInfoEx ( Number deliveryId, Boolean notification, Number partsCount, Number firstPartId, Number notificationId )
```

## Paramètres

Identifiant de diffusion **deliveryId**

**notification** S&#39;agit-il d&#39;une notification ?

**partsCount** Nombre de parties

**firstPartId** Identifiant du premier fragment

Identifiant de notification **notificationId**

## Valeur(s) renvoyée(s)

**fatalError** renvoie un code d&#39;erreur empêchant l&#39;appelant d&#39;effectuer des reprises. Dans le cas contraire, l’erreur peut être temporaire.

Message d&#39;erreur **fatalErrorMsg** associé au code d&#39;erreur &#39;fatalError&#39;.

## Fonctionnalités

**Schéma :** [nms:delivery](s-nms-delivery.md)

**Statique :**

Oui
