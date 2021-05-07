---
solution: Campaign
product: Adobe Campaign
title: Paramètres du canal de messagerie Campaign
description: Paramètres du canal de messagerie Campaign
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 73%

---

# Paramètres du canal de messagerie Campaign

## Email Cci

Vous pouvez paramétrer Adobe Campaign pour conserver une copie des emails envoyés depuis votre plateforme.

Toutefois, Adobe Campaign ne gère pas lui-même les fichiers archivés : il vous permet d&#39;envoyer les messages de votre choix à une adresse dédiée, depuis laquelle ils peuvent être traités et archivés dans un système externe.

Pour ce faire, les fichiers .eml correspondant aux emails envoyés sont transférés vers un serveur distant, comme un serveur de messagerie SMTP. La destination de l&#39;archivage est une adresse email en Cci (invisible aux destinataires de la diffusion) que vous devez spécifier.

Notez que :

* Vous ne pouvez utiliser qu&#39;une seule adresse email en Cci.

* Seuls les emails envoyés sont pris en compte, les retours ne le sont pas.

Une fois que la fonctionnalité Email Cci est configurée, assurez-vous qu&#39;elle est activée dans le modèle de diffusion ou dans la diffusion via l&#39;option **Email Cci.**

:flèche_supérieur_droite : Pour plus d’informations à ce sujet, consultez la [documentation du Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html?lang=en#email-bcc).

**Remarque** : La fonctionnalité de Cci par courrier électronique est facultative. Veuillez vérifier votre contrat de licence.

:speak_bulon: En tant qu’utilisateur Cloud Services géré, [contactez l’Adobe](../start/support.md#support) pour activer le contrôle de compte de messagerie électronique dans Campaign. L&#39;adresse email en Cci de votre choix doit être fournie à l&#39;équipe Adobe qui la configurera pour vous.