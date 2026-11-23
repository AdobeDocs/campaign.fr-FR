---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '38'
ht-degree: 21%
---
# InstallPackage

Installer un package.

```text
InstallPackage ( XML parameters )
```

## Paramètres

Élément XML **parameters** contenant le package à importer.

## Valeur(s) renvoyée(s)

Aucune.

## Remarques

Un package généré par la méthode SpecFile.Generate() doit être encapsulé dans un élément builder. Exemple:

```javascript
var params =
  {builder:
    {package:
      { ... }
    }
  }

NLWS.xtkBuilder.InstallPackage(params)
```

## Fonctionnalités

**Schéma :** [xtk:builder](s-xtk-builder.md)

**Statique :**

Oui
