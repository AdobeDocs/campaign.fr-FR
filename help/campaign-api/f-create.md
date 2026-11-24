---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '93'
ht-degree: 17%
---
# créer

Crée une nouvelle entité correspondant à un schéma donné.

```text
create ( [content ])
```

## Paramètres

**content** Chaîne de caractères facultative correspondant au XML de l’entité à créer.

## Valeur renvoyée

Renvoie l’entité sous la forme d’un objet JavaScript.

## Remarques

create n’est pas une fonction globale, mais une méthode de schéma. Pour l’appeler, vous devez lui ajouter le préfixe du schéma souhaité. Par exemple :

```javascript
var recipient = NLWS.nmsRecipient.create(
      {recipient: {
        email: "support@adobe.com", 
        lastName: "Adobe", 
        firstName: "Support"}})
recipient.save()
```

Le document n’est pas automatiquement enregistré dans la base de données. Vous devez utiliser la méthode ⌐⌐[save()](m-entity-save.md) sur l&#39;entité.

## Fonctionnalités

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
