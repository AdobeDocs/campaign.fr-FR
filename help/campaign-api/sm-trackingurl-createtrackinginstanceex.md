---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '67'
ht-degree: 19%
---
# CreateTrackingInstanceEx

Créé une instance de tracking sur un serveur de redirection

```text
CreateTrackingInstanceEx ( String internalPwd, String serverUrl, String secureServerUrl, String serverUrlList, String instanceName, String cryptedPassword, String host, String imsOrgId )
```

## Paramètres

Mot de passe interne **internalPwd**

**serverUrl** URL externe du serveur de tracking

**secureServerUrl** URL sécurisée externe du serveur de tracking

**serverUrlList** URL internes des serveurs de tracking

**instanceName** Nom de l’instance à créer

**mot de passe chiffré** mot de passe chiffré

**hôte** Masques DNS associés à l’instance

**imsOrgId** ID de l’organisation IMS

## Valeur(s) renvoyée(s)

Aucune.

## Fonctionnalités

**Schéma :** [nms:trackingUrl](s-nms-trackingurl.md)

**Statique :**

Oui
