---
title: Envoi de SMS avec Adobe Campaign
description: Prise en main des SMS dans Campaign
feature: SMS
role: User, Developer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
TQID: https://experienceleague.adobe.com/7ChOYJmYScxaAoqnruyMv-8n0AkXgYAIlt1783hTjvY
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 176
ht-degree: 92%

---

# Prise en main des SMS {#gs-sms-channel}

Utilisez Adobe Campaign pour envoyer des messages texte aux clients et aux clientes sur leurs appareils mobiles. Vous pouvez créer, personnaliser et prévisualiser des messages au format texte à partir de l’éditeur de SMS.

Pour diffuser des SMS sur des appareils mobiles avec Adobe Campaign, il vous faut :

* un compte externe configuré sur le canal **[!UICONTROL Mobile (SMS)]**. Découvrez comment configurer le canal SMS sur votre [infrastructure de midsourcing](sms-mid-sourcing.md). Pour cette configuration, vous devez comprendre les [paramètres du compte externe SMPP](smpp-external-account.md) et les [caractéristiques du canal SMS](sms-channel.md).
Après cette configuration, vérifiez votre connexion SMPP et vos connaissances en matière de résolution des problèmes si nécessaire. [En savoir plus](smpp-connection.md).

* un modèle de diffusion SMS correctement lié à ce compte externe.

Adobe Campaign prend en charge deux connecteurs SMS utilisés pour envoyer des SMS à vos clients. [En savoir plus](sms-connectors.md).

>[!NOTE]
>
>Vous pouvez également utiliser Adobe Campaign pour envoyer des [notifications push](../push.md) et des messages [LINE](../line/line.md) aux appareils mobiles.

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
