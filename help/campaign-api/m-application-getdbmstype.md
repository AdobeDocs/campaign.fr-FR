---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 15%
---
# getDBMSType

Renvoie le type de serveur de la base de données.

```text
getDBMSType ( [name ] [, checkIfUpdated ])
```

## Paramètres

**nom** Nom de la source de données.

**checkIfUpdated** Vérifiez que le schéma a été mis à jour dans le cache. Aucun impact si le schéma est déjà instancié dans le script.

## Valeur renvoyée

Chaîne de texte contenant le type de serveur de la base de données.

## Remarques

Si la source de données n&#39;est pas spécifiée, la fonction utilise &#39;nms:default&#39; par défaut. La source de données doit exister, sinon une exception est générée.

## Fonctionnalités

**Méthode de classe :** [Application](c-application.md)

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
