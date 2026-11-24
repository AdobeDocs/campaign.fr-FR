---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 9%
---
# sqlExec

Exécute un script SQL.

```text
sqlExec (query [, value1, ... ])
```

## Paramètres

**requête** La requête SQL.

**value1, ...** variables de la requête SQL.

## Valeur renvoyée

Le nombre d&#39;enregistrements mis à jour ou insérés dans le cas d&#39;une commande UPDATE ou INSERT SQL.

## Remarques

Les variables remplacent les paramètres dans la commande . Le type de variable doit correspondre au paramètre déclaré dans la commande . Ces variables sont disponibles dans une déclaration de type « select » ou « update ». Nous avons les types suivants :

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

Les paramètres de substitution suivants (valides uniquement pour une « mise à jour ») sont automatiquement remplacés par une valeur et n’ont pas besoin de variable liée.

* $(id) générer un identifiant
* $(id:NmsTrackingLogId) génère un identifiant à l’aide d’une séquence spécifique
* $(curdate) date et heure actuelles

L&#39;opérateur doit disposer du droit &#39;sql&#39; pour utiliser cette fonction, sinon une exception est levée. Exemple:

```javascript
      var sql4 = "INSERT INTO Reporting (sClientdesc,sClient) values ('" + client.@description.toString() + "','" + client.@clientCode.toString() +"')";
sqlExec(sql4);
```

## Fonctionnalités

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
