---
source-git-commit: 3319b56a62aa8a8364c7f2f85bc81708a66a5978
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 20%
---
# obscurcir

Obscurcit un entier en une chaîne de caractères. La valeur d’origine peut être récupérée en appelant la fonction [unobfuscate](f-unobfuscate.md).

```text
obfuscate (value [, size ] [, version ])
```

## Paramètres

**value** Entier à obscurcir.

**size** Taille de la chaîne résultant de l’obscurcissement. Nombre entier compris entre 6 et 10. 6 par défaut.

**version** Version d’obscurcissement à appliquer. 0 par défaut.

## Valeur renvoyée

Chaîne de caractères représentant l’entier obscurci.

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
