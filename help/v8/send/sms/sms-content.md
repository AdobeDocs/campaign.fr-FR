---
title: Définir et personnaliser le contenu des SMS
description: Découvrez comment définir et personnaliser le contenu d’une diffusion SMS.
feature: SMS
role: User
level: Beginner, Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: 71d9376c-86e8-41ec-92dc-863455d40c7a
TQID: https://experienceleague.adobe.com/N4C8Rkg-Kl-82FCZAvJ12KofuRObW170ySJaCHgW5wM
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 262
ht-degree: 70%

---

# Définition du contenu du SMS {#sms-content}

Pour configurer le contenu de votre diffusion SMS :

1. Saisissez le contenu du message dans l’onglet **[!UICONTROL Contenu texte]**.

   ![](assets/sms_content.png){zoomable="yes"}

1. Vous pouvez personnaliser votre message en insérant des champs de personnalisation (par exemple, en ajoutant le prénom) ou en insérant un bloc de personnalisation prédéfini (par exemple, en ajoutant les salutations). Cliquez sur le bouton de personnalisation pour ajouter ces éléments :

   ![](assets/sms_perso.png){zoomable="yes"}

   Par exemple, après avoir cliqué sur **[!UICONTROL Destinataire]** > **[!UICONTROL Prénom]**, le contenu du SMS est mis à jour avec le champ de personnalisation, comme ci-dessous :

   ![](assets/sms_perso_recipient.png){zoomable="yes"}

   En savoir plus sur la personnalisation dans Adobe Campaign dans [cette section](../personalize.md).

1. Vous pouvez prévisualiser le contenu de la diffusion dans l&#39;onglet **[!UICONTROL Aperçu]**. Pour vérifier vos paramètres de personnalisation, cliquez sur la liste déroulante **[!UICONTROL Tester la personnalisation]** et sélectionnez une personne destinataire.

   ![](assets/sms_preview.png){zoomable="yes"}

   Vous pouvez vérifier la prévisualisation de votre SMS avec la personnalisation :

   ![](assets/sms_preview_phone.png){zoomable="yes"}

>[!NOTE]
>
>* Les SMS sont limités à une longueur de 160 caractères si la page de code Latin-1 (ISO-8859-1) est utilisée. Si le message est écrit en Unicode, il ne doit pas dépasser 70 caractères. Certains caractères spéciaux peuvent affecter la longueur du message. Pour plus d’informations sur la longueur des messages, voir la section [Translittération des caractères SMS](smpp-external-account.md#smpp-channel-settings).
>
>* En présence de champs de personnalisation ou de contenu conditionnel, la taille du message varie d&#39;un destinataire à l&#39;autre. La longueur du message doit être évaluée une fois la personnalisation effectuée.
>
>*Lorsque vous lancez l’analyse, la longueur des messages est contrôlée et un message d’avertissement est affiché en cas de dépassement.

Après avoir créé le contenu de votre diffusion, vous pouvez [sélectionner votre audience](sms-audience.md).
