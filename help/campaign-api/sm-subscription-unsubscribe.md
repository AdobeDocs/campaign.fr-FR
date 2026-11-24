---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '29'
ht-degree: 41%
---
# Se désinscrire

Désinscription d&#39;un destinataire d&#39;un service d&#39;information

```text
Unsubscribe ( String serviceName, XML recipient )
```

## Paramètres

**serviceName** Liste des noms de services d&#39;information (séparés par des virgules)

**destinataire** Destinataire

## Valeur(s) renvoyée(s)

Aucune.

## Exemple

```javascript
      var recipient = {recipient: {_key: "email", email: "john.smith@example.com"}}
nms.subscription.Unsubscribe("SVC1", recipient)
        
```

## Fonctionnalités

**Schéma :** [nms:subscription](s-nms-subscription.md)

**Statique :**

Oui
