---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 4%
---
# generateTrackingTag

Génère automatiquement une balise JavaScript pour le tracking Web.

```text
generateTrackingTag (request [, tagid ] [, folder ])
```

## Paramètres

**request** Objet HttpServletRequest

**tagid** Chaîne de caractères représentant le nom de l’ID de balise personnalisé. S’il est vide, la fonction génère la balise en fonction du nom du chemin d’accès.

**dossier** Chaîne de caractères représentant le nom interne d’un dossier. S&#39;il est vide, la balise est créée dans le répertoire par défaut, à savoir « Balises de tracking Web ».

## Valeur renvoyée

Chaîne de caractères contenant le code JavaScript à inclure.

## Remarques

La balise générée est basée sur le nom de l&#39;application web, de la page html, du contrôleur ou plus généralement, du chemin d&#39;accès si l&#39;identifiant de balise n&#39;est pas renseigné. Le dernier paramètre spécifie le dossier de destination de balise. Pour appeler la fonction , transmettez l’objet de requête en tant qu’argument. Notez l&#39;utilisation de &lt;%==, car la fonction génère du code HTML. Exemple:

```xml
              <%== generateTrackingTag(request, request.getParameter('art'), request.getParameter('cat')) %>
```

## Fonctionnalités

**Disponible en :**

* JSSP
* WEBAPP
