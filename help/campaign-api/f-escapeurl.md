---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 21%
---
# escapeUrl

Convertit une chaîne de caractères pour l’insérer dans une URL.

```text
escapeUrl (value)
```

## Paramètres

**value** Chaîne de caractères à convertir.

## Valeur renvoyée

Chaîne de caractères après la conversion.

## Remarques

La fonction transforme des caractères non alphanumériques autres que $-\_.\!\*&#39;(),?/:@&amp;= en valeur hexadécimale correspondante. La fonction est conforme à la spécification RFC1738 et vous permet uniquement d’encoder des caractères ISO-latins. Pour coder des caractères UTF-8, utilisez la fonction JavaScript encodeURIComponent() . Exemple:

```javascript
escapeUrl("a#value!")               // "a%23value!"
escapeUrl("Système d'exploitation") // "Syst%E8me%20d'exploitation"
```

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
