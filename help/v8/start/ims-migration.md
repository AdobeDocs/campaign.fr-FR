---
title: Migration des utilisateurs techniques vers un compte technique sur Developer Console
description: Migration des utilisateurs techniques vers un compte technique sur Developer Console
hide: true
hidefromtoc: true
source-git-commit: 1f9efc0744792c1173e77965ff81eaee0ed2c618
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 2%

---

# Migration des opérateurs techniques Campaign vers la console Adobe Developer {#migrate-tech-users-to-ims}

Depuis Campaign v8.5, le processus d&#39;authentification vers Campaign v8 est en cours d&#39;amélioration. Les opérateurs techniques doivent utiliser [Adobe Identity Management System (IMS)](https://helpx.adobe.com/fr/enterprise/using/identity.html){target="_blank"} pour vous connecter à Campaign. Un opérateur technique est un profil utilisateur de Campaign qui a été explicitement créé pour l&#39;intégration de l&#39;API. Cet article décrit les étapes à suivre pour migrer un opérateur technique vers un compte technique sur la console Adobe Developer.

## Qu’est-ce qui a changé ?{#ims-changes}

Les utilisateurs standard de Campaign se connectent déjà à la console Adobe Campaign à l’aide de leur Adobe ID, via Adobe Identity Management System (IMS). Dans le cadre de l&#39;effort visant à renforcer la sécurité et le processus d&#39;authentification, l&#39;application cliente Adobe Campaign appelle désormais les API Campaign directement à l&#39;aide du jeton de compte technique IMS.

En savoir plus sur le nouveau processus d’authentification serveur à serveur dans [Documentation de la console Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.

Cette modification s’applique à partir de Campaign v8.5 et sera **mandatory** Démarrage de Campaign v8.6.


## Cela vous concerne-t-il ?{#ims-impacts}

Si vous utilisez des API Campaign, vous devez migrer votre ou vos opérateurs techniques vers la console Adobe Developer, comme décrit ci-dessous.

## Comment migrer ?{#ims-migration-procedure}

### Conditions préalables{#ims-migration-prerequisites}

Avant de commencer le processus de migration, vous devez contacter votre représentant d’Adobe afin que les équipes techniques d’Adobe puissent migrer vos groupes d’opérateurs existants et vos droits nommés vers Adobe Identity Management System (IMS).

### Étape 1 - Créer/mettre à jour votre projet Campaign dans la console Adobe Developer{#ims-migration-step-1}

Les intégrations sont créées dans le cadre d’une **Projet** dans la console Adobe Developer. En savoir plus sur les projets dans [Documentation de la console Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/projects/){target="_blank"}.

En tant qu’utilisateur de Campaign v8, vous devez déjà disposer d’un projet dans la console Adobe Developer. Dans le cas contraire, vous devez créer un projet. Les étapes de création d’un projet sont détaillées. [dans la documentation de la console Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/getting-started/){target="_blank"}.

Une fois que vous avez accès à votre projet Campaign, vous pouvez ajouter des services, y compris des API, Adobe Campaign et l’API de gestion I/O. Pour cette migration, vous devez ajouter les API suivantes dans votre projet : **API de gestion I/O** et **Adobe Campaign**.

![](assets/do-not-localize/ims-products-and-services.png)


### Étape 2 - Ajout d’une API à votre projet à l’aide de l’authentification serveur à serveur{#ims-migration-step-2}

Une fois votre projet créé dans la console Adobe Developer, ajoutez une API qui utilise l’authentification serveur à serveur. Découvrez comment configurer les informations d’identification OAuth serveur à serveur dans [Documentation de la console Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/){target="_blank"}.

Une fois la connexion à l’API établie, vous pouvez accéder aux informations d’identification nouvellement générées, y compris l’identifiant du client et le secret du client, ainsi que générer un jeton d’accès.

### Étape 3 - Ajout du profil de produit au projet{#ims-migration-step-3}

Vous pouvez maintenant ajouter votre profil de produit Campaign au projet, comme décrit ci-dessous :

1. Ouvrez l’API Adobe Campaign.
1. Cliquez sur le bouton **Modification des profils de produit** button

   ![](assets/do-not-localize/ims-edit-api.png)

1. Affectez tous les profils de produit pertinents à l’API, par exemple &quot;messagecenter&quot;, et enregistrez vos modifications.
1. Accédez au **Informations d’identification** de votre projet, puis copiez la variable **Adresse électronique du compte technique** .

### Etape 4 - Mettre à jour l&#39;opérateur technique dans la console cliente {#ims-migration-step-4}

La dernière étape consiste à mettre à jour l&#39;opérateur technique dans la console cliente Adobe Campaign.

>[!CAUTION]
>
>Après la mise à jour du type d&#39;authentification de l&#39;opérateur technique, toutes les intégrations de l&#39;API avec cet opérateur technique cesseront de fonctionner. Vous devez [mettre à jour vos intégrations d’API](#ims-migration-step-6).

Pour mettre à jour le mode d&#39;authentification des opérateurs techniques vers IMS, procédez comme suit :

1. Dans l&#39;explorateur de la console cliente Campaign, accédez à la **Administration > Gestion des accès > Opérateurs**.
1. Editez l&#39;opérateur technique existant utilisé par les API fir.
1. Remplacez la variable **Nom (login)** de cet opérateur technique par l&#39;email du compte technique récupéré précédemment.
1. Accédez au **Modifier** bouton en haut à gauche en regard de **Fichier**, puis sélectionnez **Modification de la source XML**.
1. Mettre à jour le mode d’authentification vers `ims`, comme suit :

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

Vous pouvez également mettre à jour l&#39;opérateur technique par programmation, à l&#39;aide de scripts SQL ou d&#39;API Campaign. Ces modes permettent d&#39;automatiser les étapes de mise à jour du nom de l&#39;opérateur avec l&#39;adresse email du compte technique associé et/ou le type d&#39;authentification.

* Utilisez les **Script SQL** pour remplacer le nom de l&#39;opérateur par l&#39;email associé :

   ```sql
   UPDATE xtkoperator
   SET sauthenticationtype = 'ims',
           sname = '{email}'
   WHERE sname = '{name}' AND itype = 0;
   ```

* Utilisez les `queryDef.ExecuteQuery` **API Campaign** pour récupérer l&#39;identifiant d&#39;un opérateur pour un opérateur technique donné :

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

* Utilisez les `session.Write` **API Campaign** pour mettre à jour le nom avec l’adresse électronique donnée du compte technique :

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

### Étape 5 - Valider votre configuration {#ims-migration-step-5}

Pour tester la connexion, procédez comme décrit dans la section [Guide des informations d’identification de la console Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#generate-access-tokens){target="_blank"} pour générer un jeton d’accès et copier la commande Sample cURL fournie.


### Étape 6 - Mise à jour des intégrations d’API tierces {#ims-migration-step-6}

Vous devez mettre à jour les intégrations d’API avec vos systèmes tiers.

Pour plus d’informations sur les étapes d’intégration de l’API, y compris un exemple de code pour une intégration fluide, reportez-vous à la section [Documentation d’authentification de la console Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.


### Exemples d&#39;appels Soap{#ims-migration-samples}

Une fois le processus de migration réalisé et validé, les appels Soap sont mis à jour comme ci-dessous :

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
