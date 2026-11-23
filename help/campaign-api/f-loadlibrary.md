---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 16%
---
# loadLibrary

Charge une bibliothèque JavaScript.

```text
loadLibrary (filename [, boolean ])
```

## Paramètres

**filename** Nom de la bibliothèque JavaScript à charger.

**boolean** Active ou désactive le cache de chargement. Par défaut, la valeur est true.

> Remarque : lorsque le paramètre est défini sur false, vous devez utiliser la fonction logon() avant l’appel de loadLibrary pour être authentifié en tant qu’opérateur.

## Valeur renvoyée

Aucune.

## Remarques

Le cache est activé par défaut. Si le cache est désactivé, la base de données est interrogée à chaque appel. Cette requête permet de charger la dernière version de la bibliothèque. Exemple : loadLibrary(&#39;xtk:shared/nl.js&#39;)

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
