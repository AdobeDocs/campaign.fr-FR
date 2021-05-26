---
solution: Campaign v8
product: Adobe Campaign
title: Paramètres des messages transactionnels de Campaign
description: Paramètres des messages transactionnels de Campaign
feature: Vue d'ensemble
role: Data Engineer
level: Beginner
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 11%

---

# Paramètres des messages transactionnels

:speak_ballon: En tant qu’utilisateur Cloud Services géré, [contactez l’Adobe](../start/campaign-faq.md#support) pour installer et configurer les messages transactionnels Campaign dans votre environnement.

[!DNL :bulb:] Les fonctionnalités des messages transactionnels sont présentées dans  [cette section](../send/transactional.md).

[!DNL :bulb:] Découvrez l’architecture des messages transactionnels dans  [cette page](../dev/architecture.md).

## Définition des autorisations

Pour créer de nouveaux utilisateurs pour les instances d&#39;exécution Message Center hébergées sur Adobe Cloud, vous devez contacter l&#39;assistance clientèle d&#39;Adobe. Les utilisateurs de Message Center sont des opérateurs spécifiques qui nécessitent des permissions dédiées pour accéder aux dossiers &quot;Evénements temps réel&quot; (nmsRtEvent).

## Extensions de schéma

Toutes les extensions de schéma effectuées sur les schémas utilisés par les **workflows techniques de Message Center** sur les instances de pilotage ou d&#39;exécution doivent être dupliquées sur les autres instances utilisées par le module des messages transactionnels Adobe Campaign.

:[!DNL :arrow_upper_right:] : En savoir plus sur les workflows techniques de Message Center dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/instance-configuration/technical-workflows.html?lang=en#control-instance-workflows)

## Envoi de notifications push transactionnelles

Lorsqu’elle est combinée avec le module Mobile App Channel , la messagerie transactionnelle vous permet de transmettre des messages transactionnels par le biais de notifications sur des appareils mobiles.

:[!DNL :arrow_upper_right:] : Le canal Applications mobiles est présenté dans la [documentation du Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=en#sending-messages).

Pour envoyer des notifications push transactionnelles, vous devez effectuer les configurations suivantes :

1. Installez le package **Mobile App Channel** sur les instances de pilotage et d&#39;exécution.

   >[!CAUTION]
   >
   >Vérifiez votre contrat de licence avant d&#39;installer un nouveau package natif Campaign.

1. Répliquez le service **Application mobile** et les applications mobiles associées sur les instances d&#39;exécution.

Pour que Campaign puisse envoyer des notifications push transactionnelles, l&#39;événement doit contenir les éléments suivants :

* L’identifiant de l’appareil mobile : **registrationId** pour Android et **deviceToken** pour iOS. Cet identifiant représente l’&quot;adresse&quot; à laquelle la notification sera envoyée.
* Le lien vers l’application mobile ou clé d’intégration (**uuid**) qui permet de récupérer les informations de connexion spécifiques à l’application.
* Le canal sur lequel la notification sera envoyée (**wishedChannel**) : 41 pour iOS et 42 pour Android.
* Autres données à exploiter pour la personnalisation.

Voici un exemple de traitement d&#39;un événement contenant ces informations :

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

