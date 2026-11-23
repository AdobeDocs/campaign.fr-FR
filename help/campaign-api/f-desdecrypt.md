---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 11%
---
# DESdecrypt

> Avertissement :
>
> Cette fonction est obsolète. Utilisez [decryptString()](f-decryptstring.md).

Déchiffre une donnée avec l&#39;algorithme DES.

```text
DESdecrypt (value [, key ] [, cipher mode ] [, initialization vector ])
```

## Paramètres

**value** Données à numériser, représentées en base 64.

**key** Clé représentée en hexadécimal. La clé doit comporter 64 bits de long ou 16 caractères hexadécimaux. Par défaut, l’identifiant de la base de données est utilisé.

**mode de chiffrement** Méthode de codage des blocs. Une chaîne de caractères. c’est-à-dire « CBC », « ECB » ou « EDE ». Par défaut « CBC ».

**vecteur d&#39;initialisation** Vecteur d&#39;initialisation sous forme de chaîne hexadécimale. Exactement 8 octets, soit 16 caractères. Chaîne vide par défaut.

## Valeur renvoyée

Chaîne de caractères non chiffrée.

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
