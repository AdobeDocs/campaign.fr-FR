---
source-git-commit: 77f8182ea5b1fda08206021a164b2e0ff827890a
workflow-type: tm+mt
source-wordcount: '72'
ht-degree: 22%
---
# getEnv

>[!WARNING]
>
>Cette fonction est disponible pour un environnement On-Premise.

>[!NOTE]
>
>Vous pouvez désactiver cette fonction en transmettant l’option **XtkSecurity\_Disable\_GetSetEnv** à **true**.

Renvoie la valeur d’une variable d’environnement.

```text
getEnv (name [, default ])
```

## Paramètres

**name** Nom de la variable.

**default** Valeur par défaut à utiliser si la variable d&#39;environnement est introuvable.

## Valeur renvoyée

Valeur de la variable.

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
