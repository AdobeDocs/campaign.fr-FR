---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 38%
---
# LoadExpandedContents

Charge une liste composants pour le pré-traitement avec leurs dépendances (blocs de personnalisation, options, objets de script additionnels...).

```text
XML material = delivery.LoadExpandedContents ( String ids ) const
```

## Paramètres

**ids** Liste d’identifiants de composant séparés par des virgules (par exemple, « option\|NmsServer\_URL\|text,includeView\|UnsubscriptionLink\|html »).

## Valeur(s) renvoyée(s)

**material** Renvoie le contenu sous la forme d&#39;un élément &#39;material&#39;.

## Fonctionnalités

**Schéma :** [nms:delivery](s-nms-delivery.md)

**Statique :**

Non

**Const :**

Oui

**Clé uniquement :**

Non
