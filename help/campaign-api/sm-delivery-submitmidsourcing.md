---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 21%
---
# SubmitMidSourcing

Soumet une diffusion en mode mid-sourcing.

```text
[ Number remoteId, Number remoteMatchId ] = SubmitMidSourcing ( XML delivery, XML routingMatch, String folderName )
```

## Paramètres

**delivery** Document représentant la diffusion.

**routingMatch** n’est plus utilisé

**folderName** Nom complet du dossier (dans la base de données de l&#39;expéditeur).

## Valeur(s) renvoyée(s)

**remoteId** Identifiant de la diffusion dans la base de données du destinataire.

**remoteMatchId** n’est plus utilisé

## Fonctionnalités

**Schéma :** [nms:delivery](s-nms-delivery.md)

**Statique :**

Oui
