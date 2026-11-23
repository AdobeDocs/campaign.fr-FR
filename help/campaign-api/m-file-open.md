---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 9%
---
# ouvert

Ouvre le fichier en mode lecture ou écriture.

```text
open ( [mode ] [, codepage ])
```

## Paramètres

**mode** Mode d&#39;ouverture de fichier. Le mode peut prendre plusieurs valeurs :

* « r » - Ouvre le fichier en mode lecture seule. Ce mode est le mode par défaut.
* « w » : ouvre le fichier en mode écriture.
* « a » - Ouvre le fichier en mode &#39;append&#39;, les données écrites dans le fichier sont ajoutées à la fin.

**codepage** Encodage du fichier. L’encodage peut être l’une des valeurs suivantes :

* File.CODEPAGE\_CURRENT - Il s’agit de la page de code par défaut.
* File.CODEPAGE\_OEM
* File.CODEPAGE\_MAC
* File.CODEPAGE\_THREAD
* File.CODEPAGE\_LATIN1
* File.CODEPAGE\_LATIN2
* File.CODEPAGE\_ISOLATIN1
* File.CODEPAGE\_ISOLATIN2
* File.CODEPAGE\_OEMLATIN1
* File.CODEPAGE\_OEMLATIN2
* File.CODEPAGE\_UTF7
* File.CODEPAGE\_UTF8
* File.CODEPAGE\_ISOLATIN9
* File.CODEPAGE\_OEMUS
* File.CODEPAGE\_SHIFTJIS
* File.CODEPAGE\_BIG5
* File.CODEPAGE\_CHINESE
* File.CODEPAGE\_EUCKOREAN
* File.CODEPAGE\_UTF16LE
* File.CODEPAGE\_UTF16BE

## Valeur renvoyée

Aucune.

## Remarques

Si le fichier ne peut pas être ouvert, une exception est générée.

## Fonctionnalités

**Méthode de classe :** [Fichier](c-file.md)

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
