---
title: Module complémentaire de sécurité amélioré
description: Prise en main du module complémentaire de sécurité amélioré de Campaign
feature: Configuration
role: Developer
level: Experienced
hide: true
hidefromtoc: true
exl-id: 7c586836-82e1-45fb-9c28-18361572e1fa
source-git-commit: f9b064dffa0f8792e8653760cb2ac44cfdf43848
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 1%

---

# Module complémentaire de sécurité amélioré {#enhanced-security}

Pour sécuriser davantage votre connexion réseau et offrir une meilleure sécurité à vos ressources, [!DNL Adobe Campaign] offre une nouvelle **Sécurité renforcée** module complémentaire .

Ce module complémentaire comprend deux fonctionnalités de l’écosystème :

* [Intégration de CMK sécurisée](#secure-cmk-integration)

* [Tunneling VPN sécurisé](#secure-vpn-tunneling)

Ces fonctionnalités sont présentées ci-dessous.

## Intégration de CMK sécurisée {#secure-cmk-integration}

La variable **Intégration de la clé gérée par le client sécurisée (CMK)** vous permet de chiffrer votre instance et vos données à l’aide de votre propre clé via votre compte Amazon Web Services (AWS).

Les clés gérées par le client sont des clés de service de gestion des clés (KMS) dans votre compte AWS que vous créez, possédez et gérez. Vous avez un contrôle total sur ces clés KMS et vous pouvez les utiliser pour crypter et décrypter des données. En vous rendant responsable de la génération et de la gestion des clés de cryptage, cette fonctionnalité vous permet de mieux les contrôler, notamment de révoquer une clé.

>[!CAUTION]
>
>Si vous révoquez une clé, vous devez être conscient des impacts. [En savoir plus](#cmk-callouts)

Pour activer l&#39;intégration du CMK avec Campaign, procédez comme suit :

1. Se connecter à [Amazon Web Services (AWS)](https://aws.amazon.com/){target="_blank"} compte .

1. Générez une clé avec rotation automatique sur à l’aide du service de gestion des clés (KMS) AWS. [Découvrez comment](https://docs.aws.amazon.com/kms/latest/developerguide/create-keys.html){target="_blank"}.

1. Appliquez la politique qui vous a été fournie par Adobe dans votre compte AWS, afin d’accorder l’accès à vos ressources. [En savoir plus](https://docs.aws.amazon.com/kms/latest/developerguide/key-policy-services.html){target="_blank"}. <!--link TBC-->

1. Partagez vos [Amazon Resource Name (key ARN)](https://docs.aws.amazon.com/kms/latest/developerguide/find-cmk-id-arn.html){target="_blank"} avec [!DNL Adobe Campaign]. Pour ce faire, contactez votre représentant Adobe. <!--or Adobe transition manager?-->

1. Créez et testez les règles Amazon EventBridge pour permettre la surveillance de vos clés par Adobe. &#x200B; [En savoir plus](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-rules.html){target="_blank"}.

## Tunneling VPN sécurisé {#secure-vpn-tunneling}

La variable **Tunneling réseau privé virtuel (VPN) sécurisé** est un VPN site à site qui fournit un accès sécurisé à vos données en transit sur un réseau privé, de vos locaux à la variable [!DNL Adobe Campaign] instance.

<!--As it connects two networks together, it is a site-to-site VPN.-->

Afin d&#39;assurer une haute disponibilité, il utilise deux tunnels pour éviter toute panne en cas de problème sur un tunnel.

Trois cas pratiques sont pris en charge :

* Federated Data Access (FDA) sur VPN<!--to access your on-premise database from the Campaign instance over VPN-->

* Connexion d’instance via VPN à partir d’un client épais

* Accès SFTP de l’instance par VPN

>[!CAUTION]
>
>Seules les bases de données sur site et les périphériques VPN compatibles avec AWS sont pris en charge. [En savoir plus](#vpn-callouts)

Pour garantir une utilisation correcte de cette fonctionnalité, suivez les instructions ci-dessous :

* Configurez votre VPN latéral en fonction de la configuration VPN côté Adobe.

* Gardez les deux tunnels en haute disponibilité.

* Surveillez votre tunnel latéral.

* Vous devez être l’initiateur du tunnel et être aligné pour réinitialiser la connexion si le tunnel tombe en panne.

* Configurez un mécanisme de reprise à votre fin en cas d’échec de connexion.

## Mécanismes de sécurisation {#callouts}

Certaines barrières de sécurité et limites relatives aux fonctionnalités de sécurité améliorées sont répertoriées ci-dessous.

* Assurez-vous que tous les cas d’utilisation de l’intégration du CMK sécurisé/du tunneling VPN fonctionnent.

<!--* Adobe shall reach out to you or your technical team if any issue is found on your side.

* Currently, when using Enhanced security features, any communication with Adobe must be performed manually via email.-->

* L’Adobe surveillera :

   * Disponibilité de votre instance et passez à l’alerte si la clé n’est pas disponible.

   * Les tunnels VPN, et passer à l&#39;alerte en cas de problème.

### Barrières de sécurité de l’intégration CMK sécurisées {#cmk-callouts}

* Adobe ne fournit pas de compte AWS. Vous devez disposer de votre propre compte AWS et le configurer pour générer et partager votre clé avec Adobe.

* Uniquement [Service de gestion des clés AWS](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html){target="_blank"} Les clés (KMS) sont prises en charge. Aucune clé générée par le client en dehors de KMS ne peut être utilisée. &#x200B;

* Un temps d’arrêt est nécessaire pour la première configuration. &#x200B;La durée d’interruption dépend de la taille de votre base de données.

* En tant que propriétaire et en gérant la clé, vous devez tendre la main vers l&#39;Adobe en cas de modification de votre clé. &#x200B;

* Vous pouvez contrôler votre clé à l’aide de [AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html){target="_blank"} et révoquez-la si nécessaire. &#x200B;

* Si vous révoquez, désactivez ou supprimez la clé, vos ressources et votre instance cryptées deviennent inaccessibles jusqu’à ce que vous restauriez l’action correspondante.

  >[!CAUTION]
  >
  >Si vous désactivez la clé et que vous ne revenez pas à cette action dans les 7 jours, votre base de données ne peut être récupérée qu’à partir de la sauvegarde.
  >
  >Si vous supprimez la clé et que vous ne revenez pas à cette action dans les 30 jours, toutes vos données sont définitivement supprimées et seront perdues. &#x200B;

### Sécurisation des barrières de sécurité de tunneling VPN {#vpn-callouts}

* Actuellement, seules les bases de données on-premise sont prises en charge, telles que<!--Richa to check the list with PM-->:

   * MySQL
   * Netezza 
   * Oracle 
   * SAP HANA 
   * SQL Server 
   * Sybase 
   * Teradata 
   * Hadoop via HiveSQL

* Seuls les périphériques VPN compatibles avec AWS sont pris en charge. Une liste des périphériques compatibles est disponible sur [cette page](https://docs.aws.amazon.com/vpn/latest/s2svpn/your-cgw.html#example-configuration-files){target="_blank"}<!--check which list should be communicated-->.

* La connectivité VPN à des tiers ou à des fournisseurs externes n’est pas prise en charge.

* Les VPN supplémentaires gérés par l’Adobe et les bases de données privées Cloud ne sont pas inclus.
