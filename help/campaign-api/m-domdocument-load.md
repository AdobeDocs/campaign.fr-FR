---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 18%
---
# charge

> Avertissement :
>
> L’accès via les API de fichiers est limité aux dossiers **var**, **sftp** et temporaires d’Adobe Campaign.

Crée un nouveau document à partir d&#39;un fichier XML.

```text
load (filename [, allowEmpty ])
```

## Paramètres

**nom** Nom du fichier à charger.

**allowEmpty** Si vrai, ne lève pas d&#39;exception si le fichier est vide (default=false).

## Valeur renvoyée

Aucune.

## Remarques

Une exception est générée si le fichier ne peut pas être chargé ou si le contenu du fichier n’est pas un document XML valide. Cette fonction s&#39;applique à la classe DOMDocument. Exemple:

```javascript
var doc = DOMDocument.load("data/test.xml")
```

## Fonctionnalités

**Méthode de classe :** [DOMDocument](c-domdocument.md)

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
