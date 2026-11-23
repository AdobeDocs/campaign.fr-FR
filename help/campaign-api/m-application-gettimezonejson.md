---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 7%
---
# getTimezoneJson

Renvoie une chaîne de caractères qui est la représentation JSON de la liste des différences temporelles avec l’heure UTC et leur date de début par rapport à la période UNIX pour un fuseau horaire.

```text
getTimezoneJson ( [timezone ])
```

## Paramètres

**fuseau horaire** Nom du fuseau horaire pour lequel vous devez renvoyer la liste des différences horaires par rapport à UTC. Chaque décalage horaire est associé à une date de début applicable jusqu’à la date de début suivante. Si aucune valeur n’est renvoyée, utilise le fuseau horaire de l’opérateur par défaut.

## Valeur renvoyée

Renvoie une chaîne de caractères qui est la représentation JSON des différences temporelles à appliquer en fonction des dates. La chaîne JSON renvoyée est évaluée dans un tableau de {startDate, offset} couples. La chaîne de caractères renvoyée est de la forme suivante :

```javascript
[
  {"startDate" : -1855958901000, "offset" : 0},
  {"startDate" : -1689814800000, "offset" : 3600000}
]
```

* startDate correspond à l’heure postale à partir de laquelle l’expiration s’applique.
* offset est la valeur en millisecondes de la différence temporelle avec UTC. Par exemple UTC+02:00 est égal à 7200000.

## Remarques

getTimezoneJson est appelé via l’instance de l’application.

```javascript
var tzList = eval(application.getTimezoneJson());
```

## Fonctionnalités

**Méthode de classe :** [Application](c-application.md)

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
