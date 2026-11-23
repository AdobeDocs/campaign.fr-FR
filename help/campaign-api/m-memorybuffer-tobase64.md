---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 18%
---
# toBase64

Convertit la mémoire tampon ou une partie de la chaîne de caractères codée en base 64.

```text
toBase64 ( [start ] [, length ])
```

## Paramètres

**start** Nombre d&#39;octets à ignorer au début du tampon. Le premier octet correspond à la valeur 0 (valeur par défaut).

**longueur** Nombre d&#39;octets à convertir. Par défaut, tous les octets restants sont pris en compte.

## Valeur renvoyée

Le contenu du tampon encodé en base 64.

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
