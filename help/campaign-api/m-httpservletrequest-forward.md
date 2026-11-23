---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 6%
---
# en avant

Redirige la requête vers une autre page sans passer par le client.

```text
forward (location)
```

## Paramètres

**emplacement** URL de redirection.

## Valeur renvoyée

Aucune.

## Remarques

forward vous permet d’effectuer un traitement préliminaire avant de transférer la requête vers une autre ressource qui produira le contenu de la réponse. Aucune donnée ne doit avoir été renvoyée au client en réponse à un appel de transfert, sinon une erreur est générée.

## Fonctionnalités

**Méthode de classe :** [HttpServletRequest](c-httpservletrequest.md)

**Disponible en :**

* JSSP
* WEBAPP
