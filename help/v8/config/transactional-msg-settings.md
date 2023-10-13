---
title: Paramètres de messagerie transactionnelle Campaign
description: Paramètres de messagerie transactionnelle Campaign
feature: Transactional Messaging
role: Admin, Developer
level: Intermediate, Experienced
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 100%

---

# Paramètres de messagerie transactionnelle {#mc-settings}

« Messages transactionnels » (Message Center) désigne un module de Campaign conçu pour gérer les messages déclenchés. Pour en savoir plus sur les fonctionnalités des messages transactionnels, consultez [cette section](../send/transactional.md).

Découvrez l’architecture de la messagerie transactionnelle sur [cette page](../architecture/architecture.md#transac-msg-archi).

![](../assets/do-not-localize/speech.png) En tant qu’utilisateur ou utilisatrice Managed Cloud Services, [contactez Adobe](../start/campaign-faq.md#support) pour installer et configurer la messagerie transactionnelle de Campaign dans votre environnement.

## Définition des autorisations {#mc-permissions}

Pour créer des utilisateurs pour les instances d&#39;exécution Message Center hébergées sur Adobe Cloud, vous devez contacter l&#39;assistance client Adobe. Les utilisateurs de Message Center sont des opérateurs spécifiques qui nécessitent des autorisations dédiées pour accéder aux dossiers &#39;Evénements temps réel&#39; (nmsRtEvent).

## Extensions de schéma  {#mc-schema-ext}

Les extensions de schéma effectuées sur les schémas utilisés par les [workflows techniques de Message Center](#technical-workflows) sur les instances de pilotage ou d’exécution doivent être dupliquées sur les autres instances utilisées par le module des messages transactionnels d’Adobe Campaign.

## Envoyer des notifications push transactionnelles {#mc-transactional-push}

Couplés au module [Canal des applications mobiles](../send/push.md), les messages transactionnels permettent d’émettre des notifications push sur des applications mobiles.

Pour envoyer des notifications push transactionnelles, vous devez exécuter les configurations suivantes :

1. Installez le package **Canal des applications mobiles** sur les instances de pilotage et d’exécution.

   >[!CAUTION]
   >
   >Consultez votre contrat de licence avant d’installer un nouveau package intégré Campaign.

1. Répliquez le service **Application mobile** et les applications mobiles associées sur les instances d’exécution.

En outre, l’événement doit contenir les éléments suivants :

* L’identifiant de l’appareil mobile : **registrationId** pour Android et **deviceToken** pour iOS. Cet identifiant représente l’« adresse » à laquelle la notification est envoyée.
* Le lien vers l&#39;application mobile ou la clé d&#39;intégration (**uuid**) permettant de récupérer les informations de connexion spécifiques à l&#39;application.
* Le canal sur lequel la notification sera envoyée (**wishedChannel**) : 41 pour iOS et 42 pour Android.
* Toute autre donnée de personnalisation.

Vous trouverez ci-dessous un exemple de configuration d’événement permettant d’envoyer des notifications push transactionnelles :

```
<SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
     <urn:PushEvent>
         <urn:sessiontoken>mc/</urn:sessiontoken>
         <urn:domEvent>

              <rtEvent wishedChannel="41" type="DELIVERY" registrationToken="2cefnefzef758398493srefzefkzq483974">
                <mobileApp _operation="none" uuid="com.adobe.NeoMiles"/>
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

## Purger des événements {#purge-events}

Vous pouvez adapter les paramètres de l’assistant de déploiement pour configurer la durée pendant laquelle vous souhaitez conserver les événements dans la base de données.

La purge des événements est effectuée automatiquement par le workflow technique **Nettoyage de la base**. Ce workflow purge les événements reçus et stockés sur les instances d’exécution et les événements archivés sur une instance de pilotage.

Vous pouvez modifier les paramètres de purge des **événements** (sur une instance d’exécution) et des **événements archivés** (sur une instance de pilotage) à l’aide des flèches.


## Workflows techniques {#technical-workflows}

Vous devez vous assurer que les workflows techniques de vos instances d’exécution et de pilotage ont démarré avant de procéder au déploiement des modèles de messages transactionnels.

Ces workflows sont ensuite accessibles à partir du dossier **Administration > Production > Message Center.**

### Workflows de l’instance de pilotage {#control-instance-workflows}

Sur l’instance de pilotage, vous devez créer un workflow d’archivage pour chaque compte externe **[!UICONTROL Instance d’exécution de Message Center]**. Cliquez sur le bouton **[!UICONTROL Créer le workflow d’archivage]** pour créer et démarrer le processus.

### Workflows de l’instance d’exécution {#execution-instance-workflows}

Sur la ou les instances d’exécution, vous devez démarrer les workflows techniques suivants :

* **[!UICONTROL Traitement des événements batch]** (nom interne : **[!UICONTROL batchEventsProcessing]**) : ce workflow permet de répartir les événements batch dans une file d&#39;attente avant qu&#39;ils ne soient associés à un modèle de message.
* **[!UICONTROL Traitement des événements temps réel]** (nom interne : **[!UICONTROL rtEventsProcessing]**) : ce workflow permet de répartir les événements temps réel dans une file d&#39;attente avant qu&#39;ils ne soient associés à un modèle de message.
* **[!UICONTROL Mise à jour du statut des événements]** (nom interne : **[!UICONTROL updateEventsStatus]**) : ce workflow permet d&#39;attribuer un statut à l&#39;événement.

  Les statuts possibles des événements sont les suivants :

   * **[!UICONTROL En attente]** : l’événement se trouve dans la file d’attente. Aucun modèle de message ne lui a encore été affecté.
   * **[!UICONTROL En attente de diffusion]** : l’événement est dans la file d’attente, un modèle de message lui a été associé et il est en cours de traitement par la diffusion.
   * **[!UICONTROL Envoyé]** : ce statut est copié depuis les logs de diffusion. Il signifie que la diffusion a été envoyée.
   * **[!UICONTROL Ignoré par la diffusion]** : ce statut est copié depuis les logs de diffusion. Il signifie que la diffusion a été ignorée.
   * **[!UICONTROL Erreur de diffusion]** : ce statut est copié depuis les logs de diffusion. Il signifie que la diffusion a échoué.
   * **[!UICONTROL Evénement non pris en charge]** : l’association de l’événement à un modèle de message a échoué. L’événement ne sera pas retraité.
