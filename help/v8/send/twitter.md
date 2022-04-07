---
title: Messages de publication sur Twitter avec Adobe Campaign
description: Découvrez comment utiliser le module Social Marketing d’Adobe Campaign pour publier des messages sur Twitter et collecter des données de contact.
role: Data Engineer
level: Beginner
hide: true
hidefromtoc: true
exl-id: 0783e289-ae8e-4bb7-80f1-f90937a528c1
source-git-commit: 0f15112f0eec1d7cba26523adc1e88fc5d26997c
workflow-type: tm+mt
source-wordcount: '975'
ht-degree: 40%

---


# Messages de publication sur Twitter avec Adobe Campaign {#post-tw-messages}

Adobe Campaign est fourni avec une **Social Marketing** qui permet d&#39;interagir avec vos clients et prospects via Twitter.

Une fois l&#39;intégration configurée, vous pouvez :

* Envoyer des messages sur Twitter : Adobe Campaign vous permet de publier des messages directement sur votre compte twitter. Vous pouvez également envoyer des messages directs à tous les abonnés de vos comptes.
* Collecter les nouveaux contacts : Adobe Campaign peut récupérer automatiquement les données de profil, ce qui permet d&#39;effectuer des campagnes de ciblage et, si possible, de mettre en oeuvre des stratégies cross-canal. Cette action nécessite le consentement de l’utilisateur.

Les étapes de configuration pour intégrer votre compte Twitter à Adobe Campaign sont décrites dans la section [cette page](../connect/ac-tw.md).

## Création et publication d’une publication Twitter {#publish-on-tw}

Pour publier un message sur votre compte Twitter, procédez comme suit :

1. Créer une diffusion Twitter

   Créez une diffusion basée sur le modèle de diffusion **[!UICONTROL Tweeter (Twitter)]**.

1. Sélection de la cible principale

   Vous devez sélectionner le ou les comptes sur lesquels vous souhaitez envoyer votre tweet.

   1. Cliquez sur le lien **[!UICONTROL Pour]**.
   1. Cliquez sur le bouton **[!UICONTROL Ajouter]**.
   1. Sélectionnez **[!UICONTROL Un compte Twitter]**.
   1. Dans le champ **[!UICONTROL Dossier]**, sélectionnez le dossier de services contenant le compte Twitter. Sélectionnez ensuite le compte Twitter sur lequel vous souhaitez envoyer votre tweet.

