---
title: Migration des utilisateurs et utilisatrices techniques vers un compte technique sur Developer Console
description: Migration des utilisateurs et utilisatrices techniques vers un compte technique sur Developer Console
hide: true
hidefromtoc: true
source-git-commit: 290f4e9a0d13ef49caacb7a128ccc266bafd5e69
workflow-type: ht
source-wordcount: '807'
ht-degree: 100%

---

# Migration des opérateurs et opératrices techniques Campaign vers Adobe Developer Console {#migrate-tech-users-to-ims}

Campaign v8.5 et les versions ultérieures apportent des améliorations au processus d’authentification de Campaign v8. Les opérateurs ou opératrices techniques doivent utiliser [Adobe Identity Management System (IMS)](https://helpx.adobe.com/fr/enterprise/using/identity.html){target="_blank"} pour se connecter à Campaign. Un opérateur ou une opératrice technique est un profil utilisateur de Campaign qui a été explicitement créé pour l’intégration de l’API. Cet article décrit les étapes à suivre pour migrer un opérateur ou une opératrice technique vers un compte technique sur Adobe Developer Console.

## Qu’est-ce qui a changé ?{#ims-changes}

Les utilisateurs et utilisatrices standard de Campaign peuvent déjà se connecter à la console Adobe Campaign à l’aide de leur Adobe ID, via le système IMS (Adobe Identity Management System). Dans le cadre des mesures visant à renforcer la sécurité et le processus d’authentification, l’application cliente Adobe Campaign appelle désormais les API Campaign directement à l’aide du jeton de compte technique IMS.

Pour en savoir plus sur le nouveau processus d’authentification serveur à serveur, consultez la [documentation d’Adobe Developer Console](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.

Cette modification s’applique à partir de Campaign v8.5 et sera **obligatoire** à partir de Campaign v8.6.


## Cela vous concerne-t-il ?{#ims-impacts}

Si vous utilisez des API Campaign, vous devez migrer vos opérateurs ou opératrices techniques vers Adobe Developer Console, comme indiqué ci-dessous.

## Migrer vers Adobe Developer Console{#ims-migration-procedure}

### Conditions préalables{#ims-migration-prerequisites}

Avant de commencer le processus de migration, contactez votre représentant ou représentante Adobe afin que les équipes techniques d’Adobe puissent migrer vos groupes d’opérateurs et opératrices existants et vos droits nommés vers Adobe Identity Management System (IMS).

### Étape 1 : créer/mettre à jour votre projet Campaign dans Adobe Developer Console{#ims-migration-step-1}

Les intégrations sont créées dans le cadre d’un **Projet** dans Adobe Developer Console. En savoir plus sur les projets dans la [documentation d’Adobe Developer Console](https://developer.adobe.com/developer-console/docs/guides/projects/){target="_blank"}.

En tant qu’utilisateur ou utilisatrice de Campaign v8, vous devriez déjà disposer d’un projet dans Adobe Developer Console. Dans le cas contraire, créez-en un Consultez la procédure de création d’un projet [dans la documentation d’Adobe Developer Console](https://developer.adobe.com/developer-console/docs/guides/getting-started/){target="_blank"}.

Une fois que vous avez accès à votre projet Campaign, vous pouvez ajouter des services, y compris des API telles qu’Adobe Campaign et I/O Management. Dans le cadre de cette migration, vous devez ajouter les API suivantes dans votre projet : **I/O Management** et **Adobe Campaign**.

![](assets/do-not-localize/ims-products-and-services.png)


### Étape 2 : ajouter une API à votre projet à l’aide de l’authentification de serveur à serveur{#ims-migration-step-2}

Une fois votre projet créé dans Adobe Developer Console, ajoutez une API qui nécessite une authentification de serveur à serveur. Découvrez comment configurer les informations d’identification de serveur à serveur OAuth dans la [documentation d’Adobe Developer Console](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/){target="_blank"}.

Une fois la connexion à l’API établie, vous pouvez accéder aux informations d’identification nouvellement générées, y compris l’identifiant et le secret client, ainsi que générer un jeton d’accès.

### Étape 3 : ajouter le profil de produit au projet{#ims-migration-step-3}

Vous pouvez maintenant ajouter votre profil de produit Campaign au projet, comme décrit ci-dessous :

1. Ouvrez l’API Adobe Campaign.
1. Cliquez sur le bouton **Modifier les profils de produit**.

   ![](assets/do-not-localize/ims-edit-api.png)

1. Affectez tous les profils de produit pertinents à l’API, par exemple « messagecenter » et enregistrez vos modifications.
1. Accédez à l’onglet **Informations d’identification** de votre projet, puis copiez la valeur du champ **E-mail du compte technique**.

### Étape 4 : mettre à jour l’opérateur ou opératrice technique dans la console cliente {#ims-migration-step-4}

La dernière étape consiste à mettre à jour l’opérateur ou opératrice technique dans la console cliente Adobe Campaign.

>[!CAUTION]
>
>Après la mise à jour du type d’authentification de l’opérateur ou opératrice technique, toutes les intégrations d’API avec cet opérateur ou opératrice technique cesseront de fonctionner. Vous devez [mettre à jour vos intégrations d’API](#ims-migration-step-6).

Pour remplacer le mode d’authentification des opérateurs et opératrices techniques par IMS, procédez comme suit :

1. Dans l’explorateur de la console cliente Campaign, accédez à **Administration > Gestion des accès > Opérateurs**.
1. Modifiez l’opérateur ou opératrice technique existant utilisé pour les API.
1. Remplacez le **Nom (nom d’utilisateur)** de cet opérateur ou opératrice technique par l’e-mail du compte technique récupéré précédemment.
1. Accédez au bouton **Modifier** en haut à gauche, en regard de **Fichier**, puis sélectionnez **Éditer le fichier source XML**.
1. Remplacez le mode d’authentification par `ims`, comme indiqué ci-dessous :

   ```javascript
   <operator 
   ...
       <access authenticationType="ims" ...
       ...
       </access>
   ...
   </operator>
   ```

1. Enregistrez vos modifications.

Vous pouvez également mettre à jour l’opérateur ou l’opératrice technique par programmation, à l’aide de scripts SQL ou d’API Campaign. Ces modes automatisent les étapes de remplacement du nom de l’opérateur ou de l’opératrice par l’adresse e-mail du compte technique associé et/ou le type d’authentification.

* Utilisez le **Script SQL** suivant pour remplacer le nom de l’opérateur ou de l’opératrice par l’adresse e-mail associée :

   ```sql
   UPDATE xtkoperator
   SET sauthenticationtype = 'ims',
           sname = '{email}'
   WHERE sname = '{name}' AND itype = 0;
   ```

* Utilisez les `queryDef.ExecuteQuery` **API Campaign** suivantes pour récupérer l’ID d’un opérateur ou d’une opératrice pour un opérateur ou opératrice technique donné :

   ```javascript
   <?xml version="1.0" encoding="utf-8"?>
   <soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
       <soap:Body>
           <ExecuteQuery xmlns="urn:xtk:queryDef">
               <sessiontoken>{session_token}</sessiontoken>
               <entity>
                   <queryDef schema="xtk:operator" operation="select">
                       <select>
                           <node expr="@id"/>
                       </select>
                       <where>
                           <condition expr="@name='{name}'"/>
                           <condition expr="@type=0"/>
                       </where>
                   </queryDef>
               </entity>
           </ExecuteQuery>
       </soap:Body>
   </soap:Envelope>
   ```

* Utilisez les `session.Write` **API Campaign** suivantes pour remplacer le nom par l’adresse e-mail du compte technique :

   ```javascript
   <?xml version="1.0" encoding="utf-8"?>
   <soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
       <soap:Body>
           <Write xmlns="urn:xtk:session">
               <sessiontoken>{session_token}</sessiontoken>
               <domDoc xsi:type='ns:Element' SOAP-ENV:encodingStyle='http://xml.apache.org/xml-soap/literalxml'>
                   <operator _operation="update" id="{id}" name="{email}" xtkschema="xtk:operator">
                       <access authenticationType="ims" />
                   </operator>
               </domDoc>
           </Write>
       </soap:Body>
   </soap:Envelope>
   ```

### Étape 5 : valider votre configuration {#ims-migration-step-5}

Pour tester la connexion, procédez comme décrit dans la section [Guide des informations d’identification d’Adobe Developer Console](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#generate-access-tokens){target="_blank"} pour générer un jeton d’accès et copier la commande Sample cURL fournie.


### Étape 6 : mettre à jour les intégrations d’API tierces {#ims-migration-step-6}

Vous devez mettre à jour les intégrations d’API avec vos systèmes tiers.

Pour plus d’informations sur les étapes d’intégration des API, y compris un exemple de code pour une intégration fluide, consultez la section [Documentation sur l’authentification d’Adobe Developer Console](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.


### Exemples d’appels Soap{#ims-migration-samples}

Une fois le processus de migration réalisé et validé, les appels Soap sont mis à jour comme indiqué ci-dessous :

* Avant la migration

   ```sql
   POST /nl/jsp/soaprouter.jsp HTTP/1.1
   Host: localhost:8080
   Content-Type: application/soap+xml;
   SOAPAction: "nms:rtEvent#PushEvent"
   charset=utf-8
   
   <?xml version="1.0" encoding="utf-8"?>  <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:nms:rtEvent">
   <soapenv:Header/>
   <soapenv:Body>
       <urn:PushEvent>
           <urn:sessiontoken>SESSION_TOKEN</urn:sessiontoken>
           <urn:domEvent>
               <!--You may enter ANY elements at this point-->
               <rtEvent type="type" email="name@domain.com"/>
           </urn:domEvent>
       </urn:PushEvent>
   </soapenv:Body>
   </soapenv:Envelope>
   ```

* Après la migration

   ```sql
   POST /nl/jsp/soaprouter.jsp HTTP/1.1
   Host: localhost:8080
   Content-Type: application/soap+xml;
   SOAPAction: "nms:rtEvent#PushEvent"
   charset=utf-8
   Authorization: Bearer <IMS_Technical_Token_Token>
   
   <?xml version="1.0" encoding="utf-8"?>  <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:nms:rtEvent">
   <soapenv:Header/>
   <soapenv:Body>
       <urn:PushEvent>
           <urn:sessiontoken></urn:sessiontoken>
           <urn:domEvent>
               <!--You may enter ANY elements at this point-->
               <rtEvent type="type" email="name@domain.com"/>
           </urn:domEvent>
       </urn:PushEvent>
   </soapenv:Body>
   </soapenv:Envelope>
   ```
