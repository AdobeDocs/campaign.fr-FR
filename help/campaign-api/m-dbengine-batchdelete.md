---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '65'
ht-degree: 23%
---
# batchDelete

Efface par paquets les enregistrements d&#39;une table.

```text
batchDelete (table, pk [, where ])
```

## Paramètres

**table** Nom SQL de la table.

**pk** Nom du champ utilisé comme clé primaire.

**où** condition de filtrage des enregistrements SQL.

## Valeur renvoyée

Aucune.

## Remarques

Exemple:

```javascript
      engine.batchDelete("NmsRecipient", "iRecipientId", "sName IS NULL")
```

L&#39;opérateur a besoin des droits &#39;sql&#39; pour utiliser cette fonction, sinon une exception est levée.

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
