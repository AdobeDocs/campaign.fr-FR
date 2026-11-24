---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 2%
---
# VPaned

Dispose plusieurs conteneurs horizontalement.

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

Chaque sous-élément doit être un conteneur. Chaque sous-conteneur peut spécifier le pourcentage de la largeur totale qu’il souhaite utiliser à l’aide de la propriété width-percent . Exemple:

```xml
<container type="vpaned">
  <container label="Group 1" width-percent="25"/>
    <input .../>
  </container>
  <container label="Group 2" width-percent="75"/>
    <input .../>
  </container>
</container>
```
