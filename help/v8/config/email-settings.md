---
title: Paramètres du canal e-mail de Campaign
description: Paramètres du canal e-mail de Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: e4e3fb49-9942-4e2d-a020-557d1ac5dcdc
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 49%

---

# Paramètres du canal e-mail de Campaign

## E-mail Cci {#email-bcc}

<!--
>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)-->

Vous pouvez paramétrer Adobe Campaign pour conserver une copie des e-mails envoyés depuis votre plateforme.

Adobe Campaign ne gère pas les fichiers archivés. Il vous permet d&#39;envoyer les messages de votre choix à une adresse email dédiée en Cci (copie carbone invisible), à partir de laquelle ils peuvent être traités et archivés à l&#39;aide d&#39;un système externe. Les fichiers .eml correspondant aux emails envoyés peuvent ensuite être transférés vers un serveur distant, tel qu’un serveur de messagerie SMTP.

>[!CAUTION]
>
>Pour des raisons de confidentialité, les emails en Cci doivent être traités dans un système d’archivage capable de stocker en toute sécurité les informations d’identification personnelles (PII).

La destination d&#39;archivage est l&#39;adresse email en Cci de votre choix, qui restera invisible pour les destinataires de la diffusion.

![](../assets/do-not-localize/speech.png)  En tant qu’utilisateur Cloud Services géré, [contact Adobe](../start/campaign-faq.md#support){target=&quot;_blank&quot;} pour communiquer l’adresse email en Cci à utiliser pour l’archivage.

Une fois l&#39;adresse email en Cci définie, vous devez activer l&#39;option dédiée au niveau de la diffusion.

>[!CAUTION]
>
>Lors de la création d&#39;une diffusion ou d&#39;un modèle de diffusion, **[!UICONTROL Email Cci]** n’est pas activé par défaut. Vous devez l&#39;activer manuellement dans la diffusion email ou le modèle de diffusion.


Pour ce faire, procédez comme suit :

1. Accédez à **[!UICONTROL Gestion de campagne]** > **[!UICONTROL Diffusions]** ou **[!UICONTROL Ressources]** > **[!UICONTROL Modèles]** > **[!UICONTROL Modèles de diffusion]**.
1. Sélectionnez la diffusion de votre choix ou dupliquez le modèle d&#39;usine **[!UICONTROL Diffusion email]**, puis sélectionnez le modèle dupliqué.
1. Cliquez sur le bouton **[!UICONTROL Propriétés]**.
1. Sélectionnez l&#39;onglet **[!UICONTROL Diffusion]**.
1. Cochez l&#39;option **[!UICONTROL Email Cci]**.

   ![](assets/email-bcc.png)

1. Sélectionner **[!UICONTROL Ok]**.

Une copie de tous les messages envoyés pour chaque diffusion basée sur ce modèle sera envoyée à l&#39;adresse email en Cci qui a été configurée.

Notez les spécificités et recommandations suivantes :

* Vous ne pouvez utiliser qu&#39;une seule adresse email en Cci.

* Assurez-vous que l&#39;adresse Cci dispose de suffisamment de capacité de réception pour archiver tous les emails envoyés.

* Email Cci <!--with Enhanced MTA--> envoie à l’adresse email en Cci avant la diffusion aux destinataires, ce qui peut entraîner l’envoi de messages en Cci même si les diffusions d’origine ont pu rebondir. Pour plus d’informations sur les rebonds, voir [Présentation des diffusions en échec](../send/delivery-failures.md).

* Si les emails envoyés à l&#39;adresse en Cci sont ouverts et font l&#39;objet de clics, cela sera pris en compte dans les **[!UICONTROL Ouvertures totales]** et les **[!UICONTROL Clics]** provenant de l&#39;analyse d&#39;envoi, ce qui pourrait entraîner des erreurs de calcul.

<!--Only successfully sent emails are taken in account, bounces are not.-->

**Apprenez-en davantage en consultant la documentation de Campaign Classic v7**

* [Générer la page miroir](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html?lang=fr#generating-mirror-page){target=&quot;_blank&quot;}

* [Sélectionner le format d’e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html?lang=fr#selecting-message-formats){target=&quot;_blank&quot;}

* [Sélectionner le codage des caractères ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html?lang=fr#character-encoding){target=&quot;_blank&quot;}

* [Définir l’adresse e-mail de rebond](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html?lang=fr#managing-bounce-emails){target=&quot;_blank&quot;}

* [Utiliser les modèles de diffusion par e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=fr){target=&quot;_blank&quot;}

* [Comprendre les échecs de diffusion](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html?lang=fr){target=&quot;_blank&quot;}
