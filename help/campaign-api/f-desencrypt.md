---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 8%
---
# DESencrypt

> Avertissement :
>
> Cette fonction est obsolète. Utilisez [cryptString()](f-cryptstring.md).

Numérise une chaîne avec l’algorithme DES.

```text
DESencrypt (value [, key ] [, cipher mode ] [, initialization vector ] [, padding ])
```

## Paramètres

**value** Chaîne à numériser

**key** Clé représentée en hexadécimal. La clé doit comporter 64 bits de long ou 16 caractères hexadécimaux. Par défaut, l’identifiant de la base de données est utilisé.

**mode de chiffrement** Méthode de codage des blocs. Une chaîne de caractères. c’est-à-dire « CBC », « ECB » ou « EDE ». Par défaut « CBC ».

**vecteur d&#39;initialisation** Vecteur d&#39;initialisation sous forme de chaîne hexadécimale. Exactement 8 octets, soit 16 caractères. Chaîne vide par défaut.

**padding** Type de remplissage. Une chaîne de caractères, c’est-à-dire « PKCS5PADDING » ou « PKCS7PADDING ». Par défaut, une chaîne vide, ce qui signifie qu&#39;un &#39;\\0&#39; est ajouté à la fin de la chaîne à chiffrer.

## Valeur renvoyée

La chaîne numérisée représentée en base 64.

## Remarques

* Une clé DES a 56 bits utiles et 8 bits utilisés pour la parité ; ces bits sont ignorés.
* La valeur effectivement chiffrée par l’algorithme DES sera la représentation Windows-1252 8 bits de la chaîne, se terminant par un caractère ASCII 0 et complétée par un multiple de 64 bits avec des zéros binaires.
* La valeur numérisée a une valeur de 64 bits de longueur multiple.

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
