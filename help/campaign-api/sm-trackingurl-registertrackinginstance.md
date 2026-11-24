---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 28%
---
# RegisterTrackingInstance

Valide une instance de tracking sur un serveur de redirection (en fixant l&#39;identifiant de base de données).

```text
RegisterTrackingInstance ( String serverUrl, String secureServerUrl, String serverUrlList, String instanceName, String cryptedPassword )
```

## Paramètres

**serverUrl** URL externe du serveur de tracking

**secureServerUrl** URL sécurisée externe du serveur de tracking

**serverUrlList** URL internes des serveurs de tracking

**instanceName** Nom de l’instance à approuver

**mot de passe chiffré** mot de passe chiffré

## Valeur(s) renvoyée(s)

Aucune.

## Fonctionnalités

**Schéma :** [nms:trackingUrl](s-nms-trackingurl.md)

**Statique :**

Oui
