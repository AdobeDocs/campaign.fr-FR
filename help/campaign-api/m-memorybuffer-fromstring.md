---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 36%
---
# fromString

Charge le contenu d&#39;une chaîne de caractères dans la mémoire tampon.

```text
fromString (string [, codepage ])
```

## Paramètres

**chaîne** La chaîne de caractères.

**codepage** Page de code utilisée pour sérialiser la chaîne dans la mémoire tampon. Ce paramètre optionnel permet de définir le codage des caractères. Par exemple :

* iso-8859-1
* utf-8
* utf-16
* us-ascii
* shift-jis
* euc-kr

## Valeur renvoyée

Aucune.

## Fonctionnalités

**Méthode de classe :** [MemoryBuffer](c-memorybuffer.md)

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
