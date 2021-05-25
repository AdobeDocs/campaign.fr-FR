---
solution: Campaign v8
product: Adobe Campaign
title: Paramètres du canal email Campaign
description: Paramètres du canal email Campaign
feature: Vue d'ensemble
role: Data Engineer
level: Beginner
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 68%

---

# Paramètres du canal email Campaign

## Email Cci

Vous pouvez paramétrer Adobe Campaign pour conserver une copie des emails envoyés depuis votre plateforme.

>[!NOTE]
>La fonctionnalité Email Cci est facultative. Veuillez vérifier votre accord de licence.

Adobe Campaign ne gère pas les fichiers archivés. Il vous permet d’envoyer les messages de votre choix à une adresse dédiée, à partir de laquelle ils peuvent être traités et archivés au moyen d’un système externe.

Pour ce faire, les fichiers .eml correspondant aux emails envoyés sont transférés vers un serveur distant, comme un serveur de messagerie SMTP. La destination de l&#39;archivage est une adresse email en Cci (invisible aux destinataires de la diffusion) que vous devez spécifier.

Notez que :

* Vous ne pouvez utiliser que **une** adresse email en Cci.

* Seuls les emails envoyés sont pris en compte, les retours ne le sont pas.

:speak_ballon: En tant qu&#39;utilisateur Cloud Services géré, [contactez l&#39;Adobe](../start/campaign-faq.md#support) pour activer Email Cci dans Campaign. L&#39;adresse email en Cci de votre choix doit être fournie à l&#39;équipe Adobe qui la configurera pour vous.

Une fois que la fonctionnalité Email Cci est configurée, assurez-vous qu&#39;elle est activée dans le modèle de diffusion ou dans la diffusion via l&#39;option **Email Cci.**

![](assets/email-bcc.png)


**Rubriques connexes** dans la documentation de Campaign Classic v7 :

* [Utiliser des modèles de diffusion email](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html)
* [Découvrir les paramètres de courrier électronique](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html)
* [Présentation des diffusions en échec](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html)
