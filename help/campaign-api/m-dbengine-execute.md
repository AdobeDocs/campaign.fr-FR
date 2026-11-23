---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 9%
---
# exécuter

Exécute une commande SQL.

```text
execute (command [, value1, ... ])
```

## Paramètres

**commande** commande SQL.

**value1, ...** Variables de la commande.

## Valeur renvoyée

Le nombre d&#39;enregistrements mis à jour ou insérés le cas échéant par rapport à la commande exécutée, sinon zéro.

## Remarques

Les variables sont utilisées pour remplacer les paramètres de la commande . Le type de variable doit correspondre au type déclaré dans la commande . Les types sont les suivants :

* $(sz) string
* Mémo $(m)
* $(l) long
* $(s) court
* $(b) octet
* $(d) double
* $(f) flottant
* $(ts) date et heure
* $(dt) date
* $(tm) fois
* $(dur) timespan en millisecondes (ms)

Les paramètres de substitution suivants sont automatiquement remplacés par une valeur et ne nécessitent pas de variable associée.

* $(id) Génère un identifiant
* $(id:NmsTrackingLogId) Génère un identifiant grâce à une séquence spécifique
* $(curdate) Date et heure actuelles

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
