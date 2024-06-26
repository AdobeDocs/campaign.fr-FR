---
title: Publier des messages sur X (Twitter) avec Adobe Campaign
description: Découvrez comment utiliser le module Social Marketing d’Adobe Campaign pour publier des messages sur X (anciennement Twitter) et envoyer des messages directs à vos abonnées et abonnés.
role: User
level: Beginner, Intermediate
exl-id: 0783e289-ae8e-4bb7-80f1-f90937a528c1
source-git-commit: f463c5747b844544ba561a63e4cb0359c0c258c8
workflow-type: ht
source-wordcount: '862'
ht-degree: 100%

---


# Publier des messages sur X (Twitter) avec Adobe Campaign {#post-tw-messages}

Adobe Campaign est fourni avec un module **Social Marketing** qui permet d’interagir avec la clientèle et des prospects via X (anciennement Twitter).

Une fois l’intégration configurée, vous pouvez :

* Envoyer des messages directs à vos abonnées et abonnés
* Publier sur votre compte X
* Collectez de nouveaux contacts en récupérant les données de profil. Vous pourrez alors exécuter des campagnes de ciblage et, lorsque cela est possible, mettre en œuvre des stratégies cross-canal. Cette action nécessite le consentement de l’utilisateur ou de l’utilisatrice.


Les étapes de configuration pour intégrer votre compte X à Adobe Campaign sont décrites sur [cette page](../connect/ac-tw.md).

## Créer et publier une publication X {#publish-on-tw}

Pour publier un message sur votre compte X, procédez comme suit :

1. Créer une diffusion X

   Créez une diffusion basée sur le modèle de diffusion **[!UICONTROL Tweeter (Twitter)]**.

   ![](assets/tw-new-delivery.png)

1. Sélection de la cible principale

   Vous devez sélectionner le ou les comptes auxquels vous souhaitez envoyer des publications.

   ![](assets/tw-define-target.png)

   1. Cliquez sur le lien **[!UICONTROL Pour]**.
   1. Cliquez sur le bouton **[!UICONTROL Ajouter]**.
   1. Sélectionnez **[!UICONTROL Un compte Twitter]**.
   1. Dans le champ **[!UICONTROL Dossier]**, sélectionnez le dossier de services contenant votre compte X. Sélectionnez ensuite le compte X auquel vous souhaitez envoyer votre publication.

