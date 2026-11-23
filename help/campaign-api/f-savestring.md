---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 28%
---
# saveString

Cette commande est obsolète. Utilisez [saveFile()](f-savefile.md). Enregistre une chaîne de caractères dans un fichier.

```text
saveString (text, filename [, codePage ])
```

## Paramètres

**text** Chaîne de texte à enregistrer.

**nom_fichier** Nom complet du fichier à enregistrer.

**codePage** Ce paramètre facultatif permet de spécifier le codage des caractères. Exemple:

* iso-8859-1
* utf-8
* utf-16
* us-ascii
* shift-jis
* euc-kr

## Valeur renvoyée

Aucune.

## Remarques

Si le codage des caractères n’est pas spécifié, la valeur par défaut du serveur est utilisée.

## Fonctionnalités

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
