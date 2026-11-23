---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 6%
---
# CreateRequestByName

Créer une demande d’accès à des informations personnelles à l’aide du nom interne de l’espace de noms

```text
Number id = CreateRequestByName ( String namespaceName, String reconciliationValue, Number type, Boolean confirmDeletePending Number regulation )
```

## Paramètres

**namespaceName** Nom interne de l’espace de noms

**reconciliationValue** Valeur de réconciliation

Valeur de réconciliation **type**

**confirmDeletePending** Demande de confirmation avant la suppression des données

**regulation** Type de régulation avec les valeurs suivantes :

```xml
           
               <value label="GDPR" name="gdpr" value="1"/>
            <value label="CCPA" name="ccpa" value="2"/>
            <value label="PDPA" name="pdpa" value="3"/>
            <value label="LGPD" name="lgpd" value="4"/>
           
           
```

## Valeur(s) renvoyée(s)

**id** ID de la demande nouvellement créée

## Fonctionnalités

**Schéma :** [nms:privacyRequest](s-nms-privacyrequest.md)

**Statique :**

Oui
