---
title: SMS Envoyer des bons à tirer
description: Découvrez comment envoyer des BAT d'une diffusion SMS
feature: SMS
role: User
level: Beginner, Intermediate
source-git-commit: 24a6d56a79995cd0113d8438d1bd3314a3872e35
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 8%

---


# Envoyer un BAT d&#39;une diffusion SMS {#sms-proof}

Adobe recommande vivement de configurer un cycle de validation de diffusion. Assurez-vous que votre contenu est validé avant de l&#39;envoyer à votre audience.

Vous pouvez envoyer un BAT pour votre diffusion SMS afin de la valider :

1. Cliquez sur le bouton **[!UICONTROL Envoyer un BAT]** , une fenêtre s’ouvre.

   ![](assets/proof_targeting.png){zoomable="yes"}

   Vous avez plusieurs modes pour envoyer un BAT :

   * **[!UICONTROL Définition d&#39;une cible spécifique au BAT]** : permet d&#39;interroger avec des filtres les adresses de la base en tant que cible du BAT.
   * **[!UICONTROL Substitution de l&#39;adresse]** : permet de saisir les adresses de test et d&#39;utiliser les données du destinataire cible pour valider le contenu. Les adresses de substitution peuvent être saisies manuellement ou sélectionnées dans la liste déroulante. L&#39;énumération associée est **[!UICONTROL Adresse de substitution (rcpAddress)]**.
Par défaut, la substitution est effectuée de manière aléatoire, mais vous pouvez sélectionner un destinataire spécifique dans la cible principale, via l&#39;icône **[!UICONTROL Détail]** .
   * **[!UICONTROL Adresses de contrôle]** : vous permet d’accéder aux adresses de contrôle pour en faire la cible des BAT. Ces adresses peuvent être importées à partir d’un fichier ou saisies manuellement.
   * **[!UICONTROL Cible spécifique et Adresses de contrôle]** : permet de combiner des adresses de contrôle et des adresses de destinataires.

1. Après avoir choisi le **[!UICONTROL mode de ciblage]**, ajoutez vos adresses de BAT en fonction de celles-ci.

   Dans l&#39;exemple ci-dessous, nous choisissons **[!UICONTROL Définition d&#39;une cible spécifique au BAT]** et ajoutons un destinataire :

   ![](assets/proof_recipient.png){zoomable="yes"}

1. Cliquez sur le bouton **[!UICONTROL Analyser]** .
Adobe Campaign effectuera tout le contrôle avant de valider l&#39;envoi du BAT. À la fin de l’analyse, le bouton **[!UICONTROL Confirmer la diffusion]** sera cliquable.

   ![](assets/proof_analyze.png){zoomable="yes"}

1. Pour envoyer le BAT de votre diffusion SMS, cliquez sur le bouton **[!UICONTROL Confirmer la diffusion]** .

Si tout va bien à ce stade, vous pouvez avancer et [envoyer votre diffusion SMS à l&#39;audience](sms-audience.md).
