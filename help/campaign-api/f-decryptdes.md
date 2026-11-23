---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 11%
---
# decryptDES

> Avertissement :
>
> Cette fonction est obsolète. Utilisez [decryptString()](f-decryptstring.md).

Déchiffre une chaîne avec l’algorithme DES.

```text
decryptDES (key, value [, cipher mode ] [, initialization vector ])
```

## Paramètres

**key** Clé représentée en hexadécimal. La clé doit comporter 64 bits de long ou 16 caractères hexadécimaux.

**value** Les données à chiffrer sont représentées dans la base 64.

**mode de chiffrement** Méthode de codage des blocs. Chaîne de caractères. c’est-à-dire « CBC », « ECB » ou « EDE ». Par défaut « CBC ».

**vecteur d&#39;initialisation** Vecteur d&#39;initialisation sous forme de chaîne hexadécimale. Exactement 8 octets, soit 16 caractères. Chaîne vide par défaut.

## Valeur renvoyée

Chaîne de caractères en texte clair.

## Remarques

* Une clé DES a 56 bits utiles et 8 bits utilisés pour la parité ; ces bits sont ignorés.
* Les données seront déchiffrées sous la forme d’une chaîne 8 bits dans la page de code Windows-1252.
* La longueur des données chiffrées doit être un multiple de 64 bits.

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
