---
title: Envoi de SMS avec Adobe Campaign
description: Prise en main des SMS dans Campaign
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 19c5a15a0f42285fc3b1a448f3cbf474d741e6e2
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 19%

---

# Commencer avec les SMS {#gs-sms-channel}

Utilisez Adobe Campaign pour envoyer des SMS à vos clients sur leurs appareils mobiles. Vous pouvez créer, personnaliser et prévisualiser des messages au format texte à partir de l&#39;éditeur de SMS.

Pour diffuser des SMS vers des appareils mobiles avec Adobe Campaign, vous devez :

* Un compte externe configuré sur le canal **[!UICONTROL Mobile (SMS)]**. Découvrez comment configurer le canal SMS sur votre [infrastructure de mid-sourcing](sms-mid-sourcing.md). Pour cette configuration, vous devez comprendre les [paramètres du compte externe SMPP](smpp-external-account.md) et les [ caractéristiques du canal SMS](sms-channel.md).
Une fois cette configuration effectuée, vérifiez votre connexion SMPP et sachez comment la résoudre si nécessaire. [En savoir plus](smpp-connection.md).

* Un modèle de diffusion SMS correctement associé à ce compte externe.


>[!NOTE]
>
>Vous pouvez également utiliser Adobe Campaign pour envoyer des messages [LINE](../../send/line.md), avec du texte et/ou des images et des liens.


<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="create-sms.md">
<img alt="Créer un SMS" src="../../assets/do-not-localize/sms-sending.jpg">
</a>
<div><a href="create-sms.md"><strong>Création d’une diffusion SMS</strong>
</div>
<p>
</td>
<td>
<a href="sms-content.md">
<img alt="Contenu SMS" src="../../assets/do-not-localize/sms.jpg">
</a>
<div>
<a href="sms-content.md"><strong> Définition et personnalisation du contenu </strong></a>
</div>
<p></td>
<td>
<a href="sms-audience.md">
<img alt="Audience" src="../../assets/do-not-localize/sms-opt-out.jpg">
</a>
<div>
<a href="sms-audience.md"><strong>Gestion des opt-out</strong></a>
</div>
<p>
</td>
<td>
<a href="smpp-external-account.md">
<img alt="Configuration" src="../../assets/do-not-localize/sms-config.jpg">
</a>
<div>
<a href="smpp-external-account.md"><strong>Configurer le canal SMS</strong></a>
</div>
<p>
</td>
</tr></table>
