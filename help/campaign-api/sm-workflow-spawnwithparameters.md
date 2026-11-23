---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 3%
---
# SpawnWithParameters

Crée une instance de workflow à partir d&#39;un modèle puis invoque la méthode [StartWithParameters](sm-workflow-startwithparameters.md) sur cette instance.

```text
Number instanceId = SpawnWithParameters ( String workflowId, XML parameters )
```

## Paramètres

**workflowId** Identifiant ou nom interne du modèle de workflow.

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

**instanceId** Identifiant de l’instance créée à partir du modèle.

## Remarques

La commande est exécutée en mode asynchrone et n’a pas d’effet immédiat après le retour de la méthode. Le workflow est démarré avec le compte de l&#39;opérateur appelant sauf si un login spécifique est associé au modèle dans la table des login de workflows auquel cas, c&#39;est ce dernier qui est utilisé.

## Fonctionnalités

**Schéma :** [xtk:workflow](s-xtk-workflow.md)

**Statique :**

Oui
