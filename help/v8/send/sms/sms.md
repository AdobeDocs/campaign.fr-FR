---
title: Envoi de SMS avec Adobe Campaign
description: Prise en main des SMS dans Campaign
feature: SMS
role: User, Data Engineer
level: Beginner
badge: label="Disponibilité limitée" type="Informative"
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: af1d453179c2d739eca243b435dec90a4b8e2dd5
workflow-type: ht
source-wordcount: '303'
ht-degree: 100%

---

# Commencer avec les SMS {#gs-sms-channel}

Utilisez Adobe Campaign pour envoyer des messages SMS personnalisés.

>[!IMPORTANT]
>
>Cette documentation concerne Adobe Campaign v8.7.2 et les versions ultérieures.
>
>Pour les versions plus anciennes, consultez la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/fr/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up).

>[!NOTE]
>
>Adobe Campaign permet également d&#39;envoyer des notifications push sur les mobiles, via son option **Canal des applications mobiles Adobe Campaign (NMAC)**. En savoir plus dans [cette section](../push.md).

La simplicité et la facilité d’utilisation des SMS en font un canal de communication très précieux en plus de sa robustesse et de sa compatibilité inégalée sur des milliards de terminaux.

Il existe deux façons principales d’envoyer un SMS :

* Envoyez-le manuellement à partir d’un téléphone. C’est la façon habituelle de communiquer directement entre les personnes.
* Envoyez-le depuis Internet. C’est la manière qu’Adobe Campaign utilise pour envoyer des messages. Pour cela, vous avez besoin d’un fournisseur de services de SMS destiné à connecter Internet au réseau mobile.

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
