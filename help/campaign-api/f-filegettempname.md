---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 21%
---
# fileGetTempName

Génère un nom de fichier temporaire.

```text
fileGetTempName ( [directory ] [, prefix ] [, extension ])
```

## Paramètres

**répertoire** Répertoire du fichier temporaire. Si vide, utilisez le répertoire temporaire défini par le système.

**préfixe** : préfixe avec un maximum de 4 caractères. Si ce champ est vide, le préfixe tmp est utilisé.

**extension** Extension de fichier.

## Valeur renvoyée

Nom complet du fichier.

## Fonctionnalités

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
