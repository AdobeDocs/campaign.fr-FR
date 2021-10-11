---
title: Paramètres de messagerie transactionnelle Campaign
description: Paramètres de messagerie transactionnelle Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
source-git-commit: eb8ad88ffd9dbaaf1f9ace2e88ba4486711bc72d
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 96%

---

# Paramètres de messagerie transactionnelle

?? En tant qu&#39;utilisateur Managed Cloud Services, [contactez Adobe](../start/campaign-faq.md#support) pour installer et configurer la messagerie transactionnelle de Campaign dans votre environnement.

![](../assets/do-not-localize/glass.png) Les fonctionnalités de messagerie transactionnelle sont décrites dans [cette section](../send/transactional.md).

![](../assets/do-not-localize/glass.png) Découvrez l&#39;architecture de la messagerie transactionnelle sur [cette page](../dev/architecture.md).

## Définition des autorisations

Pour créer des utilisateurs pour les instances d’exécution Message Center hébergées sur Adobe Cloud, vous devez contacter l’assistance clientèle d’Adobe. Les utilisateurs de Message Center sont des opérateurs spécifiques qui ont besoin d’autorisations dédiées pour accéder aux dossiers « Evénements temps réel » (nmsRtEvent).

## Extensions de schéma

Les extensions de schéma effectuées sur les schémas utilisés par les **workflows techniques de Message Center** sur les instances de pilotage ou d&#39;exécution doivent être dupliquées sur les autres instances utilisées par le module des messages transactionnels d&#39;Adobe Campaign.

![](../assets/do-not-localize/book.png) En savoir plus sur les workflows techniques de Message Center dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/configure-transactional-messaging/additional-configurations.html?lang=fr#technical-workflows).

## Envoi de notifications push transactionnelles

Couplée au module Canal applications mobiles (Mobile App Channel), la messagerie transactionnelle permet de transmettre des messages transactionnels par l&#39;intermédiaire de notifications push sur les appareils mobiles.

![](../assets/do-not-localize/book.png) Le canal applications mobiles (Mobile App Channel) est décrit dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=fr#sending-messages).

Pour envoyer des notifications push transactionnelles, vous devez exécuter les configurations suivantes :

1. Installez le package **Mobile App Channel** sur les instances de pilotage et d&#39;exécution.

   >[!CAUTION]
   >
   >Vérifiez votre contrat de licence avant d&#39;installer un nouveau package intégré Campaign.

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
