---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 30%
---
# lecture

Lit une ligne du fichier texte.

```text
readln ()
```

## Paramètres

Aucune.

## Valeur renvoyée

Chaîne contenant la ligne suivante du fichier ou ⌐null si la fin du fichier est atteinte.

## Remarques

Exemple:

```javascript
var f = new File("c:/dummy.xml")
f.open("r", File.CODEPAGE_UTF8)
var line
while( line = f.readln() )
  logInfo(line)
f.close()
```

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
