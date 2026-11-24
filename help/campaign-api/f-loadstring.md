---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 29%
---
# loadString

Cette commande est obsolète. Utilisez ⌐[loadFile()](f-loadfile.md). Retourne le contenu d’un fichier texte

```text
loadString (filename [, codePage ])
```

## Paramètres

**filename** Nom complet du fichier à charger.

**codePage** Ce paramètre facultatif permet de spécifier le codage des caractères. Exemple:

* iso-8859-1
* utf-8
* utf-16
* us-ascii
* shift-jis
* euc-kr

## Valeur renvoyée

Chaîne de caractères correspondant au contenu du fichier texte.

## Remarques

Si le codage des caractères n’est pas spécifié, la valeur par défaut du serveur est utilisée.

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
