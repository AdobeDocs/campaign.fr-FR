---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 20%
---
# saveXmlFile

> Avertissement :
>
> L’accès via les API de fichiers est limité aux dossiers **var**, **sftp** et temporaires d’Adobe Campaign.

Enregistre dans un fichier une chaîne de caractères correspondant à un document XML.

```text
saveXmlFile (text, filename [, codePage ])
```

## Paramètres

**text** Le document XML sous la forme d&#39;une chaîne de caractères à enregistrer.

**nom_fichier** Nom complet du fichier à enregistrer.

**codePage** Ce paramètre facultatif permet de spécifier le codage des caractères. Exemple:

* iso-8859-1
* utf-8
* utf-16
* us-ascii
* shift-jis
* euc-kr

## Valeur renvoyée

Aucune.

## Remarques

Cette fonction insère un prologue XML dans le fichier, si nécessaire, et spécifie le codage du document. Si le codage des caractères n’est pas spécifié, la valeur par défaut du serveur est utilisée.

## Fonctionnalités

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
