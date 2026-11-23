---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 3%
---
# Connexion

Ouvre une session

```text
[ String sessionToken, sessionInfo sessionInfo, String securityToken ] = Logon ( String login, String password, XML parameters )
```

## Paramètres

**connexion** Compte utilisateur

**mot de passe** mot de passe associé au nom d&#39;utilisateur

**paramètres** Paramètres de connexion

## Valeur(s) renvoyée(s)

**jeton de session** jeton de session

Paramètres de session **sessionInfo**

**jeton de sécurité** Jeton de sécurité

## Configuration du mécanisme de verrouillage des comptes

Un mécanisme de verrouillage de compte est disponible dans l’API logon() . Cette option empêche toute nouvelle tentative de connexion après un certain nombre d’échecs consécutifs au cours d’une période donnée.

Quatre options sont disponibles pour configurer le mécanisme de verrouillage :

* **XtkSecurity\_max\_Unsuccessul\_Attempts\_Allowed** : nombre maximal de tentatives infructueuses de blocage d’une clé pendant la durée spécifiée. La valeur par défaut est 3.
* **XtkSecurity\_Initial\_Ban\_Duration** : durée pendant laquelle la clé sera interdite pour la première fois. La durée par défaut est de 5 minutes.
* **XtkSecurity\_Max\_Ban\_Duration** : durée maximale pendant laquelle une clé peut être interdite.
* **XtkSecurity\_Examine\_Window** : intervalle de temps pour effectuer le suivi du nombre de tentatives de connexion infructueuses visant à interdire une clé non valide. La durée par défaut est de 10 minutes.

Par exemple, si une personne tente 3 tentatives infructueuses en 10 minutes, sa clé sera bloquée pendant 5 minutes.

## Fonctionnalités

**Schéma :** [xtk:session](s-xtk-session.md)

**Statique :**

Oui
