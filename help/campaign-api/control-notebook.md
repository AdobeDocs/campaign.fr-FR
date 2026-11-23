---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 4%
---
# Notebook

Liste d’onglets pour l’affichage de plusieurs pages.

![Contrôle Notebook](assets/notebook.3b531a46.png)

## Propriétés

**backColor - string** Couleur d&#39;arrière-plan (ombre btn, blanc).

**name - chaîne** ID de conteneur.

**marge intérieure-gauche - entier** Espace en pixel à gauche du conteneur.

**marge intérieure-droite - entier** Espace en pixel à droite du conteneur.

**padding-top - entier** Espace en pixel au-dessus du conteneur.

**marge intérieure inférieure - entier** Espace en pixel sous le conteneur.

**marge intérieure - entier** Espace en pixel autour du conteneur.

**readOnly - boolean** Force le contrôle et tous ses descendants à ne lire que.

**style - chaîne** aplatie \| vers le bas \| vers le haut (par défaut).

## Remarques

Chaque sous-élément représente une page. Exemples:

```xml
      <container colspan="2" style="down" type="notebook">
   <container label="Products">
     ...
   </container>

   <container colcount="3" xpath="link">
     ...
   </container>

   <container xpath="linkCollection">
     ...
   </container>
 </container>
```
