---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '27'
ht-degree: 18%
---
# assessmentTemplate

Évalue un modèle JavaScript (&lt;%= ... %>).

```text
evaluateTemplate (template)
```

## Paramètres

**template** Le modèle à évaluer.

## Valeur renvoyée

Chaîne après substitution des expressions entre &lt;% et %>.

## Remarques

Exemple:

```javascript
      vars.filename = evaluateTemplate(activity.filename)
```

## Fonctionnalités

**Disponible en :**

* Workflow
