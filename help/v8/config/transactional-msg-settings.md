---
title: Paramètres de messagerie transactionnelle Campaign
description: Paramètres de messagerie transactionnelle Campaign
feature: Transactional Messaging
role: Admin, Developer
level: Intermediate, Experienced
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
source-git-commit: 2d10a8f4349b9e2405847fc6a3db1ed568c60387
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 65%

---

# Paramètres de messagerie transactionnelle

Les messages transactionnels (Message Center) sont un module de Campaign conçu pour gérer les messages déclenchés. En savoir plus sur les messages transactionnels dans [cette section](../send/transactional.md).

Découvrez l&#39;architecture de la messagerie transactionnelle sur [cette page](../architecture/architecture.md#transac-msg-archi).

![](../assets/do-not-localize/speech.png) En tant qu&#39;utilisateur Managed Cloud Services, [contactez Adobe](../start/campaign-faq.md#support) pour installer et configurer la messagerie transactionnelle de Campaign dans votre environnement.

## Définition des autorisations

Pour créer des utilisateurs pour les instances d’exécution Message Center hébergées sur Adobe Cloud, vous devez contacter l’assistance clientèle d’Adobe. Les utilisateurs de Message Center sont des opérateurs spécifiques qui ont besoin d’autorisations dédiées pour accéder aux dossiers « Evénements temps réel » (nmsRtEvent).

## Extensions de schéma

Les extensions de schéma effectuées sur les schémas utilisés par les [workflows techniques de Message Center](#technical-workflows) sur les instances de pilotage ou d’exécution doivent être dupliquées sur les autres instances utilisées par le module des messages transactionnels d’Adobe Campaign.

## Envoi de notifications push transactionnelles

Lorsqu’elle est combinée avec [Module Canal des applications mobiles](../send/push.md), les messages transactionnels vous permettent de transmettre des messages transactionnels par le biais de notifications sur des appareils mobiles.

Pour envoyer des notifications push transactionnelles, vous devez exécuter les configurations suivantes :

1. Installez le package **Canal des applications mobiles** sur les instances de pilotage et d’exécution.

   >[!CAUTION]
   >
   >Consultez votre contrat de licence avant d’installer un nouveau package intégré Campaign.

1. Répliquez le service **Application mobile** et les applications mobiles associées sur les instances d&#39;exécution.

En outre, l’événement doit contenir les éléments suivants :

* L’identifiant de l’appareil mobile : **registrationId** pour Android et **deviceToken** pour iOS. Cet identifiant représente l’&quot;adresse&quot; à laquelle la notification est envoyée.
* Le lien vers l&#39;application mobile ou la clé d&#39;intégration (**uuid**) permettant de récupérer les informations de connexion spécifiques à l&#39;application.
* Le canal sur lequel la notification sera envoyée (**wishedChannel**) : 41 pour iOS et 42 pour Android.
* Toute autre donnée de personnalisation.

Vous trouverez ci-dessous un exemple de configuration d’événement pour envoyer des notifications push transactionnelles :

```
<SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
     <urn:PushEvent>
         <urn:sessiontoken>mc/</urn:sessiontoken>
         <urn:domEvent>

              <rtEvent wishedChannel="41" type="DELIVERY" registrationToken="2cefnefzef758398493srefzefkzq483974">
                <mobileApp _operation=”none” uuid="com.adobe.NeoMiles"/>
                <ctx>
                    <deliveryTime>1:30 PM</deliveryTime>
                    <url>http://www.adobe.com</url>
                </ctx>
              </rtEvent>

         </urn:domEvent>
     </urn:PushEvent>           
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```




## Purge des événements {#purge-events}

Vous pouvez adapter les paramètres de l&#39;assistant de déploiement pour paramétrer la durée pendant laquelle les données seront stockées dans la base de données.

La purge des événements est effectuée automatiquement par la fonction **Nettoyage de la base** workflow technique. Ce workflow purge les événements reçus et stockés sur les instances d&#39;exécution et les événements archivés sur une instance de pilotage.

Pour modifier les paramètres de purge de la variable **Événements** (sur une instance d’exécution) et **Evénements archivés** (sur une instance de pilotage).


## Workflows techniques {#technical-workflows}

Vous devez vous assurer que les workflows techniques sur vos instances de pilotage et d&#39;exécution ont été démarrés avant de déployer tout modèle de message transactionnel.

Ces workflows sont ensuite accessibles à partir du dossier **Administration > Production > Message Center.**

### Workflows de l&#39;instance de pilotage {#control-instance-workflows}

Sur l&#39;instance de pilotage, vous devez créer un workflow d&#39;archivage pour chaque **[!UICONTROL Instance d&#39;exécution Message Center]** compte externe . Cliquez sur le bouton **[!UICONTROL Créer le workflow d&#39;archivage]** pour créer et démarrer le processus.

### Workflows de l&#39;instance d&#39;exécution {#execution-instance-workflows}

Sur la ou les instances d&#39;exécution, vous devez démarrer les workflows techniques suivants :

* **[!UICONTROL Traitement des événements batch]** (nom interne : **[!UICONTROL batchEventsProcessing]**) : ce workflow permet de répartir les événements batch dans une file d&#39;attente avant qu&#39;ils ne soient associés à un modèle de message.
* **[!UICONTROL Traitement des événements temps réel]** (nom interne : **[!UICONTROL rtEventsProcessing]**) : ce workflow permet de répartir les événements temps réel dans une file d&#39;attente avant qu&#39;ils ne soient associés à un modèle de message.
* **[!UICONTROL Mise à jour du statut des événements]** (nom interne : **[!UICONTROL updateEventsStatus]**) : ce workflow permet d&#39;attribuer un statut à l&#39;événement.

   Les statuts des événements possibles sont les suivants :

   * **[!UICONTROL En attente]** : l&#39;événement se trouve dans la file d&#39;attente. Aucun modèle de message ne lui a encore été associé.
   * **[!UICONTROL En attente de diffusion]** : l&#39;événement est dans la file d&#39;attente, un modèle de message lui a été associé et il est en cours de traitement par la diffusion.
   * **[!UICONTROL Envoyé]** : ce statut est copié depuis les logs de diffusion. Il signifie que la diffusion a été envoyée.
   * **[!UICONTROL Ignoré par la diffusion]** : ce statut est copié depuis les logs de diffusion. Il signifie que la diffusion a été ignorée.
   * **[!UICONTROL Erreur de diffusion]** : ce statut est copié depuis les logs de diffusion. Il signifie que la diffusion a échoué.
   * **[!UICONTROL Evénement non pris en charge]** : l&#39;association de l&#39;événement à un modèle de message a échoué. L&#39;événement ne sera pas retraité.
