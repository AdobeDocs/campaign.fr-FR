---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 4%
---
# Iconbox

Liste des icônes permettant de sélectionner plusieurs pages.

![Contrôle Iconbox](assets/iconbox.05daa4bf.png)

## Propriétés

**backColor - string** Couleur d&#39;arrière-plan (ombre btn, blanc).

**name - chaîne** ID de conteneur.

**marge intérieure-gauche - entier** Espace en pixel à gauche du conteneur.

**marge intérieure-droite - entier** Espace en pixel à droite du conteneur.

**padding-top - entier** Espace en pixel au-dessus du conteneur.

**marge intérieure inférieure - entier** Espace en pixel sous le conteneur.

**marge intérieure - entier** Espace en pixel autour du conteneur.

**readOnly - boolean** Force le contrôle et tous ses descendants à ne lire que.

## Remarques

Chaque sous-élément de conteneur représente une page. Exemple:

```xml
<container name="iconbox" type="iconbox">
   <container colcount="3" label="Header">
     ...
   </container>
   <container img="ncm:ctprop.bmp" label="Intro">
     ...
   </container>
   <container img="ncm:subsection.bmp" label="Event">
     ...
   </container>
   <container img="ncm:book.bmp" label="Selection">
     ...
   </container>
   <container img="nms:contacts.bmp" label="Services">
     ...
   </container>
   <container img="nms:contacts.bmp" label="Mail footer ">
     ...
   </container>
 </container>
```
