---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 31%
---
# charger

Téléchargez un fichier depuis un fichier local vers un serveur FTP.

```text
upload (URL)
```

## Paramètres

**URL** URL du serveur.

## Valeur renvoyée

Aucune.

## Remarques

L’URL doit commencer par « ftp:&#39; Exemple :

```javascript
var ftp = new FTP
ftp.setFile("c:/rfc.txt")
ftp.upload("ftp://ftp.funet.fi/pub/standards/RFC")
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
