---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '67'
ht-degree: 20%
---
# intégrité

Renvoie le type d’intégrité du lien.

```text
integrity
```

## Remarques

La propriété peut prendre l’une des valeurs suivantes :

* Schema.INTEGRITY\_NORMAL - Lien de type « Normal ».
* Schema.INTEGRITY\_DEFINE - Lien de type « Define ».
* Schema.INTEGRITY\_NEUTRAL - Lien de type « neutral ».
* Schema.INTEGRITY\_USED - Lien de type « used ».
* Schema.INTEGRITY\_OWN - Lien de type « own ».
* Schema.INTEGRITY\_OWNCOPY - Lien de type « owncopy ».

## Fonctionnalités

**Propriété de la classe :** [SchemaNode](c-schemanode.md)

**Lecture seule :**

Oui

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
