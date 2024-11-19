---
title: Envoi de SMS avec Adobe Campaign
description: Prise en main des SMS dans Campaign
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 95dca48ae0e2ee82b80464cdf9414538776969ad
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 100%

---

# Prise en main des SMS {#gs-sms-channel}

Utilisez Adobe Campaign pour envoyer des messages texte aux clients et aux clientes sur leurs appareils mobiles. Vous pouvez créer, personnaliser et prévisualiser des messages au format texte à partir de l’éditeur de SMS.

Pour diffuser des SMS sur des appareils mobiles avec Adobe Campaign, il vous faut :

* un compte externe configuré sur le canal **[!UICONTROL Mobile (SMS)]**. Découvrez comment configurer le canal SMS sur votre [infrastructure de midsourcing](sms-mid-sourcing.md). Pour cette configuration, vous devez comprendre les [paramètres du compte externe SMPP](smpp-external-account.md) et les [caractéristiques du canal SMS](sms-channel.md).
Après cette configuration, vérifiez votre connexion SMPP et vos connaissances en matière de résolution des problèmes si nécessaire. [En savoir plus](smpp-connection.md).

* un modèle de diffusion SMS correctement lié à ce compte externe.


>[!NOTE]
>
>Vous pouvez également utiliser Adobe Campaign pour envoyer des [notifications push](../push.md) et des messages [LINE](../line.md) aux appareils mobiles.


<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="create-sms.md">
<img alt="Créer un SMS" src="../../assets/do-not-localize/sms-sending.jpg">
</a>
<div><a href="create-sms.md"><strong>Créer une diffusion SMS</strong>
</div>
<p>
</td>
<td>
<a href="sms-content.md">
<img alt="Contenu SMS" src="../../assets/do-not-localize/sms-create.jpeg">
</a>
<div>
<a href="sms-content.md"><strong>Définir le contenu de votre SMS</strong></a>
</div>
<p></td>
<td>
<a href="sms-audience.md">
<img alt="Audience des SMS" src="../../assets/do-not-localize/sms-opt-out.jpg">
</a>
<div>
<a href="sms-audience.md"><strong>Sélectionnner l’audience</strong></a>
</div>
<p>
</td>
<td>
<a href="smpp-external-account.md">
<img alt="Configuration des SMS" src="../../assets/do-not-localize/sms-config.jpg">
</a>
<div>
<a href="smpp-external-account.md"><strong>Configurer le canal SMS</strong></a>
</div>
<p>
</td>
</tr></table>
