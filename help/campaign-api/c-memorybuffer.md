---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 7%
---
# MemoryBuffer (classe)

Représente un contenu binaire stocké en mémoire.

Un est un objet intermédiaire permettant de manipuler des données depuis et vers un fichier.

## Méthodes

| Méthode | Description |
| --- | --- |
| [disposer](m-memorybuffer-dispose.md) | Libère les ressources utilisées par l’objet . |
| [charger](m-memorybuffer-load.md) | Charge le contenu d’un fichier dans la mémoire tampon. |
| [enregistrer](m-memorybuffer-save.md) | Enregistre le contenu du buffer dans un fichier. |
| [toXML](m-memorybuffer-toxml.md) | Renvoie un objet XML JavaScript obtenu à partir du contenu de [MemoryBuffer](c-memorybuffer.md) . Cette fonction est obsolète. Utilisez [toDocument()](m-memorybuffer-todocument.md). |
| [versDocument](m-memorybuffer-todocument.md) | Retourne un document XML à partir du contenu texte de ce buffer. |
| [toString](m-memorybuffer-tostring.md) | Renvoie le contenu de [MemoryBuffer](c-memorybuffer.md) sous la forme d&#39;une chaîne de caractères. |
| [fromString](m-memorybuffer-fromstring.md) | Charge le contenu d&#39;une chaîne de caractères dans la mémoire tampon. |
| [toBase64](m-memorybuffer-tobase64.md) | Convertit la mémoire tampon ou une partie de la chaîne de caractères codée en base 64. |
| [appendBase64](m-memorybuffer-appendbase64.md) | Ajoute les données d&#39;une chaîne de caractères codée en base 64 à la fin du buffer. |
| [removeAll](m-memorybuffer-removeall.md) | Vidange la mémoire tampon. |
| [sha1](m-memorybuffer-sha1.md) | Calcule la signature SHA-1 du contenu MemoryBuffer. |
| [sha224](m-memorybuffer-sha224.md) | Calcule la signature SHA-2 224 bits du contenu MemoryBuffer. |
| [sha256](m-memorybuffer-sha256.md) | Calcule la signature SHA-2 256 bits du contenu MemoryBuffer. |
| [sha384](m-memorybuffer-sha384.md) | Calcule la signature SHA-2 384 bits du contenu MemoryBuffer. |
| [sha512](m-memorybuffer-sha512.md) | Calcule la signature SHA-2 512 bits du contenu MemoryBuffer. |
| [fromHexString](m-memorybuffer-fromhexstring.md) | Charge le contenu d&#39;une chaîne hexadécimale dans le buffer. |
| [toHexString](m-memorybuffer-tohexstring.md) | Convertit la mémoire tampon en une chaîne de caractères hexadécimaux. |
| [hmac](m-memorybuffer-hmac.md) | Calcule le hachage MD5, SHA-1 ou SHA-256 du tampon. |

## Propriétés

| Propriété | Description |
| --- | --- |
| [taille](p-memorybuffer-size.md) | Renvoie la taille du tampon en octets. |
| [isEmpty](p-memorybuffer-isempty.md) | Renvoie true si la mémoire tampon est vide. |

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
