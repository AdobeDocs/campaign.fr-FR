---
title: Envoyer et surveiller vos emails
description: Découvrez la portée et les spécificités de l'envoi d'emails avec Adobe Campaign
feature: Email
role: Data Engineer
level: Beginner
exl-id: f2c26351-8ed7-498a-ac83-d4c583fb98f3
source-git-commit: 9fa6666532a6943c438268d7ea832f0908588208
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 36%

---


# Envoyer et surveiller vos emails

Une fois la diffusion configurée et prête à être envoyée, vérifiez que vous avez exécuté l’analyse de la diffusion.

![](../assets/do-not-localize/book.png) [Apprenez-en davantage dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#confirming-delivery){target=&quot;_blank&quot;}

Une fois cette opération terminée, validez la diffusion pour lancer la diffusion des messages.

Vous pouvez également procéder comme suit :

* planifier la diffusion à une date ultérieure en utilisant [l&#39;option différer la diffusion](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#scheduling-the-delivery-sending){target=&quot;_blank&quot;},
* envoyer dans plusieurs lots à l’aide de [plusieurs vagues](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#sending-using-multiple-waves){target=&quot;_blank&quot;}.

Tracker l&#39;exécution de la diffusion depuis la **Diffusion** , accessible à partir du détail de cette diffusion ou à partir de la liste des diffusions.

## Surveillance de vos e-mails

Une fois les messages envoyés, vérifiez l&#39;état de votre diffusion dans le tableau de bord des diffusions et accédez aux logs de diffusion et aux rapports pour confirmer que vos messages ont été correctement envoyés.

![](../assets/do-not-localize/book.png) [Apprenez-en davantage en consultant la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html).{target=&quot;_blank&quot;}


## MTA de Campaign {#mta}

L’agent de transfert de messagerie (MTA) de Campaign v8 fournit une infrastructure d’envoi haut de gamme permettant une délivrabilité, une réputation, un débit, un reporting, une gestion des bounces, une montée d’adresses IP et une gestion des paramètres de connexion optimaux.

Disponible pour tous les clients de Campaign v8, il garantit une évolutivité, un débit de diffusion élevé et permet d&#39;envoyer plus d&#39;emails plus rapidement. Ces améliorations sont possibles grâce à de nouvelles techniques de diffusion adaptatives qui modifient en temps réel les paramètres d’envoi des emails en fonction des retours des fournisseurs d’accès à Internet.

### Avantages

Adobe Campaign utilise un MTA (Mail Transfer Agent) qui exécute le MTA de messagerie commercial de SparkPost appelé **Moment**.

Momentum offre une technologie MTA innovante et extrêmement performante. Elle comprend une gestion des retours plus intelligente et une fonctionnalité d&#39;optimisation de la délivrabilité automatisée qui aide les expéditeurs à atteindre et à maintenir des taux de remise optimaux aux boîtes de réception.

* Le MTA permet une augmentation massive de la vitesse de débit globale et une réduction significative des soft bounces.
* Il utilise la dernière technologie MTA pour vous fournir des vitesses de débit optimales pour votre diffusion email.
* En s&#39;adaptant instantanément et automatiquement aux retours qu&#39;il reçoit, il garantit également une diffusion par email plus précise et plus intelligente avec des données de diffusion en temps réel.

### Qualification des retours

Pour **synchrone** messages d’erreur d’échec de diffusion, le MTA détermine le type et la qualification de rebond et renvoie ces informations à Campaign.

Le MTA qualifie le bounce SMTP et renvoie cette qualification à Campaign sous la forme d&#39;un code rebond mappé à une raison et une qualification de bounce Campaign.

>[!NOTE]
>
>Actuellement **asynchrone** les bounces sont qualifiés par le processus inMail via le **[!UICONTROL Email entrant]** règles. Voir à ce sujet la section [Documentation de Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html#bounce-mail-qualification){target=&quot;_blank&quot;}. <!--Refer to [bounce mail qualification](delivery-failures.md#bounce-mail-qualification)-->

En savoir plus sur les diffusions en échec dans [cette section](delivery-failures.md).


### Règles MX spécifiques

Les règles MX (Mail eXchanger) correspondent aux règles de gestion de communication entre un serveur expéditeur et un serveur destinataire.

Le MTA possède ses propres règles MX qui lui permettent de personnaliser votre débit par domaine en fonction de votre réputation de courriel historique et des commentaires en temps réel provenant des domaines où vous envoyez des emails.

### Signature DKIM

Domain Keys Identified Mail (DKIM) est une méthode d&#39;authentification utilisée pour détecter les adresses d&#39;expéditeur falsifiées (usurpation de nom).

Dans Adobe Campaign, la signature de l&#39;authentification des emails DKIM est effectuée par le MTA.

En savoir plus sur DKIM dans la section [Guide des bonnes pratiques en matière de délivrabilité des Adobes](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=fr#authentication){target=&quot;_blank&quot;}.

## Service de retour d&#39;e-mail
 {#email-feedback-service}

Grâce à la fonctionnalité Email Feedback Service (EFS) , l’état de chaque email est rapporté de manière précise, car les commentaires sont capturés directement à partir du MTA.

Une fois la diffusion démarrée, aucune modification n’est apportée dans la variable **[!UICONTROL Succès]** pourcentage lorsque le message est relayé de Campaign au MTA.

Les logs de diffusion affichent le statut **[!UICONTROL Pris en compte par le prestataire]** pour chaque adresse ciblée.

Lorsque le message est effectivement diffusé aux profils ciblés et que ces informations sont reportées en temps réel à partir du MTA, les logs de diffusion affichent la variable **[!UICONTROL Envoyé]** pour chaque adresse qui a reçu le message avec succès. Le pourcentage **[!UICONTROL Succès]** augmente en conséquence lorsqu&#39;une diffusion est effectuée avec succès.

Lorsque des messages rebonds hard sont signalés à partir du MTA, leur état de journal passe de **[!UICONTROL Pris en compte par le prestataire]** to **[!UICONTROL En échec]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->.

Lorsque les messages de soft bounces sont signalés à partir du MTA, leur état de journal reste inchangé (**[!UICONTROL Pris en compte par le prestataire]**) : uniquement [raison de l’erreur](delivery-failures.md#delivery-failure-reasons) est mis à jour<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->. Le pourcentage **[!UICONTROL Succès]** reste inchangé. Les messages rebonds par soft sont ensuite relancés tout au long de la diffusion. [période de validité](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target=&quot;_blank&quot;} :

* Si une reprise est effectuée avec succès avant la fin de la période de validité, l’état du message passe à **[!UICONTROL Envoyé]** et le pourcentage **[!UICONTROL Succès]** augmente en conséquence.

* Sinon, l’état devient **[!UICONTROL Échec]**. Le <!--and **[!UICONTROL Bounces + errors]** -->pourcentage **[!UICONTROL Succès]** reste inchangé.

>[!NOTE]
>
>Pour plus d&#39;informations sur les hard et soft bounces, voir [cette section](delivery-failures.md#delivery-failure-reasons).
>
>Pour plus d&#39;informations sur les reprises après une diffusion temporairement en échec, voir [cette section](delivery-failures.md#retries).

Le tableau ci-dessous montre comment les KPI et les statuts des envois sont mis à jour à chaque étape du processus d’envoi avec la fonctionnalité EFS.

| Étape du processus d’envoi | Résumé des KPI | État des logs d&#39;envoi |
|--- |--- |--- |
| Le message est relayé de Campaign vers le MTA | Le pourcentage **[!UICONTROL Succès]** n’est pas affiché (démarre à 0 %) | Pris en compte par le prestataire |
| Les messages rebonds sont signalés à partir du MTA | Aucun changement du pourcentage **[!UICONTROL Succès]** | En échec |
| Les messages à rebonds de soft sont signalés à partir du MTA | Aucun changement du pourcentage **[!UICONTROL Succès]** | Pris en compte par le fournisseur de services |
| Les reprises des messages soft bounce sont effectuées avec succès | Le pourcentage **[!UICONTROL Succès]** augmente en conséquence | Envoyés |
| Échec des reprises des messages soft bounce | Aucun changement du pourcentage **[!UICONTROL Succès]** | En échec |
