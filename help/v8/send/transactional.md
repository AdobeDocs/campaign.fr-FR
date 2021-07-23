---
product: Adobe Campaign
title: Messagerie transactionnelle de Campaign
description: Prise en main de la messagerie transactionnelle
feature: Vue d'ensemble
role: Data Engineer
level: Beginner
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: ht
source-wordcount: '1550'
ht-degree: 100%

---

# Prise en main de la messagerie transactionnelle{#send-transactional-messages}

Les messages transactionnels (Message Center) sont un module de gestion des messages de déclenchement de Campaign. Ces messages (factures, confirmation de commande ou d&#39;expédition, changement de mot de passe, notification d&#39;indisponibilité d&#39;un produit, relevé de compte ou création d&#39;un compte sur un site web par exemple) sont générés à partir des événements déclenchés depuis des systèmes d&#39;information.

?? En tant qu&#39;utilisateur Managed Cloud Services, [contactez Adobe](../start/campaign-faq.md#support) pour installer et configurer la messagerie transactionnelle de Campaign dans votre environnement.

Les messages transactionnels sont utilisés pour envoyer :

* des notifications, telles que les confirmations de commande ou les réinitialisations de mot de passe, par exemple ;
* une réponse individuelle en temps réel à une action client ;
* du contenu non promotionnel.

?? Les paramètres de messagerie transactionnelle sont décrits dans [cette section](../config/transactional-msg-settings.md).

?? Découvrez l&#39;architecture de la messagerie transactionnelle sur [cette page](../dev/architecture.md).

>[!CAUTION]
>
>Les messages transactionnels nécessitent une licence spécifique. Veuillez vérifier votre accord de licence.

## Définition de modèles de messages transactionnels

Chaque événement peut déclencher un message personnalisé. Pour ce faire, vous devez créer un modèle de message correspondant à chaque type d&#39;événement. Les modèles contiennent les informations nécessaires à la personnalisation du message transactionnel. Vous pouvez également utiliser des modèles pour tester la prévisualisation des messages et envoyer des BAT à l&#39;aide d&#39;adresses de contrôle avant de les diffuser à la cible finale.

### Création du modèle

Pour créer un modèle de message, procédez comme suit :

1. Positionnez-vous au niveau du dossier **[!UICONTROL Message Center > Modèles de messages transactionnels]** dans l&#39;arborescence Adobe Campaign.
1. Dans la liste des modèles de messages transactionnels, cliquez avec le bouton droit de la souris et sélectionnez **[!UICONTROL Nouveau]** dans le menu contextuel ou cliquez sur le bouton **[!UICONTROL Nouveau]** situé au-dessus de la liste des modèles de messages transactionnels.

   ![](assets/messagecenter_create_model_001.png)

1. Dans la fenêtre de diffusion, sélectionnez le modèle de diffusion propre au canal que vous souhaitez utiliser.

   ![](assets/messagecenter_create_model_002.png)

1. Modifiez le libellé si nécessaire.
1. Sélectionnez le type d&#39;événement correspondant au message que vous souhaitez envoyer.

   ![](assets/messagecenter_create_model_003.png)

   Les types d&#39;événement destinés à être traités par Adobe Campaign doivent être créés sur l&#39;instance de pilotage par Adobe.

   >[!NOTE]
   >
   >Un type d&#39;événement ne doit jamais être lié à plusieurs modèles.

1. Renseignez la nature et la description selon vos besoins, puis cliquez sur **[!UICONTROL Continuer]** pour créer le corps du message. Voir [Création du contenu du message](#create-message-content).

### Création du contenu{#create-message-content}

La définition du contenu du message transactionnel est la même que pour toutes les diffusions dans Adobe Campaign. Par exemple, pour une diffusion e-mail, vous pouvez créer du contenu au format HTML ou texte, ajouter des pièces jointes ou personnaliser l&#39;objet de diffusion. Pour plus d&#39;informations à ce sujet, consultez [cette section](../start/create-message.md).

>[!CAUTION]
>
>Les images incluses dans le message doivent être accessibles publiquement. Adobe Campaign ne fournit pas de mécanisme de mise en ligne des images pour les messages transactionnels.\
>Contrairement à JSSP ou webApp, `<%=` n&#39;a pas de séquence d&#39;échappement par défaut.
>
>Vous devez appliquer une séquence d&#39;échappement correcte à toutes les données provenant de l&#39;événement. Cette séquence d&#39;échappement dépend de l&#39;utilisation de ce champ. Par exemple, dans une URL, utilisez encodeURIComponent. Pour un affichage dans le code HTML, vous pouvez utiliser escapeXMLString.

Lorsque vous avez défini le contenu de votre message, vous pouvez intégrer les informations de l&#39;événement dans le corps du message et ainsi le personnaliser. Les informations de l&#39;événement sont insérées dans le corps du texte à l&#39;aide des balises de personnalisation.

![](assets/messagecenter_create_content.png)

* Tous les champs de personnalisation proviennent de la payload.
* Il est possible de référencer un ou plusieurs blocs de personnalisation dans un message transactionnel. Le contenu du bloc est ajouté au contenu de la diffusion au cours de la publication dans l&#39;instance d&#39;exécution.

Pour insérer des balises de personnalisation dans le corps d&#39;un message e-mail, procédez comme suit :

1. Dans le modèle de message, cliquez sur l&#39;onglet correspondant au format de l&#39;e-mail (HTML ou texte).
1. Rédigez le corps du message.
1. Dans le corps du texte, insérez la balise à l&#39;aide des menus **[!UICONTROL Evénement temps réel>XML de l&#39;événement]**.

   ![](assets/messagecenter_create_custo_1.png)

1. Complétez la balise selon la syntaxe suivante : .**nom de l&#39;élément**.@**nom de l&#39;attribut** comme illustré ci-dessous.

   ![](assets/messagecenter_create_custo_2.png)

### Ajouter des adresses de contrôle{#add-seeds}

Une adresse de contrôle vous permet d&#39;afficher une prévisualisation de votre message, d&#39;envoyer un BAT et de tester la personnalisation du message avant l&#39;envoi. Les adresses de contrôle sont liées à la diffusion et ne peuvent pas être utilisées pour d&#39;autres diffusions.

1. Dans le modèle de message transactionnel, cliquez sur l&#39;onglet **[!UICONTROL Adresses de contrôle]**, puis sur le bouton **[!UICONTROL Ajouter]**.

   ![](assets/messagecenter_create_seed_1.png)

1. Attribuez-lui un libellé afin de faciliter la sélection ultérieurement, puis saisissez l&#39;adresse de contrôle (e-mail ou téléphone portable selon le canal de communication).

1. Renseignez l&#39;identifiant externe : ce champ optionnel vous permet de renseigner la clé métier (identifiant unique, nom + e-mail, etc.), commune à toutes les applications de votre site web, que vous utilisez pour identifier vos profils. Si ce champ est aussi présent dans la base marketing Adobe Campaign, vous pourrez alors réconcilier un événement avec un profil en base.

   ![](assets/messagecenter_create_seed_2.png)

1. Insérez les données de test. Consultez [cette section](#personalization-data).

   ![](assets/messagecenter_create_custo_3.png)

1. Cliquez sur **[!UICONTROL OK]** pour valider la création de l&#39;adresse de contrôle.

1. Répétez l&#39;opération pour créer le nombre d&#39;adresses voulu.

   ![](assets/messagecenter_create_seed_6.png)

Une fois les adresses créées, vous pouvez accéder à la prévisualisation et à la personnalisation.

### Ajout de données de personnalisation{#personalization-data}

Vous pouvez ajouter des données dans le modèle de message afin de tester la personnalisation du message transactionnel. Vous pouvez ainsi générer une prévisualisation ou envoyer un BAT. Si vous installez le module **Délivrabilité**, ces données vous permettent d&#39;afficher un rendu des messages pour divers clients de bureau, web ou mobiles.

Ces données n&#39;ont pour but que de tester vos messages avant leur diffusion effective et ne correspondent pas aux données réelles qui seront traitées par Message Center. En revanche, la structure XML doit être identique à celle de l&#39;événement qui est stocké dans l&#39;instance d&#39;exécution, comme illustré ci-dessous.

![](assets/messagecenter_create_custo_4.png)

Ces informations vous permettent de personnaliser le contenu des messages à l&#39;aide de balises de personnalisation.

1. Dans le modèle de message, cliquez sur l&#39;onglet **[!UICONTROL Adresses de contrôle]**.
1. Dans le contenu de l&#39;événement, entrez les informations de test au format XML.

   ![](assets/messagecenter_create_custo_3.png)

### Prévisualisation de vos messages transactionnels{#transactional-message-preview}

Lorsque vous avez créé une ou plusieurs adresses de contrôle, ainsi que le corps du message, vous pouvez afficher l&#39;aperçu de votre message et vérifier la personnalisation de ce dernier.

1. Dans le modèle de message, cliquez sur l&#39;onglet **[!UICONTROL Aperçu]**, puis sélectionnez **[!UICONTROL Une adresse de contrôle]** dans la liste déroulante.

   ![](assets/messagecenter_preview_1.png)

1. Sélectionnez l&#39;adresse de contrôle préalablement créée afin d&#39;afficher le message personnalisé.

   ![](assets/messagecenter_create_seed_7.png)

### Envoi d&#39;un BAT

Vous pouvez tester la diffusion du message en envoyant un BAT vers une adresse de contrôle créée précédemment.

L&#39;envoi d&#39;un BAT engage le même processus que pour toute diffusion.

↗️ En savoir plus sur les bons à tirer dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=fr){target=&quot;_blank&quot;}

Toutefois, pour envoyer un BAT de message transactionnel, il vous faut exécuter les opérations suivantes :

* Création d&#39;une ou plusieurs [adresses de contrôle](#add-seeds) avec des données de test de personnalisation
* Création du contenu du message

Pour effectuer l&#39;envoi :

1. Cliquez sur bouton **[!UICONTROL Envoyer un BAT]** dans la fenêtre de diffusion.
1. Analysez la diffusion.
1. Corrigez les erreurs et validez la diffusion.

   ![](assets/messagecenter_send_proof_001.png)

1. Vérifiez que le message est bien parvenu à l&#39;adresse de contrôle et que son contenu est conforme à ce que vous aviez paramétré.

   ![](assets/messagecenter_send_proof_002.png)

Les BAT sont accessibles au niveau de chaque modèle, depuis l&#39;onglet **[!UICONTROL Suivi]**.

![](assets/messagecenter_send_proof_003.png)

### Publication du modèle

Lorsque le modèle de message créé sur l&#39;instance de pilotage est terminé, vous pouvez le publier. Ce processus le publiera également sur toutes les instances d&#39;exécution.

>[!NOTE]
>
>Lors de la publication de modèles de messages transactionnels, les règles de typologie sont également automatiquement publiées sur les instances d&#39;exécution.

La publication vous permet de créer automatiquement deux modèles de messages sur les instances d&#39;exécution. Vous pouvez ainsi envoyer des messages liés à des événements temps réel et par lots.

>[!CAUTION]
>
>Chaque fois que vous apportez des modifications à un modèle, veillez à le republier pour que ces modifications soient effectives pendant la diffusion du message transactionnel.

1. Dans l&#39;instance de pilotage, positionnez-vous au niveau du dossier **[!UICONTROL Message Center > Modèle de messages transactionnels]** dans l&#39;arborescence.
1. Sélectionnez le modèle que vous souhaitez publier sur vos instances d&#39;exécution.
1. Cliquez sur **[!UICONTROL Publier]**.

   ![](assets/messagecenter_publish_template.png)

Lorsque la publication est terminée, les deux modèles de messages destinés à être appliqués aux types d&#39;événements temps réel et par lots sont créés dans l&#39;arborescence de l&#39;instance d&#39;exploitation dans le dossier **[!UICONTROL Administration > Production > Message Center (Exécution) > Défaut > Modèles de messages transactionnels]**.

![](assets/messagecenter_deployed_model.png)

Une fois qu&#39;un modèle est publié, si l&#39;événement correspondant est déclenché, l&#39;instance d&#39;exécution reçoit l&#39;événement, le lie au modèle transactionnel et envoie le message transactionnel correspondant à chaque destinataire.

>[!NOTE]
>
>Si vous remplacez un champ existant du modèle de message transactionnel, tel que l&#39;adresse de l&#39;expéditeur, par une valeur vide, le champ correspondant sur l&#39;instance ou les instances d&#39;exécution ne sera pas mis à jour une fois le message transactionnel republié. Il contiendra toujours la valeur précédente.
>
>Cependant, si vous ajoutez une valeur non vide, le champ correspondant sera mis à jour comme d&#39;habitude après la publication suivante.


### Dépublication d&#39;un modèle

Lorsqu&#39;un modèle de message a été publié sur les instances d&#39;exécution, il est possible de le dépublier.

* En effet, un modèle publié peut toujours être appelé si l&#39;événement correspondant est déclenché : si vous n&#39;utilisez plus de modèle de message, il est recommandé de le dépublier. Vous éviterez ainsi d&#39;envoyer par erreur un message transactionnel indésirable.

   Par exemple, vous avez publié un modèle de message utilisé uniquement pour les campagnes de Noël. Vous pouvez le dépublier une fois la période de Noël terminée et le publier de nouveau l&#39;année suivante.

* En outre, vous ne pouvez pas supprimer un modèle de message transactionnel dont le statut est **[!UICONTROL Publié]**. Vous devez d&#39;abord le dépublier.

Pour dépublier un modèle de message transactionnel, procédez comme décrit ci-dessous.

1. Dans l&#39;instance de pilotage, accédez au dossier **[!UICONTROL Message Center > Modèles de messages transactionnels]**.
1. Sélectionnez le modèle dont vous souhaitez annuler la publication.
1. Cliquez sur **[!UICONTROL Dépublier]**.
1. Cliquez sur **[!UICONTROL Démarrer]**.

![](assets/message-center-unpublish.png)

Le statut du modèle de message transactionnel passe de **[!UICONTROL Publié]** à **[!UICONTROL En édition]**.

Une fois la publication annulée :

* Les deux modèles de message (appliqués aux types d&#39;événements par lot et temps réel) sont supprimés de chaque instance d&#39;exécution.

   Ils n&#39;apparaissent plus dans le dossier **[!UICONTROL Administration > Production > Exécution Message Center > Défaut > Modèles de messages transactionnels]**.

* Une fois la dépublication d&#39;un modèle effectuée, vous pouvez le supprimer de l&#39;instance de pilotage.

   Pour ce faire, sélectionnez-le dans la liste et cliquez sur le bouton **[!UICONTROL Supprimer]** en haut à droite de l&#39;écran.
