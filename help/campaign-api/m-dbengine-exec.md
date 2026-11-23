---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 23%
---
# exec

Alias de la commande d’exécution. Cette fonction est obsolète. Utilisez [execute()](m-dbengine-execute.md).

```text
exec (command [, value1, ... ])
```

## Paramètres

**commande** commande SQL.

**value1, ...** Variables de la commande.

## Valeur renvoyée

Le nombre d&#39;enregistrements mis à jour ou insérés si cela s&#39;applique à la commande exécutée, sinon zéro.

## Fonctionnalités

**Méthode de classe :** [DBEngine](c-dbengine.md)

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
