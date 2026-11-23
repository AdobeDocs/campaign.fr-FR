---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 23%
---
# toXML

Renvoie un objet XML JavaScript obtenu à partir du contenu de [MemoryBuffer](c-memorybuffer.md). Cette fonction est obsolète. Utilisez [toDocument()](m-memorybuffer-todocument.md).

```text
toXML ( [codePage ])
```

## Paramètres

**codePage** Entier codant la page de caractères utilisée. Par défaut, MemoryBuffer.CODEPAGE\_UTF8.

## Valeur renvoyée

Contenu d’un tampon sous la forme d’un objet XML.

## Fonctionnalités

**Méthode de classe :** [MemoryBuffer](c-memorybuffer.md)

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
