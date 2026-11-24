---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 7%
---
# Application (Classe)

Cette classe comporte une seule instance qui permet d’accéder à certaines propriétés du serveur d’applications. Ce singleton est accessible via la variable globale `application`.

## Méthodes

| Méthode | Description |
| --- | --- |
| [hasPackage](m-application-haspackage.md) | Teste si un package est installé. |
| [getSchema](m-application-getschema.md) | Retourne un mapping sur un schéma Adobe Campaign ou null si le schéma n’existe pas. |
| [getDBMSType](m-application-getdbmstype.md) | Renvoie le type de serveur de la base de données. |
| [getNewIds](m-application-getnewids.md) | Retourne une liste d’identifiants des clés de la base interne. |
| [getConnection](m-application-getconnection.md) | Retourne une nouvelle connexion au serveur de base de données. |
| [getTimezoneJson](m-application-gettimezonejson.md) | Renvoie une chaîne de caractères qui est la représentation JSON de la liste des différences temporelles avec l’heure UTC et leur date de début par rapport à la période UNIX pour un fuseau horaire. |
| [onLog](m-application-onlog.md) | Ajoute ou supprime une fonction d&#39;interception des messages écrits dans le journal |
| [onTrace](m-application-ontrace.md) | Ajoute ou supprime une fonction d&#39;interception de messages de trace. |

## Propriétés

| Propriété | Description |
| --- | --- |
| [buildNumber](p-application-buildnumber.md) | Renvoie le numéro de build du serveur d’applications. |
| [instanceName](p-application-instancename.md) | Nom de l’instance sur laquelle le script est exécuté. |
| [instanceVarDir](p-application-instancevardir.md) | Chemin complet du répertoire &#39;var&#39; de l&#39;instance d&#39;exécution du script. |
| [instanceUploadDir](p-application-instanceuploaddir.md) | Chemin complet du répertoire &#39;upload&#39; pour l&#39;instance sur laquelle s&#39;exécute le script. |
| [opérateur](p-application-operator.md) | Renvoie un objet contenant des informations sur l’opérateur courant (nom, identifiants, droits, etc.). |
| [paramètres régionaux](p-application-locale.md) | Renvoie une chaîne de caractères correspondant à l’instance locale. |

## Fonctionnalités

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
