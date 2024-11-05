---
title: 'SMS : définir le contenu'
description: Découvrez comment configurer le contenu d’une diffusion SMS
feature: SMS
role: User
level: Beginner, Intermediate
exl-id: 71d9376c-86e8-41ec-92dc-863455d40c7a
source-git-commit: 70af3bceee67082d6a1bb098e60fd2899dc74600
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 100%

---

# Contenu SMS {#sms-content}

Pour configurer le contenu de votre diffusion SMS :

1. Saisissez le contenu du message dans l’assistant **[!UICONTROL Contenu texte]**.

   ![](assets/sms_content.png){zoomable="yes"}

1. Vous pouvez personnaliser votre message en insérant des champs de personnalisation (par exemple, en ajoutant le prénom) ou en insérant un bloc de personnalisation prédéfini (par exemple, en ajoutant les salutations). Vous pouvez cliquer sur le bouton de personnalisation pour ajouter ces éléments :

   ![](assets/sms_perso.png){zoomable="yes"}

   Après avoir cliqué sur **[!UICONTROL Destinataire]** > **[!UICONTROL Prénom]**, vous obtenez la personnalisation comme suit :

   ![](assets/sms_perso_recipient.png){zoomable="yes"}

1. Vous pouvez prévisualiser votre diffusion en accédant à l’onglet **[!UICONTROL Aperçu]** et en cliquant sur la liste déroulante **[!UICONTROL Tester la personnalisation]**, puis en choisissant une personne destinataire dans la table **[!UICONTROL Destinataire]**.

   ![](assets/sms_preview.png){zoomable="yes"}

   Vous disposez de l’aperçu de votre SMS avec la personnalisation :

   ![](assets/sms_preview_phone.png){zoomable="yes"}

>[!NOTE]
>
>* La longueur des messages SMS est limitée à 160 caractères si la page de code Latin-1 (ISO-8859-1) est utilisée. Si le message est rédigé en unicode, il ne peut dépasser 70 caractères. Certains caractères spéciaux peuvent avoir une influence sur la longueur du message. Pour plus d’informations sur la longueur des messages, voir la section [Translittération des caractères SMS](smpp-external-account.md#smpp-channel-settings).
>
>* Lors de la présence de champs de personnalisation ou de contenu conditionnel, la taille du message varie d’une personne destinataire à l’autre. La longueur du message doit être évaluée une fois la personnalisation effectuée.
>
>*Lorsque vous lancez l’analyse, la longueur des messages est contrôlée et un message d’avertissement est affiché en cas de dépassement.

Après avoir créé le contenu de votre diffusion, vous pouvez [sélectionner votre audience](sms-audience.md).
