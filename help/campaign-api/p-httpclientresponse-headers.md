---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 12%
---
# en-têtes

La liste des en-têtes pour la réponse HTTP regroupée par nom.

```text
headers
```

## Remarques

Chaque propriété d’en-tête portait le nom de l’en-tête et la valeur du tableau qui correspond à chaque en-tête portant ce nom. Cette fonction est différente de [header](p-httpclientresponse-header.md), car elle renvoie une table de valeurs au lieu d&#39;une valeur unique pour un nom donné. Cela s’avère utile pour les en-têtes qui peuvent apparaître plusieurs fois, comme Accept-Language ou Set-Cookie. La fonction renvoie un tableau vide si la réponse HTTP ne comporte pas d’en-tête portant ce nom. Exemple:

```javascript
      var http = new HttpClientRequest("http://www.google.com/")
http.execute()
var response = response
var cookies = response.headers["set-cookie"]
for each(var c in cookies)
{
  logInfo("Set-Cookie: " + c)
}
```

les propriétés des en-têtes ne peuvent pas être détaillées. Les noms de propriété ne respectent pas la casse.

## Fonctionnalités

**Propriété de la classe :** [HttpClientResponse](c-httpclientresponse.md)

**Lecture seule :**

Oui

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