1. Sélectionner la cible du BAT

   L’onglet **[!UICONTROL Cible des BAT]** vous permet de définir le compte X à utiliser pour les diffusions test avant la diffusion finale.

   Comme indiqué dans les [étapes de configuration](../connect/ac-tw.md#tw-test-account), vous devez créer un compte X de test privé dédié à l’envoi de BAT.

   >[!NOTE]
   >
   >Si vous utilisez le même compte de test X pour toutes vos diffusions, vous pouvez enregistrer la cible des BAT dans le modèle de diffusion **[!UICONTROL Poster]**, accessible à partir du nœud **[!UICONTROL Ressources > Modèles > Modèles de diffusion]**. La cible des BAT sera alors renseignée par défaut pour chaque nouvelle diffusion.

1. Définition du contenu de votre publication

   Saisissez le contenu de votre publication dans l&#39;onglet **[!UICONTROL Contenu]**.

   ![](assets/tw-delivery-content.png)

   >[!CAUTION]
   >
   >Lors de la publication sur X, des restrictions s’appliquent :
   >
   >* Le message ne peut pas dépasser 140 caractères.
   >* Le format HTML n&#39;est pas supporté.
   >

1. Prévisualisation de votre publication

   Accédez à l&#39;onglet **[!UICONTROL Aperçu]** pour vérifier le rendu de votre publication.

   ![](assets/tw-delivery-preview.png)

   1. Cliquez sur l&#39;onglet **[!UICONTROL Aperçu]**.
   1. Cliquez sur le menu déroulant **[!UICONTROL Tester la personnalisation]** et sélectionnez **[!UICONTROL Service]**.
   1. Dans le champ **[!UICONTROL Dossier]**, sélectionnez le dossier de services contenant votre compte X.

1. Envoyer un BAT

   Avant de publier votre publication, veillez à la valider en envoyant un BAT de votre publication : vous pouvez ensuite obtenir un rendu exact de la publication sur une page de test X privée.

1. Publication du message

   1. Une fois le contenu validé, cliquez sur le bouton **[!UICONTROL Envoyer]**.
   1. Choisissez **[!UICONTROL Diffuser dès que possible]** et cliquez sur le bouton **[!UICONTROL Analyser]**.
   1. Une fois l&#39;analyse terminée, vérifiez le résultat de l&#39;analyse.
   1. Cliquez sur le bouton **[!UICONTROL Confirmer l&#39;envoi]**, puis cliquez sur **[!UICONTROL Oui]**.

## Envoi de messages directs à des abonnés {#direct-tw-messages}

Le workflow technique **[!UICONTROL Synchronisation des comptes X]** récupère la liste des abonnées et abonnés X afin que vous puissiez leur envoyer des messages directs. [En savoir plus](../connect/ac-tw.md#synchro-tw-accounts)

Pour envoyer des messages directs à vos abonnés, procédez comme suit :

1. Créez une diffusion X basée sur le modèle de diffusion intégré **[!UICONTROL Poster (message direct)]**.

1. Sélection de la cible principale

   ![](assets/tw-dm-define-target.png)

   1. Sélectionnez le lien **[!UICONTROL À]** et le bouton **[!UICONTROL Ajouter]**.

   1. Choisir un type de ciblage

      * Sélectionnez **[!UICONTROL Abonnés d’un compte Twitter]** pour envoyer un message direct à tous vos abonnés.

      * Sélectionnez **[!UICONTROL Conditions des filtres]** pour définir une requête et afficher son résultat. Découvrez comment créer un filtre dans [cette section](../audiences/create-filters.md#advanced-filters).

1. Sélectionnez la cible du BAT dans l’onglet **[!UICONTROL Cible des BAT]** : ce compte recevra le BAT de votre message direct.

   Comme indiqué dans les [étapes de configuration](../connect/ac-tw.md#tw-test-account), vous devez créer un compte test X privé dédié à l’envoi de BAT.


   >[!NOTE]
   >
   >Si vous souhaitez envoyer tous les BAT de vos messages directs au même compte X, vous pouvez enregistrer la cible du BAT dans le modèle de diffusion **[!UICONTROL Poster (message direct)]**, accessible via le nœud **[!UICONTROL Ressources > Modèles > Modèles de diffusion]**.

1. Saisissez le contenu du message dans l&#39;onglet **[!UICONTROL Contenu]**.

   ![](assets/tw-dm-content.png)

   Comme pour une diffusion par e-mail, il est possible d&#39;utiliser les champs de personnalisation, par exemple si vous souhaitez ajouter le nom de l&#39;abonné dans le corps du message. En savoir plus dans [cette section](../send/personalize.md).

1. Prévisualisez votre message

   Accédez à l&#39;onglet **[!UICONTROL Aperçu]** pour vérifier le rendu de votre publication.

   ![](assets/tw-dm-preview.png)

   1. Cliquez sur l&#39;onglet **[!UICONTROL Aperçu]**.
   1. Cliquez sur le menu déroulant **[!UICONTROL Tester la personnalisation]** et sélectionnez **[!UICONTROL Abonnements des visiteurs]**.
   1. Sélectionnez le compte X sur lequel vous souhaitez tester l’aperçu.

1. Envoyer un BAT

   Avant d’envoyer votre message, veillez à le valider en [envoyant un BAT vers un compte test](../send/preview-and-proof.md) : vous pouvez ensuite obtenir un rendu exact du message sur un compte X privé et vérifier le contenu et la personnalisation.

1. Envoi du message direct

   1. Une fois le contenu validé, cliquez sur le bouton **[!UICONTROL Envoyer]**.
   1. Choisissez **[!UICONTROL Diffuser dès que possible]** et cliquez sur le bouton **[!UICONTROL Analyser]**.
   1. Une fois l&#39;analyse terminée, vérifiez le résultat de l&#39;analyse.
   1. Cliquez sur le bouton **[!UICONTROL Confirmer l&#39;envoi]**, puis cliquez sur **[!UICONTROL Oui]**.

>[!CAUTION]
>
>Vous ne pouvez pas envoyer plus de 250 messages directs par jour. Pour éviter de dépasser ce seuil, vous pouvez effectuer une diffusion par vagues. Pour en savoir plus à ce sujet, consultez la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=fr#sending-using-multiple-waves){target="_blank"}.


## Accès aux données de suivi {#tw-tracking}

Dans le modèle de diffusion **[!UICONTROL Tweet]**, le tracking est activé par défaut.

Les données de tracking sont visualisables dans les rapports de diffusion et dans l&#39;onglet **[!UICONTROL Modifier > Tracking]** de la diffusion et du service.

La configuration du tracking est le même que pour une diffusion e-mail. Apprenez-en davantage en consultant la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=fr){target="_blank"}.

