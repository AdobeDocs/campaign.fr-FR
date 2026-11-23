---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 37%
---
# escapeXmlStr

Convertit une chaîne de caractères au format XML.

```text
escapeXmlStr (value)
```

## Paramètres

**value** Chaîne de caractères à convertir.

## Valeur renvoyée

Chaîne de caractères après la conversion.

## Remarques

La fonction transforme les caractères &amp;, &lt;, > et \\ » en séquences d’échappement correspondantes :

* &amp;
* &lt; &lt;
* > >
* &quot; &amp;quot;

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
