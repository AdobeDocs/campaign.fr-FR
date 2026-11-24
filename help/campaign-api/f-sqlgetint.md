---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 8%
---
# sqlGetInt

Retourne l&#39;entier issu d&#39;une requête SQL.

```text
sqlGetInt (query [, value1, ... ])
```

## Paramètres

**requête** La requête SQL.

**value1, ...** variables de la requête SQL.

## Valeur renvoyée

Valeur entière correspondant à la requête.

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

* $(id) Génère un identifiant
* $(id:NmsTrackingLogId) Génère un identifiant à l’aide d’une séquence spécifique
* $(curdate) Date et heure actuelles

L’utilisation de variables ne modifie pas les performances d’Adobe Campaign. La requête SQL doit sélectionner une seule ligne et un seul champ de type texte. L&#39;opérateur doit disposer du droit &#39;sql&#39; pour utiliser cette fonction, sinon une exception est levée. Exemple:

```javascript
      var age = sqlGetInt('select sAge from nmsRecipient where sEmail =$(sz) order by tsCreated DESC LIMIT 1', email)
var iRecipientId = sqlGetInt("select irecipientId FROM NmsRecipient WHERE sLastName=$(sz) and tsCreated>$(ts)", strName);
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
