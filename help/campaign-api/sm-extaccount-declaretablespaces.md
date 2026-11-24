---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 39%
---
# DeclaredTableSpaces

Déclare dans la base Adobe Campaign les options permettant d&#39;utiliser des tablespaces spécifiques dans la base distante accéssible par l&#39;intermédiaire du compte externe

```text
DeclareTableSpaces ( String extAccountId, String tableSpace, String tableSpaceIndex )
```

## Paramètres

**extAccountId** Nom interne ou clé primaire du compte externe

**tableSpace** Nom du tablespace à utiliser pour les tables de travail distantes

**tableSpaceIndex** Nom de l&#39;espace disque logique à utiliser pour les index

## Valeur(s) renvoyée(s)

Aucune.

## Fonctionnalités

**Schéma :** [nms:extAccount](s-nms-extaccount.md)

**Statique :**

Oui
