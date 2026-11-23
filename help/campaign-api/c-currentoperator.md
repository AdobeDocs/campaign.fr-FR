---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 12%
---
# CurrentOperator (Classe)

Objet contenant les informations sur l’opérateur courant (nom, identifiants, droits, etc.).

Cette classe comporte une seule instance qui permet d’accéder à certaines propriétés du serveur d’applications. Ce singleton est accessible via la propriété de la variable globale `application`.

Exemple:

```text
var operator = application.operator logInfo("login: " + operator.login) logInfo("id: " + operator.id) logInfo("description: " + operator.computeString) logInfo("=== Groups ===") for each(var id in operator.groups) logInfo(id) logInfo("=== Rights ===") for each(var right in operator.rights) logInfo(right)
```

## Méthodes

| Méthode | Description |
| --- | --- |
| [hasRight](m-currentoperator-hasright.md) | Vérifie si l’opérateur dispose d’un droit nommé spécifique. |

## Propriétés

| Propriété | Description |
| --- | --- |
| [connexion](p-currentoperator-login.md) | Retourne le login de l&#39;opérateur courant |
| [id](p-currentoperator-id.md) | Retourne l’identifiant interne de l’opérateur courant. |
| [computeString](p-currentoperator-computestring.md) | Renvoie la chaîne de description de l’opérateur courant. Par défaut, il s’agit du nom de l’opérateur suivi de son nom d’utilisateur. |
| [groupes](p-currentoperator-groups.md) | Retourne la liste des identifiants des groupes d’opérateurs actifs. |
| [droits](p-currentoperator-rights.md) | Retourne la liste des droits de l&#39;opérateur courant |
| [fuseau horaire](p-currentoperator-timezone.md) | Renvoie le nom du fuseau horaire utilisé par l’opérateur courant. |
| [accueil](p-currentoperator-home.md) | Renvoie le nom du dossier racine de l’opérateur courant. |

## Fonctionnalités

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
