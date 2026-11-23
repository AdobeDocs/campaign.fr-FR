---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 15%
---
# Démarrer

Lance une requête en mode asynchrone.

```text
start (context, name, ...)
```

## Paramètres

**context** Tout paramètre utilisateur qui sera transféré à la fonction [complete](p-soapservice-complete.md).

**name** Nom de la méthode à appeler.

**...** Paramètres de la fonction.

## Valeur renvoyée

La requête créée. Cet objet n&#39;a aucune propriété ni fonction. Il est utile pour la fonction [wait](m-soapservice-wait.md) qui vous permet d&#39;attendre la fin d&#39;une opération.

## Remarques

La connexion au service doit être asynchrone. Si la connexion est bloquante, une exception est générée. Les requêtes ne peuvent pas être exécutées si une autre requête est en cours d’exécution sur la connexion. Dans ce cas, une exception est générée.

## Fonctionnalités

**Méthode de classe :** [SoapService](c-soapservice.md)

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
