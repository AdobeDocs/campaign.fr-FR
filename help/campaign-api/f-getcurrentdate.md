---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 31%
---
# getCurrentDate

Retourne la date courante du serveur de base de données.

```text
getCurrentDate ()
```

## Paramètres

Aucune.

## Valeur renvoyée

Date courante du serveur de base de données.

## Remarques

Exemple:

```javascript
      date = formatDate(getCurrentDate(),"%4Y/%2M/%2D %02H:%02N:%02S")
```

Pour plus d&#39;informations sur la fonction formatDate(), reportez-vous à [formatDate(date, format)](f-formatdate.md)

## Fonctionnalités

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
