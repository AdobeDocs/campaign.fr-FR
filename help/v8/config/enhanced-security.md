---
title: Module complémentaire de sécurité améliorée Campaign
description: Commencer à utiliser le module complémentaire Campaign de sécurité améliorée
feature: Configuration
role: Developer
level: Experienced
exl-id: 7c586836-82e1-45fb-9c28-18361572e1fa
source-git-commit: 55c16fe19125ea54035a8f97928484c7baea161b
workflow-type: ht
source-wordcount: '753'
ht-degree: 100%

---


# Module complémentaire Campaign de sécurité améliorée {#enhanced-security}

Pour sécuriser davantage votre connexion réseau et offrir une meilleure sécurité à vos ressources, [!DNL Adobe Campaign] fournit un nouveau module complémentaire de **Sécurité améliorée**.

Ce module complémentaire comprend deux fonctionnalités réseau :

* [Intégration de la clé sécurisée gérée par le client ou la cliente (CMK)](#secure-cmk-integration)

* [Tunnellisation du réseau privé virtuel (VPN) sécurisé](#secure-vpn-tunneling)

Ces fonctionnalités sont décrites ci-dessous.

Quelques mécanismes de sécurisation et limites en lien avec les fonctionnalités de sécurité améliorée sont répertoriés sur cette page. En outre, vous devez vous assurer que tous les cas d’utilisation de l’intégration sécurisée de CMK/de la tunnellisation du VPN sécurisé fonctionnent.

Une fois ces fonctionnalités implémentées, Adobe surveille les éléments suivants :

* La disponibilité de votre instance, et envoie une alerte si la clé n’est pas disponible.

* Les tunnels VPN, et envoie une alerte en cas de problème.

## Intégration de la clé sécurisée gérée par le client ou la cliente {#secure-cmk-integration}

L’**intégration de la clé sécurisée gérée par le client ou la cliente (CMK)** vous permet de chiffrer des données inactives à l’aide de votre propre clé via votre compte Amazon Web Services (AWS).

Les clés gérées par le client ou la cliente sont des clés de service de gestion des clés (KMS) dans votre compte AWS que vous créez, possédez et gérez. Vous avez un contrôle total sur ces clés KMS et vous pouvez les utiliser pour chiffrer et déchiffrer des données. En vous rendant responsable de la génération et de la gestion des clés de chiffrement, cette fonctionnalité vous permet de mieux les contrôler, en offrant notamment l’option de révoquer une clé.

>[!CAUTION]
>
>Si vous révoquez une clé, vous devez avoir conscience des impacts que cela produit. [En savoir plus](#cmk-callouts)

Pour configurer l’intégration de CMK avec Campaign, procédez comme suit :

1. Connectez-vous à votre compte [Amazon Web Services (AWS)](https://aws.amazon.com/){target="_blank"}.

1. Générez une clé avec la rotation automatique activée à l’aide du service de gestion de clés (KMS) AWS. [Découvrez comment procéder](https://docs.aws.amazon.com/kms/latest/developerguide/create-keys.html){target="_blank"}.

1. Appliquez la politique qui vous a été fournie par Adobe dans votre compte AWS, afin d’accorder l’accès à vos ressources. [En savoir plus](https://docs.aws.amazon.com/kms/latest/developerguide/key-policy-services.html){target="_blank"}.<!--link TBC-->

1. Partagez votre [Nom de ressource Amazon (clé ARN)](https://docs.aws.amazon.com/kms/latest/developerguide/find-cmk-id-arn.html){target="_blank"} avec [!DNL Adobe Campaign]. Pour ce faire, contactez votre représentant ou représentante Adobe.<!--or Adobe transition manager?-->

1. Créez et testez les règles Amazon EventBridge pour permettre la surveillance de vos clés par Adobe. [En savoir plus](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-rules.html){target="_blank"}.


### Mécanismes de sécurisation et limitations {#cmk-callouts}

Les mécanismes de sécurisation et limitations ci-après s’appliquent à l’intégration de CMK à Adobe Campaign v8 :

* Adobe ne fournit pas de compte [Amazon Web Services (AWS)](https://aws.amazon.com/){target="_blank"}. Vous devez disposer de votre propre compte AWS et le configurer pour générer et partager votre clé avec Adobe.

* Seules les clés du [Service de gestion de clés AWS](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html){target="_blank"} (KMS) sont prises en charge. Aucune clé générée par le client ou la cliente en dehors du KMS ne peut être utilisée.

* Des temps d’arrêt sont attendus lors de la première configuration.La durée de l’interruption dépend de la taille de votre base de données.

* En tant que client ou cliente, vous détenez et devez conserver la clé. Vous devez contacter Adobe en cas de changement de la clé.

* Vous pouvez vérifier votre clé à l’aide d’[AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html){target="_blank"} et la révoquer si nécessaire.

* Si vous révoquez, désactivez ou supprimez la clé, vos ressources et votre instance chiffrées deviennent inaccessibles jusqu’à ce que vous annuliez l’action correspondante.

  >[!CAUTION]
  >
  >Si vous désactivez la clé et que vous n’annulez pas cette action dans les 7 jours, votre base de données ne pourra être récupérée qu’à partir de la sauvegarde.
  >
  >Si vous supprimez la clé et que vous n’annulez pas cette action dans les 30 jours, toutes vos données seront définitivement supprimées et seront perdues.

## Tunnelisation du réseau privé virtuel sécurisé {#secure-vpn-tunneling}

La tunnellisation sécurisée de **Réseau privé virtuel (VPN)** est un VPN site à site qui fournit un accès sécurisé à vos données en transit sur un réseau privé, de vos locaux jusqu’à l’instance [!DNL Adobe Campaign].

<!--As it connects two networks together, it is a site-to-site VPN.-->

Afin de garantir une haute disponibilité, cette fonctionnalité utilise deux tunnels pour éviter toute panne en cas de problème sur un tunnel.

Trois cas d’utilisation sont pris en charge :

* Federated Data Access (FDA) via un VPN, pour accéder à votre base de données On-Premise à partir de l’instance Campaign via un VPN

* Connexion à l’instance via un VPN à partir d’un client épais

* Accès SFTP à l’instance via un VPN

>[!CAUTION]
>
>Seuls les bases de données On-Premise et les périphériques VPN compatibles avec AWS sont pris en charge. [En savoir plus](#vpn-callouts)

Pour garantir une utilisation correcte de cette fonctionnalité, suivez les instructions ci-dessous :

* Configurez le VPN de votre côté en fonction de la configuration du VPN côté Adobe.

* Gardez les deux tunnels actifs pour bénéficier d’une haute disponibilité.

* Surveillez le tunnel de votre côté.

* Vous devez être l’initiateur ou l’initiatrice du tunnel et vous aligner pour réinitialiser la connexion si le tunnel cesse de fonctionner.

* Configurez un mécanisme de reconnexion de votre côté en cas de déconnexion accidentelle.


### Mécanismes de sécurisation et limitations {#vpn-callouts}

Les mécanismes de sécurisation et limitations ci-après s’appliquent à l’intégration de la tunnellisation du VPN à Adobe Campaign v8 :

* Seules les bases de données On-Premise sont prises en charge, telles que<!--Richa to check the list with PM--> :

   * MySQL
   * Netezza
   * Oracle
   * SAP HANA
   * SQL Server
   * Sybase
   * Teradata
   * Hadoop via HiveSQL

* Seuls les périphériques VPN compatibles avec AWS sont pris en charge. Une liste des périphériques compatibles est disponible sur [cette page](https://docs.aws.amazon.com/vpn/latest/s2svpn/your-cgw.html#example-configuration-files){target="_blank"}<!--check which list should be communicated-->.

* Les connexions VPN à des tiers ou à des fournisseurs externes ne sont pas prises en charge.

* Les VPN supplémentaires gérés par Adobe et les bases de données privées Cloud ne sont pas inclus.
