---
title: Paramètres de messagerie transactionnelle Campaign
description: Paramètres de messagerie transactionnelle Campaign
feature: Transactional Messaging
role: Admin, Developer
level: Intermediate, Experienced
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: ht
source-wordcount: '326'
ht-degree: 100%

---

# Paramètres de messagerie transactionnelle

![](../assets/do-not-localize/speech.png)  En tant qu’utilisateur Managed Cloud Services, [contactez Adobe](../start/campaign-faq.md#support) pour installer et configurer la messagerie transactionnelle de Campaign dans votre environnement.

![](../assets/do-not-localize/glass.png) Les fonctionnalités de messagerie transactionnelle sont décrites dans [cette section](../send/transactional.md).

![](../assets/do-not-localize/glass.png) Découvrez l&#39;architecture de la messagerie transactionnelle sur [cette page](../architecture/architecture.md).

## Définition des autorisations

Pour créer des utilisateurs pour les instances d’exécution Message Center hébergées sur Adobe Cloud, vous devez contacter l’assistance clientèle d’Adobe. Les utilisateurs de Message Center sont des opérateurs spécifiques qui ont besoin d’autorisations dédiées pour accéder aux dossiers « Evénements temps réel » (nmsRtEvent).

## Extensions de schéma

Les extensions de schéma effectuées sur les schémas utilisés par les **workflows techniques de Message Center** sur les instances de pilotage ou d&#39;exécution doivent être dupliquées sur les autres instances utilisées par le module des messages transactionnels d&#39;Adobe Campaign.

![](../assets/do-not-localize/book.png) En savoir plus sur les workflows techniques de Message Center dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/configure-transactional-messaging/additional-configurations.html?lang=fr#technical-workflows).

## Envoi de notifications push transactionnelles

Couplés au module Canal des applications mobiles, les messages transactionnels permettent d&#39;émettre des messages transactionnels au travers des notifications push sur des applications mobiles.

![](../assets/do-not-localize/book.png) Le canal des applications mobiles est décrit dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=fr#sending-messages).

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
