---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 9%
---
# ajouter

Ajoute une nouvelle entité à la collection.

```text
add ( [index ], xml)
```

## Paramètres

**index** L&#39;entité sera ajoutée à ce point d&#39;index. Si cet argument n&#39;est pas spécifié, l&#39;entité est ajoutée à la fin de la liste.

**xml** Entité à insérer au format XML.

## Valeur renvoyée

L’élément créé.

## Remarques

L’exemple suivant montre deux manières différentes d’ajouter un nouvel élément à une collection. La première solution transmet la définition complète de l’élément à la méthode add(), tandis que la seconde transmet et vide l’élément &lt;attachment/> ; elle attribue ensuite les attributs de manière normale.

```javascript
var delivery = NLWS.nmsDelivery.load("12435")

delivery.attachment.add(
  {attachment: {
    compressMode: "print", filterActive: "false", label: "First File", 
    nameScriptActive: "false", type: "normal", upload: "false", 
    name: { $: "file1.txt" }
  }})

var attach = delivery.attachment.add()
attach.label            = "Second File"
attach.name             = "file2.txt"
attach.compressMode     = "print"
attach.type             = "normal"
attach.filterActive     = false
attach.nameScriptActive = false
attach.upload           = false

delivery.save()
```

Les deux solutions sont équivalentes, mais la seconde permet d&#39;utiliser les types JavaScript correspondant aux types d&#39;attribut, alors que la première ne prend en charge que les chaînes.

## Fonctionnalités

**Méthode de la classe :** [EntityCollection](c-entitycollection.md)

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
