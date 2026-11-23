---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 46%
---
# decryptPassword

> Avertissement :
>
> Cette documentation a été mise à jour. Pour plus d’informations, reportez-vous à cette [page](https://experienceleague.adobe.com/en/docs/campaign-classic/using/technotes/gcm-functions#decryptpassword-headding-anchor-decryptpassword-javascript).

Déchiffre un mot de passe stocké dans un compte externe.

```text
decryptPassword (str)
```

## Paramètres

**str** La chaîne de caractères chiffrée.

## Valeur renvoyée

Renvoie le mot de passe en texte brut.

## Remarques

Cette fonction ne peut pas être appelée dans les workflows, les applications web, les rapports ou les diffusions. Elle peut être appelée dans les implémentations d’appels JSSP ou SOAP. Exemple :

```javascript
          function nms_extAccount_LogonToRemoteInstance(remoteInstanceUrl, login, encryptedPassword) {
          var cnx = null, sessionService = null;
          try
              {
                  var cnx = new HttpSoapConnection(remoteInstanceUrl + '/nl/jsp/soaprouter.jsp', 'utf-8', 0);
                  sessionService = new SoapService(cnx, 'xtk:session');
                  sessionService.addMethod("Logon", "xtk:session#Logon",
                      ["token", "string", "login", "string", "password", "string", "parameters", "NLElement"],
                      ["sessionToken", "string", "sessionInfo", "NLElement", "securityToken", "string"]);
                  return sessionService.Logon("", login, decryptPassword(encryptedPassword), <parameters/>);
              }
          catch( e ) {
          logError(e);
          }
          finally {
          if( sessionService ) sessionService.dispose();
          if( cnx ) cnx.dispose();
          }
          })
      
```

## Fonctionnalités

**Disponible en :**

* Méthode SOAP
