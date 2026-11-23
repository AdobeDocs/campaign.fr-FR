---
source-git-commit: 3319b56a62aa8a8364c7f2f85bc81708a66a5978
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 17%
---
# connexion

Remplace le contexte d’exécution du script par la connexion active.

```text
logon (sessionToken)
```

```text
logon (login, password)
```

```text
logon (context)
```

## Paramètres

**sessionToken** Jeton de session à utiliser.

**login** Login de l’opérateur à utiliser.

**password** Mot de passe de l’opérateur. Le mot de passe peut être une chaîne vide si le login actuel possède des droits « administrateur ».

**context** Objet représentant une connexion, renvoyé par un appel de connexion précédent.

## Valeur renvoyée

Renvoie un objet correspondant au nom d’utilisateur précédent. Cela permet de restaurer le login précédent en transmettant ce paramètre à la fonction de connexion.

## Remarques

Exemple:

```javascript
var oldContext = logon("jdoe", "")

// ...

logon(oldContext)
```

## Fonctionnalités

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Message de diffusion
* Règle de typologie
* Import
* JSSP
* Méthode SOAP
* WebApp
* Workflow
