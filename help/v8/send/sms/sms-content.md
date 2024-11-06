---
title: Définir et personnaliser le contenu du SMS
description: Découvrez comment définir et personnaliser le contenu d'une diffusion SMS
feature: SMS
role: User
level: Beginner, Intermediate
exl-id: 71d9376c-86e8-41ec-92dc-863455d40c7a
source-git-commit: 0ef082b49261d0d2de5a6891a4a7f0cf5aafa221
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 60%

---

# Définition du contenu des SMS {#sms-content}

Pour configurer le contenu de votre diffusion SMS :

1. Saisissez le contenu de votre message dans l&#39;onglet **[!UICONTROL Contenu texte]** .

   ![](assets/sms_content.png){zoomable="yes"}

1. Vous pouvez personnaliser votre message en insérant des champs de personnalisation (par exemple, en ajoutant le prénom) ou en insérant un bloc de personnalisation prédéfini (par exemple, en ajoutant les salutations). Cliquez sur le bouton de personnalisation pour ajouter ces éléments :

   ![](assets/sms_perso.png){zoomable="yes"}

   Par exemple, après avoir cliqué sur **[!UICONTROL Destinataire]** > **[!UICONTROL Prénom]**, le contenu du SMS est mis à jour avec le champ de personnalisation, comme ci-dessous :

   ![](assets/sms_perso_recipient.png){zoomable="yes"}

   En savoir plus sur la personnalisation dans Adobe Campaign dans [cette section](../personalize.md).

1. Vous pouvez prévisualiser le contenu de la diffusion depuis l&#39;onglet **[!UICONTROL Aperçu]**. Pour vérifier vos paramètres de personnalisation, cliquez sur la liste déroulante **[!UICONTROL Tester la personnalisation]** et sélectionnez un destinataire.

   ![](assets/sms_preview.png){zoomable="yes"}

   Vous pouvez vérifier l&#39;aperçu de votre SMS avec la personnalisation :

   ![](assets/sms_preview_phone.png){zoomable="yes"}

>[!NOTE]
>
>* La longueur des messages SMS est limitée à 160 caractères si la page de code Latin-1 (ISO-8859-1) est utilisée. Si le message est rédigé en unicode, il ne peut dépasser 70 caractères. Certains caractères spéciaux peuvent avoir une influence sur la longueur du message. Pour plus d’informations sur la longueur des messages, voir la section [Translittération des caractères SMS](smpp-external-account.md#smpp-channel-settings).
>
>* Lors de la présence de champs de personnalisation ou de contenu conditionnel, la taille du message varie d’une personne destinataire à l’autre. La longueur du message doit être évaluée une fois la personnalisation effectuée.
>
>*Lorsque vous lancez l’analyse, la longueur des messages est contrôlée et un message d’avertissement est affiché en cas de dépassement.

Après avoir créé le contenu de votre diffusion, vous pouvez [sélectionner votre audience](sms-audience.md).
