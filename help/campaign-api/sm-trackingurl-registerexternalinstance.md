---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 37%
---
# RegisterExternalInstance

Valide une instance de tracking sur un serveur relai vers des serveurs de redirection (en fixant l&#39;identifiant de base de données).

```text
RegisterExternalInstance ( String login, String instanceName, String dbId, Boolean saveParams )
```

## Paramètres

**login** Login d&#39;accès au serveur relais

**instanceName** Nom de l’instance à approuver

Identifiant de base de données **dbId** pour le client effectuant une diffusion

**saveParams** Enregistrez les options en cas de réussite

## Valeur(s) renvoyée(s)

Aucune.

## Fonctionnalités

**Schéma :** [nms:trackingUrl](s-nms-trackingurl.md)

**Statique :**

Oui
