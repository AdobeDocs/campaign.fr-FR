---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 2%
---
# HPaned

Dispose plusieurs conteneurs verticalement.

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

Chaque sous-élément doit être un conteneur. Chacun de ses sous-conteneurs peut spécifier le pourcentage de la hauteur totale qu’il souhaite utiliser à l’aide de la propriété height-percent . Exemple:

```xml
<container type="hpaned">
  <container label="Group 1" height-percent="25"/>
    <input .../>
  </container>
  <container label="Group 2" height-percent="75"/>
    <input .../>
  </container>
</container>
```
