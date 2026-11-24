---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 5%
---
# getAsModel

```text
XML parentOut = getAsModel ( String refIdName, Number refIdValue, XML selection, XML parentIn )
```

## Paramètres

**refIdName** Attribut contenant l&#39;identifiant de l&#39;entité à associer (par exemple &#39;delivery-id&#39;)

**refIdValue** Identifiant de l&#39;entité à associer (valeur de &#39;refIdName&#39;)

Élément **selection** contenant les identifiants des modèles sélectionnés

Élément **parentIn** contenant les adresses de contrôle existantes

## Valeur(s) renvoyée(s)

**parentOut** renvoie l’élément avec les nouveaux modèles ajoutés

## Fonctionnalités

**Schéma :** [nms:seedMember](s-nms-seedmember.md)

**Statique :**

Oui
