---
solution: Campaign
product: Adobe Campaign
title: Paramètres de messagerie transactionnelle Campaign
description: Paramètres de messagerie transactionnelle Campaign
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 11%

---

# Paramètres de messagerie transactionnelle

:speak_bulon: En tant qu&#39;utilisateur Cloud Services géré, [contactez l&#39;Adobe](../start/support.md#support) pour installer et configurer la messagerie active Campaign Transactional dans votre environnement.

: bulb: Les fonctionnalités de messagerie transactionnelle sont détaillées dans [cette section](../send/transactional.md).

: bulb: Découvrez l&#39;architecture de la messagerie transactionnelle dans [cette page](../dev/architecture.md).

## Définition des autorisations

Pour créer de nouveaux utilisateurs pour les instances d&#39;exécution du Centre de messages hébergées sur Adobe Cloud, vous devez contacter le service d’assistance clientèle Adobe. Les utilisateurs du Centre de messages sont des opérateurs spécifiques qui nécessitent des autorisations dédiées pour accéder aux dossiers &quot;Événements temps réels&quot; (nmsRtEvent).

## Extensions de schéma

Toutes les extensions de schéma effectuées sur les schémas utilisés par **les workflows techniques du centre de message** sur le contrôle ou les instances d&#39;exécution doivent être dupliquées sur les autres instances utilisées par le module de messagerie transactionnelle Adobe Campaign.

:flèche_supérieur_droite : En savoir plus sur les workflows techniques du centre de messages dans [la documentation du Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/instance-configuration/technical-workflows.html?lang=en#control-instance-workflows)

## Envoyer des notifications Push transactionnelles

Combinée au module de canal d&#39;application mobile, la messagerie transactionnelle vous permet de transmettre des messages transactionnels par le biais de notifications sur des périphériques mobiles.

:flèche_supérieur_droite : Le canal d’applications mobiles est détaillé dans la [documentation du Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=en#sending-messages).

Pour envoyer des notifications Push transactionnelles, vous devez effectuer les configurations suivantes :

1. Installez le package **Mobile App Channel** sur les instances de pilotage et d&#39;exécution.

   >[!CAUTION]
   >
   >Vérifiez votre contrat de licence avant d&#39;installer un nouveau pack intégré Campaign.

1. Répliquez le service **Application mobile** et les applications mobiles associées sur les instances d&#39;exécution.

Pour que Campaign envoie des notifications Push transactionnelles, le événement doit contenir les éléments suivants :

* ID du périphérique mobile : **registerId** pour Android et **deviceToken** pour iOS. Cet identifiant représente l&#39;&quot;adresse&quot; à laquelle la notification sera envoyée.
* Lien vers l’application mobile ou la clé d’intégration (**uuid**) qui vous permet de récupérer des informations de connexion spécifiques à l’application.
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

