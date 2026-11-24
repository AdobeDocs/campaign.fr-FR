---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 7%
---
# DOMNode (classe)

DOMNode est la classe parente des différents composants qui constituent un document.

## Méthodes

| Méthode | Description |
| --- | --- |
| [insertBefore](m-domnode-insertbefore.md) | Insérez un nœud avant une position spécifique. |
| [replaceChild](m-domnode-replacechild.md) | Remplacez un nœud . |
| [removeChild](m-domnode-removechild.md) | Supprimer un nœud |
| [appendChild](m-domnode-appendchild.md) | Insérer un nœud en fin de liste des sous-dossiers. |
| [hasChildNodes](m-domnode-haschildnodes.md) | Vérifie si le nœud comporte au moins un sous-dossier. |
| [normaliser](m-domnode-normalize.md) | Normalise le nœud : les nœuds de texte adjacents sont fusionnés et les nœuds de texte vides sont supprimés. |
| [hasAttributes](m-domnode-hasattributes.md) | Vérifie si le nœud possède au moins un attribut. |
| [isSameNode](m-domnode-issamenode.md) | Vérifie si la référence donnée représente le même nœud. |
| [isDefaultNamespace](m-domnode-isdefaultnamespace.md) | Teste si l’espace de noms donné est l’espace par défaut. |
| [urlEspaceRechercheNoms](m-domnode-lookupnamespaceuri.md) | A recherché l’URI de l’espace de noms lié au préfixe donné. |
| [isEqualNode](m-domnode-isequalnode.md) | Compare deux nœuds. |

## Propriétés

| Propriété | Description |
| --- | --- |
| [nodeName](p-domnode-nodename.md) | Nom de nœud qualifié. Le nom dépend du type de nœud. |
| [nodeValue](p-domnode-nodevalue.md) | Valeur du nœud. La valeur dépend du type de nœud. |
| [nodeType](p-domnode-nodetype.md) | Type de nœud. |
| [parentNode](p-domnode-parentnode.md) | Nœud parent ou nul. |
| [childNodes](p-domnode-childnodes.md) | Renvoie la liste des nœuds enfants sous la forme d’un tableau. |
| [premierEnfant](p-domnode-firstchild.md) | Premier nœud enfant de ce nœud ou valeur nulle s’il n’a pas d’enfant. |
| [dernierEnfant](p-domnode-lastchild.md) | Dernier nœud enfant de ce nœud ou null s&#39;il n&#39;a pas d&#39;enfant. |
| [frère suivant](p-domnode-nextsibling.md) | Nœud suivant ce nœud ou null. |
| [précédentFrère](p-domnode-previoussibling.md) | Nœud précédant immédiatement ce nœud ou nul. |
| [attributs](p-domnode-attributes.md) | Renvoie une table contenant la liste des attributs si le nœud est un élément, sinon null. |
| [namespaceURI](p-domnode-namespaceuri.md) | URI de l’espace de noms du nœud. |
| [préfixe](p-domnode-prefix.md) | Préfixe d’espace de noms de ce nœud ou vide s’il n’est pas spécifié. |
| [localName](p-domnode-localname.md) | Partie locale du nom qualifié du nœud. |
| [baseURI](p-domnode-baseuri.md) | URI de base de ce nœud. |
| [textContent](p-domnode-textcontent.md) | Contenu textuel du nœud. La valeur dépend du type de nœud. |
| [ownerDocument](p-domnode-ownerdocument.md) | Document auquel appartient ce nœud. |

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
