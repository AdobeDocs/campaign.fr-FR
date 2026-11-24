---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 3%
---
# HttpServletRequest (classe)

Représente la requête d’un client transférée vers une servlet.

Il n&#39;y a qu&#39;une seule instance de cette adresse accessible via le `request`. variable.

## Méthodes

| Méthode | Description |
| --- | --- |
| [getHeader](m-httpservletrequest-getheader.md) | Renvoie un attribut défini dans l’en-tête de la requête. |
| [getParameter](m-httpservletrequest-getparameter.md) | Renvoie la valeur d’un paramètre de requête. |
| [getRemoteAddr](m-httpservletrequest-getremoteaddr.md) | Renvoie l’adresse IP du client ou du dernier proxy à avoir envoyé une requête. |
| [paramètre getUTF8](m-httpservletrequest-getutf8parameter.md) | Renvoie la valeur (codée en UTF-8) d’un paramètre de la requête. |
| [getBodyAsString](m-httpservletrequest-getbodyasstring.md) | Renvoie le corps de la requête sous la forme d’une chaîne de caractères à l’aide du codage de requête. |
| [suivant](m-httpservletrequest-forward.md) | Redirige la requête vers une autre page sans passer par le client. |

## Propriétés

| Propriété | Description |
| --- | --- |
| [paramètres](p-httpservletrequest-parameters.md) | Renvoie les paramètres de la requête. |
| [cookies](p-httpservletrequest-cookies.md) | Retourne les cookies de la requête. |
| [requestURI](p-httpservletrequest-requesturi.md) | Renvoie l’URL de la requête. |
| [queryString](p-httpservletrequest-querystring.md) | Retourne la partie de l&#39;URL de la requête correspondant aux paramètres. |
| [schéma](p-httpservletrequest-scheme.md) | Renvoie le nom du protocole utilisé (HTTP, HTTPS, etc.) pour accéder à cette page. |
| [serverName](p-httpservletrequest-servername.md) | Renvoie le nom du serveur de requête. |
| [serverPort](p-httpservletrequest-serverport.md) | Renvoie le numéro de port utilisé pour contacter le serveur. |
| [serverURL](p-httpservletrequest-serverurl.md) | Retourne l’URL d’accès au serveur. |
| [servletPath](p-httpservletrequest-servletpath.md) | Renvoie la section de l’URL de la requête correspondant au servlet. |
| [contextPath](p-httpservletrequest-contextpath.md) | Retourne la section de l&#39;URL de la requête correspondant au contexte. |
| [pathInfo](p-httpservletrequest-pathinfo.md) | Retourne les informations additionnelles de l’URL de la requête. |
| [méthode](p-httpservletrequest-method.md) | Renvoie une chaîne de caractères contenant la méthode HTTP utilisée pour appeler cette requête (GET, HEAD, POST, etc.). |

## Fonctionnalités

**Disponible en :**

* JSSP
* WEBAPP
