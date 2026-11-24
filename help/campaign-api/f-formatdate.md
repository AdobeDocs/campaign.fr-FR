---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 7%
---
# formatDate

Met en forme une date sous forme de chaîne de caractères.

```text
formatDate (date, format [, timeZone ])
```

## Paramètres

**date** Date à convertir.

**format** Chaîne de caractères décrivant le format à utiliser. Les caractères utilisés pour mettre en forme les différentes parties de la date sont les suivants :

* Y - Année
* M - Mois de l&#39;année (1-12)
* B - Nom du mois
* D - Jour du mois (1-31)
* A - Nom du jour
* J - Jour de l’année (1-366)
* W - Semaine de l’année
* H - Heure (0-23)
* I - Heure (1-12)
* N - Minutes (0-59)
* S - Secondes (0-59)
* P - AM/PM

Vous pouvez spécifier un nombre devant certains de ces caractères. Les caractères A et B peuvent être suivis d’un l pour utiliser le nom complet plutôt que la version abrégée, ou d’un i pour utiliser le nom en anglais. Exemples:

* « %4Y/%2M/%2D » => 2000/01/24.
* « %A %D %B %4Y » => le 24 janvier 2000.
* « %Al %D %Bl %4Y » => lundi 24 janvier 2000.
* « %02H:%02N:%02S » affiche l&#39;heure, les minutes et les secondes à deux chiffres.

**timeZone** Chaîne de caractères correspondant au fuseau horaire. Les valeurs possibles sont spécifiées dans le schéma d&#39;énumération xtk:common:timezone .

## Valeur renvoyée

Chaîne de caractères représentant la date au format demandé.

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
