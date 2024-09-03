---
title: SMS dans une instance autonome
description: Découvrez comment configurer une diffusion SMS dans une instance autonome
feature: SMS
role: User
hide: true
hidefromtoc: true
level: Beginner, Intermediate
badge: label="Disponibilité limitée" type="Informative"
source-git-commit: 6926d84576df1810b511ef1a9976593cb99585bb
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 8%

---


# SMS dans une instance autonome {#sms-standalone}

>[!IMPORTANT]
>
>Cette documentation concerne Adobe Campaign v8.7.2 et versions ultérieures.
>
>Pour les versions plus anciennes, consultez la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up).

Dans une instance autonome, l&#39;envoi d&#39;une diffusion SMS nécessite :

1. Un **compte externe** spécifiant un connecteur et le type de message, [en savoir plus ici](#external-account)

1. Un **modèle de diffusion** dans lequel ce compte externe est référencé, [en savoir plus ici](#sms-delivery-template)

## Créer un compte externe {#external-account}

>[!IMPORTANT]
>
>L’utilisation du même compte et du même mot de passe pour plusieurs comptes SMS externes peut entraîner des conflits et des chevauchements entre les comptes. En savoir plus sur la [page de dépannage des SMS](smpp-connection.md#sms-troubleshooting).

Voici les étapes de création de votre compte externe SMPP :

1. Dans **[!UICONTROL Administration]** > **[!UICONTROL Plateforme]** > **[!UICONTROL Comptes externes]**, cliquez sur l&#39;icône **[!UICONTROL Nouveau]**

   ![](assets/sms_extaccount.png){zoomable="yes"}

1. Configurez le **[!UICONTROL libellé]** et le **[!UICONTROL nom interne]** de votre compte externe. Définissez le type de compte sur **[!UICONTROL Routage]**, cochez la case **[!UICONTROL Activé]**, sélectionnez **[!UICONTROL Mobile (SMS)]** pour le canal et **[!UICONTROL Envoi en masse]** pour le mode de diffusion.

   ![](assets/sms_extaccount_new.png){zoomable="yes"}

1. Dans l&#39;onglet **[!UICONTROL Mobile]**, conservez **[!UICONTROL SMPP générique étendu]** dans la liste déroulante **[!UICONTROL Connector]**.
La case **[!UICONTROL Envoyer les messages par le biais d&#39;un processus dédié]** est cochée par défaut.

   ![](assets/sms_extaccount_connector.png){zoomable="yes"}

   Pour configurer la connexion, vous devez remplir les onglets de ce formulaire. Pour plus d&#39;informations, [en savoir plus sur le compte externe SMPP](smpp-external-account.md#smpp-connection-settings).


## Configuration du modèle de diffusion {#sms-delivery-template}

Pour faciliter la création de votre diffusion SMS, créez un modèle de diffusion SMS dans lequel votre compte externe SMPP est référencé.

Dans **[!UICONTROL Ressources]** > **[!UICONTROL Modèles]** > **[!UICONTROL Modèles de diffusion]**, cliquez avec le bouton droit sur le modèle de diffusion Mobile existant, puis sélectionnez **[!UICONTROL Dupliquer]**.

![](assets/sms_template_duplicate.png){zoomable="yes"}

Modifiez le **[!UICONTROL libellé]** et le **[!UICONTROL nom interne]** de votre modèle pour le reconnaître facilement, puis cliquez sur le bouton **[!UICONTROL Propriétés]** .

![](assets/sms_template_name.png){zoomable="yes"}

Dans l&#39;onglet **[!UICONTROL Général]**, dans **[!UICONTROL Routage]**, sélectionnez votre compte externe SMPP.

![](assets/sms_template_routing.png){zoomable="yes"}

Dans l&#39;onglet **[!UICONTROL SMS]**, vous pouvez ajouter des paramètres facultatifs à votre modèle.

![](assets/sms_template_properties.png){zoomable="yes"}

[En savoir plus sur cette configuration de l&#39;onglet SMS](sms-delivery-settings.md).
