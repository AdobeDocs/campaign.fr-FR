---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 7%
---
# addMethod

Déclare une fonction sur le service.

```text
addMethod (name, action, arguments, responses, requestNodeName, responseNodeName)
```

## Paramètres

**name** Nom de la méthode. Il s’agit du nom exposé dans JavaScript et du nom de la méthode SOAP.

Paramètre SOAP-Action **action**.

**arguments** Déclaration des arguments sous la forme d&#39;un tableau contenant une liste de chaînes regroupées par paires. La première chaîne est le nom de l’argument et la seconde correspond au type : \[« name1 », « type1 », « name2 », « type2 », ...\]

**réponses** Déclaration des valeurs de retour sous la forme d&#39;une table contenant une liste de chaînes regroupées par paires : la première chaîne est le nom de l&#39;argument et la seconde correspond au type : \[« name1 », « type1 », « name2 », « type2 », ...\]

**requestNodeName** Chaîne de caractères spécifiant le nom du nœud XML de la requête SOAP au lieu du nom de la méthode.

**responseNodeName** Une chaîne de caractères qui spécifie le nom du nœud XML de la réponse SOAP au lieu du nom de la méthode suivie de la réponse.

## Valeur renvoyée

Aucune.

## Remarques

Les types suivants sont pris en charge :

* string
* boolean
* long
* short
* byte
* float
* double
* date
* heure
* datetime
* NLDocument
* NLElement
* NLRawXML
* NLCollection

Lorsqu’une méthode est déclarée sur le service, elle devient une méthode du service et peut être appelée directement en appelant la méthode par son nom. Le type NLRawXML utilisé sur un paramètre entrant copie l’intégralité du nœud XML pour remplacer l’argument . Utilisé comme type de retour, il contient l’intégralité du premier élément enfant de la réponse SOAP. Son utilisation implique que la réponse SOAP n’a qu’un seul élément enfant. Le type NLCollection utilisé sur un paramètre entrant copie tous les éléments enfants pour remplacer l&#39;argument. Cela s’avère utile lorsque l’argument entrant est un paramètre de variable. Utilisé comme type de retour, il contient l’intégralité de la réponse SOAP, puisqu’il s’agit de la racine de la valeur renvoyée. En cas d’erreur, une exception est générée. S’il s’agit d’une erreur SOAP correctement formée, l’exception levée possède une propriété soapFault et contient le nœud XML de l’erreur SOAP. Exemple:

```javascript
      var cnx = new HttpSoapConnection("http://localhost/nl/jsp/soaprouter.jsp", "utf-8", 0)
var session = new SoapService(cnx, "xtk:session")
session.addMethod("GetOption", "xtk:session#GetOption",
  ["token", "string", "name", "string"],
  ["value", "string", "type", "byte"])
try
{
var result  = session.GetOption("admin/", "NmsBroadcast_DefaultProvider")
var value   = result[0]
var type    = result[1]
logInfo("Value = " + value)
logInfo("Type = " + type)
}
catch( e )
{
  if( e.soapFault )
    logInfo("A SOAP Fault occured : " + e.soapFault.toXMLString());
  else
    logInfo("An error occured : " + e);
}
```

## Fonctionnalités

**Méthode de classe :** [SoapService](c-soapservice.md)

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
