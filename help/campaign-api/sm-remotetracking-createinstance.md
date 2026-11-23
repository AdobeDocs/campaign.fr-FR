---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 15%
---
# CreateInstance

> Avertissement : cette fonction est disponible pour un environnement On-Premise.

Permet de créer une instance de tracking

```text
CreateInstance ( String instanceName, String hosts, String dbId, String cryptedPwd, String lang )
```

## Paramètres

**instanceName** Nom de l’instance à créer

**hôtes** masques DNS associés à l’instance

Identifiant de base de données **dbId** pour le client effectuant une diffusion

Mot de passe chiffré **cryptedPwd** utilisé pour le suivi

**lang** Langue de l&#39;instance

## Valeur(s) renvoyée(s)

Aucune.

## Fonctionnalités

**Schéma :** [nms:remoteTracking](s-nms-remotetracking.md)

**Statique :**

Oui
