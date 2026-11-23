---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 10%
---
# Schéma (Classe)

Représente la définition du schéma.

Un schéma est obtenu en appelant la méthode de la variable globale `application`. Une instance de cet objet possède un objet en tant que prototype et hérite donc de ses méthodes.

## Méthodes

| Méthode | Description |
| --- | --- |
| [versDocument](m-schema-todocument.md) | Convertit le schéma en formulaire de document XML. |

## Propriétés

| Propriété | Description |
| --- | --- |
| [énumérations](p-schema-enumerations.md) | Renvoie la table contenant la liste des [énumérations](c-enumeration.md) définies dans ce schéma. |
| [id](p-schema-id.md) | Identifiant du schéma sous la forme d’une chaîne. |
| [isLibrary](p-schema-islibrary.md) | Renvoie une valeur booléenne qui spécifie si le schéma est une bibliothèque de composants. |
| [labelSingular](p-schema-labelsingular.md) | Nom unique du schéma sous la forme d’une chaîne. |
| [mappingType](p-schema-mappingtype.md) | La nature du mapping de schéma sous la forme d&#39;une chaîne |
| [md5](p-schema-md5.md) | Le code MD5 du schéma sous la forme d’une chaîne hexadécimale. |
| [espace de noms](p-schema-namespace.md) | Espace de noms du schéma sous la forme d’une chaîne. |
| [root](p-schema-root.md) | Elément principal du schéma ou null s&#39;il n&#39;est pas défini. |
| [userDescription](p-schema-userdescription.md) | Description du schéma sous la forme d’une chaîne. |

## Fonctionnalités

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
