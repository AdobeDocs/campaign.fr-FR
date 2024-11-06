---
title: Envoi de SMS avec Adobe Campaign
description: Prise en main des SMS dans Campaign
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 5b2638927e39b6f839fb3a8639fe106d2c519fbf
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 79%

---

# Commencer avec les SMS {#gs-sms-channel}

Adobe Campaign vous permet de diffuser des [SMS](../send/sms/sms.md) personnalisés sur des mobiles.

Pour les SMS, vous pouvez créer, modifier et personnaliser des messages au format texte uniquement. Vous pouvez également prévisualiser les SMS avant leur envoi.

>[!NOTE]
>
>Vous pouvez également utiliser Adobe Campaign pour envoyer des messages [LINE](../send/line.md), avec du texte et/ou des images et des liens.

Pour diffuser des SMS vers un téléphone mobile avec Adobe Campaign, vous devez :

* un compte externe paramétré sur le canal **[!UICONTROL Mobile (SMS)]** ou **[!UICONTROL LINE]**,
* Un modèle de diffusion SMS correctement associé à ce compte externe.

Vous pouvez voir dans cette documentation les étapes de configuration, d’envoi et de surveillance d’une diffusion SMS :

* **Configurer le canal SMS**

Tout d’abord, vous devez configurer le canal SMS sur votre [infrastructure de midsourcing](sms-mid-sourcing.md).

<!--The steps depend on the platform: either you have [a standalone instance](sms-standalone-instance.md) or you are in [a mid-sourcing infrastructure](sms-mid-sourcing.md).-->

Pour cette configuration, vous devez comprendre les [paramètres du compte externe SMPP](smpp-external-account.md) et les [ caractéristiques du canal SMS](sms-channel.md).

Après cette configuration, vérifiez votre [connexion SMPP et vos connaissances en matière de résolution des problèmes si nécessaire](smpp-connection.md).

* **Créer votre première diffusion par SMS**

Pour commencer la configuration de votre diffusion SMS, procédez comme suit :

1. Créez votre diffusion et remplissez les [paramètres de diffusion SMS](sms-delivery-settings.md).

1. [Définissez le contenu](sms-content.md) de votre diffusion.

1. [Sélectionnner l’audience](sms-audience.md).

Les étapes de définition d’une audience sont décrites sur [cette page](../../audiences/create-audiences.md).

* **Valider et envoyer les SMS**

Après la création de votre diffusion, procédez comme suit :

1. [Envoyez des BAT](sms-proofs.md) pour valider le rendu et le contenu.

1. Ensuite, [envoyez à l’audience finale](sms-send.md).

* **Surveiller et suivre des SMS**

Après l’envoi, [apprenez à surveiller et suivre vos SMS](sms-monitor.md).
