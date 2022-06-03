---
title: Nouvelles API de Campaign v8
description: Nouvelles API de Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: dd822f88-b27d-4944-879c-087f68e79825
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 100%

---

# Nouvelles API de Campaign{#gs-new-api}

Dans le contexte d’un [Déploiement Enterprise (FFDA)](enterprise-deployment.md), Campaign v8 est fourni avec deux nouvelles API pour gérer les données entre la base de données locale Campaign et la base de données Cloud. Les conditions préalables à leur utilisation sont l&#39;activation du mécanisme d&#39;évaluation sur le schéma. [En savoir plus](staging.md)

* API d&#39;ingestion : **xtk.session.ingest**

   Cette API est dédiée uniquement à l&#39;insertion de données. [En savoir plus](#data-insert-api)

* API de mise à jour/suppression des données : **xtk.session.ingestExt**

   Cette API est utilisée pour mettre à jour ou supprimer des données. [En savoir plus](#data-update-api)

Un workflow intégré dédié synchronise les données dans la base de données cloud.

## Insérer les données {#data-insert-api}

L&#39;API **xtk.session.ingest** est réservée à l&#39;insertion de données uniquement. Aucune mise à jour/suppression.

### Insertion sans réconciliation

**Dans un workflow**

Utilisez le code suivant dans une activité **Code JavaScript** pour insérer des données dans la base de données Cloud sans réconciliation :

```
var xmlStagingSampleTable = <sampleTableStg
                                testcol1="testValue1"
                                testcol2="testValue2"
                                xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;
strUuid = xtk.session.Ingest(xmlStagingSampleTable);
logInfo(strUuid);
```

Une fois le workflow exécuté, la table d&#39;évaluation est alimentée comme prévu.

**À partir d&#39;un appel SOAP**

1. Obtenez le jeton d&#39;authentification.
1. Déclenchez l&#39;API. La payload est la suivante :

   ```
   <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:xtk:session">
   <soapenv:Header/>
   <soapenv:Body>
       <urn:Ingest>
           <urn:sessiontoken>___xxxxxxx-xxxx-xxx-xxx-xxxxxxxxxxx</urn:sessiontoken>
           <urn:domDoc>
               <sampleTableStg
                   testcol1="Test Value 1 (from SOAP)"
                   testcol2="Test Value 2 (from SOAP)"
                   xtkschema="dem:sampleTableStg">
               </sampleTableStg>
           </urn:domDoc>
       </urn:Ingest>
   </soapenv:Body>
   </soapenv:Envelope>
   ```

1. UUID est renvoyé à la réponse SOAP :

   ```
   <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="urn:wpp:default" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
       <IngestResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns="urn:wpp:default">
           <pstrSUuids xsi:type="xsd:string">e1e7c8b3-6f79-44da-a72d-49ed0f73db2c</pstrSUuids>
       </IngestResponse>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   ```

Par conséquent, le tableau d&#39;évaluation est alimenté comme prévu.

![](assets/no-reconciliation.png)

### Insertion avec réconciliation

**Dans un workflow**

Utilisez le code suivant dans une activité **Code JavaScript** pour insérer des données dans la base de données Cloud avec réconciliation :

```
var xmlStagingSampleTable = <sampleTableStg  _key="@id" id="ABC12345"
                              testcol1="testValue1"
                              testcol2="testValue2"
                              xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;         
strUuid = xtk.session.Ingest(xmlStagingSampleTable);
logInfo(strUuid);
```

Une fois le workflow exécuté, la table d&#39;évaluation est alimentée comme prévu.

![](assets/with-reconciliation.png)


**À partir d&#39;un appel SOAP**

1. Obtenez le jeton d&#39;authentification.
1. Déclenchez l&#39;API. La payload est la suivante :

   ```
   <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:xtk:session">
   <soapenv:Header/>
   <soapenv:Body>
     <urn:Ingest>
        <urn:sessiontoken>___5e71f4bf-d38a-4ba8-ac15-35a958f7f138</urn:sessiontoken>
        <urn:domDoc>
           <sampleTableStg  _key="@id" id="ABDCD321"
                testcol1="Test Value 1 (from SOAP)"
                testcol2="Test Value 2 (from SOAP)"
                xtkschema="dem:sampleTableStg">
            </sampleTableStg>
        </urn:domDoc>
     </urn:Ingest>
    </soapenv:Body>
   </soapenv:Envelope>
   ```

1. Dans ce cas, l&#39;UUID n&#39;est pas renvoyé à la réponse, car il a été fourni dans la payload. La réponse est :

   ```
   <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="urn:wpp:default" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
       <IngestResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns="urn:wpp:default">
           <pstrSUuids xsi:type="xsd:string"/>
       </IngestResponse>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   ```

Par conséquent, le tableau d&#39;évaluation est alimenté comme prévu.

## Mise à jour ou suppression de données{#data-update-api}

L&#39;API **xtk.session.IngestExt** est optimisée pour la mise à jour/suppression des données. Pour insérer uniquement, préférez **xtk.session.ingest**. L&#39;insertion fonctionne si la clé d&#39;enregistrement ne se trouve pas dans la table d&#39;évaluation.

### Insertion/mise à jour

**Dans un workflow**

Utilisez le code suivant dans une activité **Code JavaScript** pour mettre à jour les données de la base de données Cloud :

```
var xmlStagingRecipient = <sampleTableStg  _key="@id" id="ABC12345"
                              testcol1="testValue A (updated)"
                              testcol2="testValue B (updated)"
                              xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;
xtk.session.IngestExt(xmlStagingRecipient);
```

Une fois le workflow exécuté, la table d&#39;évaluation est mise à jour comme prévu.

![](assets/updated-data.png)

**À partir d&#39;un appel SOAP**


1. Obtenez le jeton d&#39;authentification.
1. Déclenchez l&#39;API. La payload est la suivante :

   ```
   <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:xtk:session">
   <soapenv:Header/>
   <soapenv:Body>
       <urn:IngestExt>
           <urn:sessiontoken>___444cd168-a1e2-4fb6-a2a8-73be9f133489</urn:sessiontoken>
           <urn:domDoc>
           <sampleTableStg  _key="@id" id="ABDCD321"
                   testcol1="Test Value E (from SOAP)"
                   testcol2="Test Value F (from SOAP)"
                   xtkschema="dem:sampleTableStg">
               </sampleTableStg>
           </urn:domDoc>
       </urn:IngestExt>
   </soapenv:Body>
   </soapenv:Envelope>
   ```

1. La réponse SOAP est la suivante :

   ```
   <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="urn:wpp:default" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
       <IngestExtResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns="urn:wpp:default"/>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   ```

Par conséquent, le tableau d&#39;évaluation est mis à jour comme prévu.

## Gestion des abonnements {#sub-apis}

La gestion des abonnements dans Campaign est décrite dans [cette page](../start/subscriptions.md).

L&#39;insertion des données d&#39;abonnement et de désabonnement repose sur le [mécanisme d&#39;évaluation](staging.md) de la base de données locale de Campaign. Les informations sur les abonnés sont temporaires et stockées dans des tables intermédiaires de la base de données locale. Le workflow de synchronisation envoie ces données de la base locale vers la base de données Cloud. Par conséquent, les processus d&#39;abonnement et de désabonnement sont **asynchrones**. Les demandes d&#39;opt-in et d&#39;opt-out sont traitées toutes les heures par le biais d&#39;un workflow technique spécifique. [En savoir plus](replication.md#tech-wf)


**Rubriques connexes**

* [JSAPI Campaign Classic v7](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html?lang=fr)
