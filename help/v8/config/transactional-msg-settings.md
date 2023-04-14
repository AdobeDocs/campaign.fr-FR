---
title: Paramètres de messagerie transactionnelle Campaign
description: Paramètres de messagerie transactionnelle Campaign
feature: Transactional Messaging
role: Admin, Developer
level: Intermediate, Experienced
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
source-git-commit: c61f03252c7cae72ba0426d6edcb839950267c0a
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 74%

---

# Paramètres de messagerie transactionnelle

![](../assets/do-not-localize/speech.png) En tant qu&#39;utilisateur Managed Cloud Services, [contactez Adobe](../start/campaign-faq.md#support) pour installer et configurer la messagerie transactionnelle de Campaign dans votre environnement.

![](../assets/do-not-localize/glass.png) Les fonctionnalités de messagerie transactionnelle sont décrites dans [cette section](../send/transactional.md).

![](../assets/do-not-localize/glass.png) Découvrez l&#39;architecture de la messagerie transactionnelle sur [cette page](../architecture/architecture.md#transac-msg-archi).

## Définition des autorisations

Pour créer des utilisateurs pour les instances d’exécution Message Center hébergées sur Adobe Cloud, vous devez contacter l’assistance clientèle d’Adobe. Les utilisateurs de Message Center sont des opérateurs spécifiques qui ont besoin d’autorisations dédiées pour accéder aux dossiers « Evénements temps réel » (nmsRtEvent).

## Extensions de schéma

Les extensions de schéma effectuées sur les schémas utilisés par les **workflows techniques de Message Center** sur les instances de pilotage ou d&#39;exécution doivent être dupliquées sur les autres instances utilisées par le module des messages transactionnels d&#39;Adobe Campaign.

![](../assets/do-not-localize/book.png) En savoir plus sur les workflows techniques de Message Center dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/configure-transactional-messaging/additional-configurations.html?lang=fr#technical-workflows).

## Envoi de notifications push transactionnelles

Couplés au module Canal des applications mobiles, les messages transactionnels permettent d&#39;émettre des messages transactionnels au travers des notifications push sur des applications mobiles.

![](../assets/do-not-localize/book.png) Mobile App Channel est présenté dans la section [cette section](../send/push.md).

Pour envoyer des notifications push transactionnelles, vous devez exécuter les configurations suivantes :

1. Installez le package **Canal des applications mobiles** sur les instances de pilotage et d’exécution.

   >[!CAUTION]
   >
   >Consultez votre contrat de licence avant d’installer un nouveau package intégré Campaign.

1. Répliquez le service **Application mobile** et les applications mobiles associées sur les instances d&#39;exécution.

Afin que Campaign envoie des notifications push transactionnelles, l&#39;événement doit contenir les éléments suivants :

* L&#39;identifiant de l&#39;appareil mobile : **registrationId** pour Android et **deviceToken** pour iOS. Cet identifiant représente &quot;l&#39;adresse&quot; à laquelle la notification sera envoyée.
* Le lien vers l&#39;application mobile ou la clé d&#39;intégration (**uuid**) permettant de récupérer les informations de connexion spécifiques à l&#39;application.
* Le canal sur lequel la notification sera envoyée (**wishedChannel**) : 41 pour iOS et 42 pour Android.
* Les autres données à exploiter pour la personnalisation.

Voici un exemple de traitement d&#39;un événement contenant ces informations :

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

## Surveillance des seuils {#monitor-thresholds}

Vous pouvez paramétrer les seuils d&#39;avertissement (orange) et d&#39;alerte (rouge) des indicateurs qui apparaissent dans la **Qualité de service Message Center** et **Temps traitement Message Center** rapports.

Pour ce faire, procédez comme suit :

1. Ouvrez l’assistant de déploiement dans la **instance d&#39;exécution** et accédez à la **[!UICONTROL Message Center]** page.
1. Utilisez les flèches pour modifier les seuils.


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
