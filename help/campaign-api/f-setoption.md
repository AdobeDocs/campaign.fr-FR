---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 12%
---
# setOption

Modifie la valeur d’une option dans le tableau des options.

```text
setOption (name, value, description )
```

## Paramètres

**nom** Nom de l’option.

**value** Valeur de l’option.

**description** Valeur de la description (facultatif).

## Valeur renvoyée

Aucune.

## Remarques

Les différents types de données sont les suivants :

* texte,
* nombre entier,
* virgule flottante
* Date + Heure,
* texte long

Notez que longText et le type entier ne peuvent pas être créés à partir de l’API.

Pour ces deux types, vous devez d’abord créer l’option à partir de la console, puis vous pouvez gérer les valeurs via l’API setOption.

**Exemple:**

```javascript
               //create option of type Date+Time'
               var ourDate = getCurrentDate();
               setOption("testOptionDateTime",ourDate,"option of type Date+Time");
                              
               //create option of type Floating point'
               setOption("testOptionFloat",1,"option of type Floating point");
               
               //create option of type Text'
               setOption("testOptionText","I am a text","option of type Text");               
           
```

Si vous souhaitez supprimer la description, vous devez appeler l’API avec une description vide (setOption(name,value, » »).

## Fonctionnalités

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
