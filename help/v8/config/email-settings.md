---
title: Paramètres du canal e-mail de Campaign
description: Paramètres du canal e-mail de Campaign
feature: Email
role: User
level: Intermediate, Experienced
exl-id: e4e3fb49-9942-4e2d-a020-557d1ac5dcdc
source-git-commit: edb099b3e882d857752af76798012ccd1c5a99be
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 95%

---

# Paramètres du canal e-mail de Campaign

## E-mail Cci {#email-bcc}

<!--
>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)-->

Vous pouvez paramétrer Adobe Campaign pour conserver une copie des e-mails envoyés depuis votre plateforme.

Adobe Campaign ne gère pas les fichiers archivés. Il vous permet d&#39;envoyer les messages de votre choix à une adresse e-mail Cci (copie carbone invisible) dédiée, à partir de laquelle ils peuvent être traités et archivés au moyen d&#39;un système externe. Les fichiers .eml correspondant aux e-mails envoyés peuvent ensuite être transférés vers un serveur distant, tel qu’un serveur de messagerie SMTP.

>[!CAUTION]
>
>Pour des raisons de confidentialité, les e-mails en Cci doivent être traités dans un système d’archivage capable de stocker en toute sécurité les informations d’identification personnelles (PII).

La destination d&#39;archivage est l&#39;adresse email en Cci de votre choix, qui restera invisible pour les destinataires de la diffusion.

![](../assets/do-not-localize/speech.png)  En tant qu’utilisateur Cloud Services géré, [contact Adobe](../start/campaign-faq.md#support){target="_blank"} communiquer l&#39;adresse email en Cci à utiliser pour l&#39;archivage.

Une fois l&#39;adresse e-mail en Cci définie, vous devez activer l&#39;option dédiée au niveau de la diffusion.

>[!CAUTION]
>
>Lors de la création d&#39;une diffusion ou d&#39;un modèle de diffusion, la fonctionnalité **[!UICONTROL Email Cci]** n&#39;est pas activée par défaut. Vous devez l’activer manuellement au niveau de la diffusion e-mail ou du modèle de diffusion.


Pour ce faire, procédez comme suit :

1. Accédez à **[!UICONTROL Gestion de campagne]** > **[!UICONTROL Diffusions]** ou **[!UICONTROL Ressources]** > **[!UICONTROL Modèles]** > **[!UICONTROL Modèles de diffusion]**.
1. Sélectionnez la diffusion de votre choix ou dupliquez le modèle d&#39;usine **[!UICONTROL Diffusion email]**, puis sélectionnez le modèle dupliqué.
1. Cliquez sur le bouton **[!UICONTROL Propriétés]**.
1. Sélectionnez l&#39;onglet **[!UICONTROL Diffusion]**.
1. Cochez l’option **[!UICONTROL Email Cci]**.

   ![](assets/email-bcc.png)

1. Cliquez sur **[!UICONTROL OK]**.

Une copie de tous les messages envoyés pour chaque diffusion basée sur ce modèle sera envoyée à l’adresse e-mail en Cci qui a été configurée.

Notez les spécificités et recommandations suivantes :

* Vous ne pouvez utiliser qu’une seule adresse email en Cci.

* Vérifiez que l’adresse en Cci dispose de suffisamment de capacité pour archiver tous les e-mails envoyés.

* L’option Email Cci <!--with Enhanced MTA--> assure la diffusion auprès de l’adresse e-mail en Cci avant la diffusion aux destinataires, ce qui peut entraîner l’envoi de messages en Cci même si les diffusions d’origine ont pu l’objet de retours. Pour plus d’informations sur les retours, voir [Présentation des diffusions en échec](../send/delivery-failures.md).

* Si les e-mails envoyés à l&#39;adresse en Cci sont ouverts et font l’objet de clics, cela sera pris en compte dans les **[!UICONTROL Ouvertures totales]** et les **[!UICONTROL Clics]** provenant de l’analyse d’envoi, ce qui pourrait entraîner des erreurs de calcul.

<!--Only successfully sent emails are taken in account, bounces are not.-->

**Apprenez-en davantage en consultant la documentation de Campaign Classic v7**

* [Sélectionner le format d&#39;e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html?lang=fr#selecting-message-formats){target="_blank"}

* [Sélectionner le codage des caractères](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html?lang=fr#character-encoding){target="_blank"}

* [Définir l&#39;adresse e-mail de rebond](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html?lang=fr#managing-bounce-emails){target="_blank"}

* [Utiliser des modèles de diffusion e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=fr){target="_blank"}

* [Présentation des diffusions en échec](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html?lang=fr){target="_blank"}
