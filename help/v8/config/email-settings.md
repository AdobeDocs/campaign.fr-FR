---
product: Adobe Campaign
title: Paramètres du canal e-mail de Campaign
description: Paramètres du canal e-mail de Campaign
feature: Vue d'ensemble
role: Data Engineer
level: Beginner
source-git-commit: 0566d40370a3e14d5205861509f7c1ae8cb4b22d
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 100%

---

# Paramètres du canal e-mail de Campaign

## E-mail Cci

Vous pouvez paramétrer Adobe Campaign pour conserver une copie des e-mails envoyés depuis votre plateforme.

>[!NOTE]
>La fonctionnalité E-mail Cci est facultative. Veuillez vérifier votre accord de licence.

Adobe Campaign ne gère pas les fichiers archivés. Il vous permet d&#39;envoyer les messages de votre choix à une adresse dédiée, à partir de laquelle ils peuvent être traités et archivés au moyen d&#39;un système externe.

Pour ce faire, les fichiers .eml correspondant aux e-mails envoyés sont transférés vers un serveur distant, comme un serveur de messagerie SMTP. La destination de l&#39;archivage est une adresse e-mail en Cci (invisible aux destinataires de la diffusion) que vous devez spécifier.

Notez que :

* Vous ne pouvez utiliser qu&#39;**une seule** adresse e-mail en Cci.

* Seuls les e-mails envoyés sont pris en compte, les retours ne le sont pas.

[!DNL :speech_balloon:] En tant qu&#39;utilisateur Managed Cloud Services, [contactez Adobe](../start/campaign-faq.md#support) pour activer l&#39;option E-mail Cci dans Campaign. L&#39;adresse e-mail en Cci de votre choix doit être fournie à l&#39;équipe Adobe qui la configurera pour vous.

Une fois que la fonctionnalité E-mail Cci est configurée, assurez-vous qu&#39;elle est activée dans le modèle de diffusion ou dans la diffusion via l&#39;option **E-mail Cci**.

![](assets/email-bcc.png)


**Rubriques connexes** dans la documentation de Campaign Classic v7 :


[!DNL :arrow_upper_right:] [Générer la page miroir](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html?lang=fr#generating-mirror-page){target=&quot;_blank&quot;}

[!DNL :arrow_upper_right:] [Sélectionner le format d’e-mail ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html?lang=fr#selecting-message-formats){target=&quot;_blank&quot;}

[!DNL :arrow_upper_right:] [Sélectionner le codage des caractères ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html?lang=fr#character-encoding){target=&quot;_blank&quot;}

[!DNL :arrow_upper_right:] [Définir l&#39;adresse e-mail de rebond ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html?lang=fr#managing-bounce-emails){target=&quot;_blank&quot;}

[!DNL :arrow_upper_right:] [Utiliser les modèles de diffusion par e-mail ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=fr){target=&quot;_blank&quot;}

[!DNL :arrow_upper_right:] [Comprendre les échecs de diffusion](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html?lang=fr){target=&quot;_blank&quot;}