1. Sélection de la cible du BAT

   Le **[!UICONTROL Cible des BAT]** vous permet de définir le compte Twitter à utiliser pour les diffusions test avant la diffusion finale.

   Comme indiqué dans la section [étapes de configuration](../connect/ac-tw.md#tw-test-account), vous devez créer un compte Twitter privé dédié à l&#39;envoi de BAT.

   >[!NOTE]
   >
   >Si vous utilisez le même compte Twitter de test pour toutes vos diffusions, vous pouvez enregistrer la cible du BAT dans le modèle de diffusion **[!UICONTROL Tweeter]**, accessible à partir du nœud **[!UICONTROL Ressources > Modèles > Modèles de diffusion]**. La cible du BAT sera alors renseignée par défaut pour chaque nouvelle diffusion.

1. Définition du contenu de votre publication

   Saisissez le contenu de votre publication dans le champ **[!UICONTROL Contenu]** .

   >[!CAUTION]
   >
   >Lors de la publication sur Twitter, les restrictions s’appliquent :
   >
   >* Le message ne peut pas dépasser 140 caractères.
   >* Le format de HTML n’est pas pris en charge.


1. Aperçu de votre publication

   Parcourez les **[!UICONTROL Aperçu]** pour vérifier le rendu de votre publication.

   1. Cliquez sur l&#39;onglet **[!UICONTROL Aperçu]**.
   1. Cliquez sur le menu déroulant **[!UICONTROL Tester la personnalisation]** et sélectionnez **[!UICONTROL Service]**.
   1. Dans le champ **[!UICONTROL Dossier]**, sélectionnez le dossier de services contenant votre compte Twitter.
   1. Sélectionnez le compte Twitter sur lequel vous souhaitez tester l&#39;aperçu.

1. Envoi d&#39;un BAT

   Avant de publier votre tweet, veillez à le valider en envoyant un bon à tirer de votre publication : vous pouvez ensuite obtenir un rendu exact de la publication sur une page de test Twitter privée.

   Pour en savoir plus sur la création d’un compte Twitter privé, reportez-vous à [cette section](../connect/ac-tw.md#tw-test-account).

   ![](../assets/do-not-localize/book.png) [Découvrez les étapes clés de validation d&#39;une diffusion](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=fr){target=&quot;_blank&quot;}

1. Publier le message

   1. Une fois le contenu validé, cliquez sur le bouton **[!UICONTROL Envoyer]**.
   1. Choisissez **[!UICONTROL Diffuser dès que possible]** et cliquez sur le bouton **[!UICONTROL Analyser]**.
   1. Une fois l&#39;analyse terminée, vérifiez le résultat de l&#39;analyse.
   1. Cliquez sur le bouton **[!UICONTROL Confirmer l&#39;envoi]**, puis cliquez sur **[!UICONTROL Oui]**.


## Envoyer des messages directs aux abonnés {#direct-tw-messages}

Le **[!UICONTROL Synchronisation des comptes Twitter]** workflow technique récupère la liste des abonnés Twitter afin que vous puissiez leur envoyer des messages directs. [En savoir plus](../connect/ac-tw.md#synchro-tw-accounts)

Pour envoyer des messages directs à vos abonnés, procédez comme suit :

1. Créez une diffusion Twitter basée sur la variable **[!UICONTROL Tweet (message direct)]** modèle de diffusion intégré.

1. Sélection de la cible principale

1. Sélectionnez la **[!UICONTROL À]** et la variable **[!UICONTROL Ajouter]** bouton .

1. Choisissez un type de ciblage

   * Sélectionner **[!UICONTROL Abonnés twitter]** pour envoyer un message direct à tous vos abonnés.

   * Sélectionner **[!UICONTROL Conditions de filtrage]** pour définir une requête et visualiser son résultat. Cette option est la même que pour les diffusions email. Apprenez-en davantage dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/creating-queries/defining-filter-conditions.html){target=&quot;_blank&quot;}.

1. Dans la **[!UICONTROL Cible des BAT]** sélectionnez l’abonné qui recevra le BAT de votre message direct.

   >[!NOTE]
   >
   >Si vous souhaitez envoyer tous les BAT de vos messages directs au même abonné Twitter, vous pouvez enregistrer la cible du BAT dans la variable **[!UICONTROL Tweet (message direct)]** modèle de diffusion, accessible à partir du **[!UICONTROL Ressources > Modèles > Modèles de diffusion]** noeud .

1. Saisissez le contenu du message dans le champ **[!UICONTROL Contenu]** .

   Les champs de personnalisation peuvent être utilisés de la même manière que pour les diffusions email, par exemple pour ajouter le nom de l&#39;abonné dans le corps du message. Apprenez-en davantage dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/about-personalization.html?lang=fr){target=&quot;_blank&quot;}.

1. Prévisualisez votre message

   Parcourez les **[!UICONTROL Aperçu]** pour vérifier le rendu de votre publication.

   1. Cliquez sur l&#39;onglet **[!UICONTROL Aperçu]**.
   1. Cliquez sur le menu déroulant **[!UICONTROL Tester la personnalisation]** et sélectionnez **[!UICONTROL Service]**.
   1. Dans le champ **[!UICONTROL Dossier]**, sélectionnez le dossier de services contenant votre compte Twitter.
   1. Sélectionnez le compte Twitter sur lequel vous souhaitez tester l&#39;aperçu.

1. Envoi d&#39;un BAT

   Avant d&#39;envoyer votre message, veillez à le valider en envoyant un BAT à un compte test : vous pouvez ensuite obtenir un rendu exact du message sur un compte Twitter privé et vérifier le contenu et la personnalisation.

   Pour en savoir plus sur la création d’un compte Twitter privé, reportez-vous à [cette section](../connect/ac-tw.md#tw-test-account).

   ![](../assets/do-not-localize/book.png) [Découvrez les étapes clés de validation d&#39;une diffusion](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html){target=&quot;_blank&quot;}

1. Envoyer le message direct

   1. Une fois le contenu validé, cliquez sur le bouton **[!UICONTROL Envoyer]**.
   1. Choisissez **[!UICONTROL Diffuser dès que possible]** et cliquez sur le bouton **[!UICONTROL Analyser]**.
   1. Une fois l&#39;analyse terminée, vérifiez le résultat de l&#39;analyse.
   1. Cliquez sur le bouton **[!UICONTROL Confirmer l&#39;envoi]**, puis cliquez sur **[!UICONTROL Oui]**.

>[!CAUTION]
>
>Vous ne pouvez pas envoyer plus de 250 messages directs par jour. Pour éviter de dépasser cette limite, vous pouvez effectuer une diffusion par vagues. Pour en savoir plus à ce sujet, consultez la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=fr#sending-using-multiple-waves){target=&quot;_blank&quot;}.


## Accès aux données de suivi {#tw-tracking}

Dans le **[!UICONTROL Tweet]** modèle de diffusion, le tracking est activé par défaut.

Les données de tracking peuvent être visualisées dans les rapports de diffusion et dans la variable **[!UICONTROL Edition > Tracking]** de la diffusion et du service.

Le paramétrage du tracking est le même que pour une diffusion email. Apprenez-en davantage dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=fr){target=&quot;_blank&quot;}.

