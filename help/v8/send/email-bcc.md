---
title: Envoyer une copie de vos messages à une adresse en Cci
description: Découvrez comment activer la fonctionnalité Email Cci dans Adobe Campaign
feature: Email
role: User
level: Beginner
source-git-commit: 87c971ac6cf4abb6b04d52ce60ac2036055e1e02
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 36%

---


# Envoyer une copie de vos messages à une adresse en Cci {#bcc}

<!--
>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)-->

## A propos des emails en Cci {#gs-bcc}

Vous pouvez configurer Adobe Campaign pour conserver une copie des emails envoyés depuis votre plateforme. Cette option vous permet d&#39;envoyer des messages avec une adresse email dédiée en Cci (copie carbone aveugle), à partir de laquelle ils peuvent être traités et archivés à l&#39;aide d&#39;un système externe.
Adobe Campaign ne gère pas les fichiers archivés. Les fichiers .eml correspondant aux e-mails envoyés peuvent ensuite être transférés vers un serveur distant, tel qu’un serveur de messagerie SMTP.

La destination d&#39;archivage est l&#39;adresse email en Cci de votre choix, qui restera invisible pour les destinataires de la diffusion. Une fois l&#39;adresse email en Cci définie, vous devez activer l&#39;option dédiée au niveau de la [modèle de diffusion](create-templates.md) niveau.

![](../assets/do-not-localize/speech.png)En tant qu’utilisateur ou utilisatrice Managed Cloud Services, [contactez Adobe](../start/campaign-faq.md#support){target="_blank"} pour communiquer l’adresse e-mail en Cci à utiliser pour l’archivage.

>[!CAUTION]
>
>Pour des raisons de confidentialité, les e-mails en Cci doivent être traités dans un système d’archivage capable de stocker en toute sécurité les informations d’identification personnelles (PII).


## Activer Email Cci {#enable-bcc}

Pour activer la Cci pour un [modèle de diffusion](create-templates.md), procédez comme suit :

1. Depuis l&#39;explorateur Campaign, accédez au dossier des modèles de diffusion. Par défaut, les modèles de diffusion sont stockés dans la variable **[!UICONTROL Ressources]** > **[!UICONTROL Modèles]** > **[!UICONTROL Modèles de diffusion]** dossier.
1. Editez le modèle de diffusion à mettre à jour en Cci.
1. Cliquez sur le bouton **[!UICONTROL Propriétés]**.
1. Dans la **[!UICONTROL Diffusion]** , vérifiez les **[!UICONTROL Email Cci]** .

   ![](assets/email-bcc.png)

1. Cliquez sur **[!UICONTROL Ok]** pour confirmer.

Une copie de tous les messages envoyés pour chaque diffusion basée sur ce modèle sera envoyée à l&#39;adresse email en Cci qui a été configurée pour votre plateforme.

## Mécanisme de sécurisation et recommandations {#recommendations-bcc}

Lors de l’utilisation de la fonctionnalité Email Cci avec Adobe Campaign, les barrières de sécurité et recommandations suivantes s’appliquent :

* Vous ne pouvez utiliser qu’une seule adresse e-mail en Cci.

* Vérifiez que l’adresse en Cci dispose de suffisamment de capacité pour archiver tous les e-mails envoyés.

* L’option E-mail Cci <!--with Enhanced MTA--> assure la diffusion auprès de l’adresse e-mail en Cci avant la diffusion aux destinataires, ce qui peut entraîner l’envoi de messages en Cci même si les diffusions d’origine ont pu faire l’objet de rebonds. Pour plus d’informations sur les rebonds, voir [Présentation des diffusions en échec](delivery-failures.md).

* Les emails envoyés à l&#39;adresse en Cci ne doivent pas être ouverts ni faire l&#39;objet de clics, car ces activités sont prises en compte dans la variable **[!UICONTROL Ouvertures totales]** et **[!UICONTROL Clics]** de l’analyse d’envoi, peut entraîner des erreurs de calcul.

<!--Only successfully sent emails are taken in account, bounces are not.-->
