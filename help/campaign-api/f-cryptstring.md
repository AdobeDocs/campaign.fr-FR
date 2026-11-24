---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 38%
---
# cryptString

> Avertissement :
>
> Cette fonction est complètement obsolète. Pour plus d’informations, reportez-vous à cette [page](https://experienceleague.adobe.com/fr/docs/campaign-classic/using/technotes/gcm-functions#deprecated-functions-headding-anchor-depracated-functions).

Chiffre une chaîne de caractères avec la clé de l’instance ou toute autre clé.

```text
cryptString (str [, key ] [, useSalt ])
```

## Paramètres

**str** La chaîne de caractères à chiffrer.

**clé** La clé de chiffrement AES est codée en base 64 : 256 bits si la longueur de la clé est 32 ; 192 bits si la longueur de la clé est 24 ; 128 bits si la longueur de la clé est 16 ou si aucune clé n&#39;est spécifiée.

**useSalt** Utilisez un sel des données à chiffrer. True par défaut.

## Valeur renvoyée

Renvoie la chaîne de caractères chiffrée

## Remarques

Le chiffrement se fait selon la méthode suivante :

* La chaîne de caractères unicode est transformée en chaîne UTF-8.
* Un caractère de vérification est ajouté à la fin.
* Cette chaîne est chiffrée à l’aide de l’algorithme AES en mode de chaîne de blocs de chiffrement (CBC) avec un vecteur d’initialisation nul. Si aucune clé n’est fournie en tant que paramètre, la clé d’instance est utilisée.
* Le bloc chiffré est alors converti en base 64.

Le déchiffrement est effectué à l&#39;aide de la fonction [decryptString](f-decryptstring.md).

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
