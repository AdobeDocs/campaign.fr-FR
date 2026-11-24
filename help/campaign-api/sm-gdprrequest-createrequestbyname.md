---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 29%
---
# CreateRequestByName

Créer une demande RGPD en utilisant le nom interne de l&#39;espace de noms

```text
Number id = CreateRequestByName ( String namespaceName, String reconciliationValue, Number type, Boolean confirmDeletePending )
```

## Paramètres

**namespaceName** Nom interne de l’espace de noms

**reconciliationValue** Valeur de réconciliation

Valeur de réconciliation **type**

**confirmDeletePending** Demande de confirmation avant la suppression des données

## Valeur(s) renvoyée(s)

**id** ID de la demande nouvellement créée

## Fonctionnalités

**Schéma :** [nms:gdprRequest](s-nms-gdprrequest.md)

**Statique :**

Oui
