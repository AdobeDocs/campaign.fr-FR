---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 12%
---
# HttpClientResponse (Classe)

Objet représentant la réponse à une requête HTTP.

Ne peut être obtenu qu&#39;après l&#39;exécution d&#39;une requête HTTP par la propriété `response`.

## Propriétés

| Propriété | Description |
| --- | --- |
| [corps](p-httpclientresponse-body.md) | Corps de la réponse HTTP sous la forme d’un objet MemoryBuffer. |
| [code](p-httpclientresponse-code.md) | Code de retour de la réponse HTTP sous la forme d’un entier JavaScript. |
| [codePage](p-httpclientresponse-codepage.md) | Valeur de codePage de la réponse. Utilisé pour décoder le corps de la réponse HTTP. |
| [en-tête](p-httpclientresponse-header.md) | Un objet contenant tous les en-têtes HTTP. |
| [en-têtes](p-httpclientresponse-headers.md) | La liste des en-têtes pour la réponse HTTP regroupée par nom. |
| [message](p-httpclientresponse-message.md) | Message transmis par la réponse HTTP. |

## Fonctionnalités

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
