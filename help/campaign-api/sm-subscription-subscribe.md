---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 32%
---
# S&#39;abonner

Création ou mise à jour de l&#39;abonnement d&#39;un destinataire à un service d&#39;information

```text
Subscribe ( String serviceName, XML recipient, Boolean create )
```

## Paramètres

**serviceName** Liste des noms de services d&#39;information (séparés par des virgules)

**destinataire** Destinataire à enregistrer et éventuellement à créer

**créer** Créez un destinataire s’il n’existe pas

## Valeur(s) renvoyée(s)

Aucune.

## Exemple

```javascript
      var recipient = {recipient: {_key: "email", email: "john.smith@example.com"}}
nms.subscription.Subscribe("SVC1", recipient, false)
        
```

## Fonctionnalités

**Schéma :** [nms:subscription](s-nms-subscription.md)

**Statique :**

Oui
