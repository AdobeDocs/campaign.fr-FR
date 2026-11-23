---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 15%
---
# liste

Retourne la liste des fichiers sur le serveur dans un répertoire spécifié.

```text
list (URL, pattern [, max ])
```

## Paramètres

**URL** Adresse du serveur FTP sous forme d’URL.

**pattern** Fichier et masque de la liste des fichiers à récupérer.

**max** Nombre maximal de fichiers à renvoyer. Si ce paramètre est manquant, la méthode renvoie la liste complète des fichiers.

## Valeur renvoyée

Un tableau contenant les noms de fichiers correspondant au chemin d’accès et au masque spécifiés.

## Remarques

Si la commande FTP échoue et qu’une exception est générée. Exemple:

```javascript
var ftp = new FTP
var files = ftp.list("ftp://ftp.funet.fi/", "pub/standards/RFC/rfc*.txt", 10)
for(var i in files)
  logInfo(files[i])
ftp.dispose()
```

## Fonctionnalités

**Méthode de classe :** [FTP](c-ftp.md)

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
