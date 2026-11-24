---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 15%
---
# hmac

Calcule le hachage MD5, SHA-1 ou SHA-256 du tampon.

```text
hmac (key [, algo ])
```

## Paramètres

Clé **key**, sous la forme d&#39;un tampon.

Type de hachage **algo** à utiliser. Les valeurs possibles sont « MD5 », « SHA1 » ou « SHA256. Elles ne sont pas sensibles à la casse, les valeurs peuvent donc être saisies en minuscules ou en majuscules. Par défaut, la valeur « SHA1 » est sélectionnée si le paramètre n’est pas spécifié.

## Valeur renvoyée

Le MD5 de hachage, SHA-1 ou SHA-256 (selon le type de hachage choisi) du tampon.

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
