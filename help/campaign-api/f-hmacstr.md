---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 8%
---
# hmacStr

Calcule le hachage MD5, SHA-1 ou SHA-256 d’une chaîne de caractères. La chaîne est automatiquement codée au format UTF-8 avant le calcul.

```text
hmacStr (string [, key ] [, algo ])
```

## Paramètres

**string** Chaîne dans laquelle le hachage doit être calculé.

Clé **key**, sous la forme d&#39;une chaîne de caractères. Il est automatiquement converti en UTF-8. Si la clé est manquante, le serveur utilisera une clé qui dépend de l’instance et qui n’est valide que sur cette instance.

**algo** Type de hachage à utiliser. Les valeurs possibles sont « MD5 », « SHA1 » ou « SHA256 ». La casse est ignorée, les valeurs peuvent donc être saisies en minuscules ou en majuscules. La valeur « SHA1 » est sélectionnée par défaut, si aucun paramètre n’est spécifié.

## Valeur renvoyée

Le hachage MD5, SHA-1 ou SHA-256 (selon le type de hachage sélectionné) de la chaîne transmise en tant que paramètre.

## Remarques

Pour les types MD5 et SHA-1, la clé peut contenir jusqu’à 64 caractères (512 bits) après la conversion au format UTF-8. Pour le type SHA-256, la clé peut contenir jusqu’à 32 caractères (256 bits) après la conversion au format UTF-8.

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
