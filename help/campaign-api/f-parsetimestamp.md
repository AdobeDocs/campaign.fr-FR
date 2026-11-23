---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 17%
---
# parseTimeStamp

Convertit une chaîne de caractères contenant une date formulée à partir d&#39;une version simplifiée de la norme ISO 8601 en un objet de type Date.

```text
parseTimeStamp (aString)
```

## Paramètres

**aString** La date en tant que chaîne de caractères au format ISO 8601.

## Valeur renvoyée

Objet de type Date correspondant à la date définie en tant que paramètre.

## Remarques

La syntaxe est la suivante :

```javascript
              date
              time[time-zone]
            
```

ou

```javascript
              dateTtime[time-zone]
            
```

La date doit avoir le format suivant :

```javascript
YYYY-MM-DD
```

Pour des raisons de compatibilité, le format suivant est également accepté :

```javascript
YYYY/MM/DD
```

L&#39;heure doit avoir le format suivant :

```javascript
hh:mm:ss
hh:mm:ss.nnn
```

Le fuseau horaire, s’il est spécifié, doit avoir le format suivant :

```javascript
Z
+hh:mm
-hh:mm
+hh
-hh
```

Si le fuseau horaire n’est pas spécifié, la date est convertie dans le fuseau horaire actuel (en fonction du contexte). Exemples:

```javascript
2005-03-02 00:00:00
2005-03-02
2005-03-02T14:32:26
2005-03-02T14:32:26.0000
2005-03-02T14:32:26.0000000+01:00
2005-03-02T14:32:26+01:00
2005-03-02T14:32:26Z
2005-03-02T14:32:26.0005Z
2005/03/02 14:32:25
```

Si le format de date n’est pas valide, une exception est générée.

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
