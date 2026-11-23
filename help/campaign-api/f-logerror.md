---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 20%
---
# logError

Ajoute un message d’erreur au journal de l’instance de workflow et suspend l’exécution du script.

```text
logError (message)
```

## Paramètres

**message** Message à ajouter au journal.

## Valeur renvoyée

Aucune.

## Remarques

La tâche en cours se comporte comme si une erreur s’était produite : une erreur est marquée et le workflow est suspendu. Cette fonction est donc utile pour générer explicitement une erreur sur un workflow et pour le suspendre.

## Fonctionnalités

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
