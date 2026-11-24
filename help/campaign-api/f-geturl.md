---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 16%
---
# getUrl

Récupère un contenu texte depuis une URL.

```text
getUrl (url [, timeout ])
```

## Paramètres

**url** Adresse de la page à récupérer.

**délai d’expiration de la connexion**. Si la connexion ne peut pas être établie dans le délai donné, une erreur est générée et le script est interrompu.

## Valeur renvoyée

Chaîne de caractères contenant la page de texte.

## Remarques

L’encodage de la chaîne renvoyée est l’encodage spécifié par la réponse (Content-Type). Si une erreur se produit lors du téléchargement ou si le code de retour n’est pas égal à 200 (OK), une erreur est générée et le script en cours d’exécution est interrompu. Exemple:

```javascript
      var content = getUrl("http://www.google.com/index.html")
```

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
