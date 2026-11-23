---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 18%
---
# loadXmlFile

> Avertissement :
>
> L’accès via les API de fichiers est limité aux dossiers **var**, **sftp** et temporaires d’Adobe Campaign.

Cette fonction est obsolète. Utilisez [DOMDocument.load()](m-domdocument-load.md). Charge un fichier sous forme d&#39;un objet document XML

```text
loadXmlFile (filename [, noErr ])
```

## Paramètres

**nom_fichier** Nom complet du fichier à charger.

**noErr** Si vrai, aucune erreur si le fichier est vide (par défaut=faux).

## Valeur renvoyée

Un document XML.

## Remarques

Cette fonction prend en charge la détection de la page de code du fichier grâce à la détection de la nomenclature et du prologue XML.

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
