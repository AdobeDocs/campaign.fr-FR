---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 5%
---
# StartWithParameters

Démarre un workflow et lui fournit des paramètres.

```text
StartWithParameters ( String workflowId, XML parameters )
```

## Paramètres

**workflowId** Identifiant ou nom interne du workflow.

**paramètres** Paramètres à transmettre à l’instance. Ces paramètres deviendront les variables d’instance du workflow. Cet argument est un élément XML dont le nom doit être des variables et ne peut inclure que des attributs. Exemple:

```xml
<variables foo="abc" bar="def">
```

Les scripts JavaScript du workflow peuvent accéder à ces variables à partir de l’objet instance.vars :

```javascript
    var foo = instance.vars.foo   // "abc"
    var bar = instance.vars.bar   // "def"
            
```

## Valeur(s) renvoyée(s)

Aucune.

## Remarques

La commande est exécutée en mode asynchrone, elle n&#39;a pas d&#39;effet immédiat après le retour de la méthode.

## Fonctionnalités

**Schéma :** [xtk:workflow](s-xtk-workflow.md)

**Statique :**

Oui
