---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 21%
---
# nodeValue

Valeur du nœud. La valeur dépend du type de nœud.

```text
nodeValue
```

## Remarques

Cette propriété est accessible avec des autorisations de lecture et d’écriture. Exemple pour récupérer une ligne d&#39;objet et l&#39;ajouter aux données additionnelles d&#39;une activité de requête dans un workflow :

```javascript
      Substring(NodeValue('/delivery/mailParameters/subject/text()',data), 1, 255)
```

Exemple pour récupérer une ligne d&#39;objet d&#39;une activité d&#39;enrichissement dans un workflow :

```javascript
      Substring(NodeValue('/delivery/mailParameters/subject/text()',[target/data]), 1, 255)
```

## Fonctionnalités

**Propriété de la classe :** [DOMNode](c-domnode.md)

**Lecture seule :**

Oui

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
