---
title: Envoyer et surveiller vos e-mails
description: Découvrez la portée et les spécificités de l’envoi d’e-mails avec Adobe Campaign
feature: Email
role: Data Engineer
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: f2c26351-8ed7-498a-ac83-d4c583fb98f3
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '845'
ht-degree: 97%

---


# Envoyer et surveiller vos e-mails  {#send-and-monitor-emails}

Une fois la diffusion configurée et prête à être envoyée, vérifiez que vous avez exécuté l’analyse de la diffusion. [En savoir plus](delivery-analysis.md)

Une fois que vous avez terminé, confirmez la diffusion pour lancer la diffusion des messages.

Suivre l’exécution de la diffusion depuis l’onglet **Diffusion**, accessible à partir des détails de cette diffusion ou de la liste des diffusions.

## Surveiller vos e-mails {#email-monitoring}

Une fois les messages envoyés, vérifiez le statut de votre diffusion dans le **tableau de bord des diffusions** et accédez aux logs de diffusion et aux rapports pour confirmer que vos messages ont été correctement envoyés.

Depuis le tableau de bord des diffusions, vous pouvez vérifier les messages traités et consulter les logs d’audit de diffusion. Vous pouvez également contrôler le statut des messages dans les logs de diffusion.

>[!NOTE]
>
>Les statuts des diffusions ne s’affichent pas en temps réel. Découvrez le service de retour par e-mail dans [cette section](#email-feedback-service).


[En savoir plus sur la surveillance des diffusions dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html?lang=fr){target="_blank"}

## MTA de Campaign {#mta}

Le MTA (Mail Transfer Agent) de Campaign v8 fournit la meilleure infrastructure d’envoi de sa catégorie. Il offre des performances optimales en matière de délivrabilité, de réputation, de débit, de reporting, de gestion des rebonds, de préchauffage des adresses IP et de gestion des paramètres de connexion.

Disponible pour tous les clients de Campaign v8, le MTA garantit une évolutivité ainsi qu’un débit de diffusion élevé et permet d’envoyer plus d’e-mails plus rapidement. Ces améliorations sont possibles grâce à de nouvelles techniques de diffusion adaptatives qui modifient en temps réel les paramètres d’envoi des e-mails en fonction des retours des fournisseurs d’accès à Internet.

### Avantages

Adobe Campaign utilise un MTA (Mail Transfer Agent) qui exécute le MTA d’e-mail commercial de SparkPost appelé **Momentum**.

Momentum offre une technologie MTA innovante et extrêmement performante. Elle comprend une gestion des rebonds plus intelligente et une fonctionnalité d’optimisation de la délivrabilité automatisée qui aide les personnes expéditrices à atteindre et à maintenir des taux de remise optimaux aux boîtes de réception.

* Le MTA permet une augmentation considérable de la vitesse de débit globale et une réduction significative des rebonds temporaires.
* Il utilise la dernière technologie MTA pour vous offrir des vitesses de débit optimales pour votre diffusion par e-mail.
* En s&#39;adaptant instantanément et automatiquement aux retours qu&#39;il reçoit, il garantit également une diffusion par e-mail plus précise et plus intelligente avec des données de diffusion en temps réel.

### Qualification des rebonds

Pour les messages d’erreur d’échec de diffusion **synchrone**, le MTA détermine le type et la qualification du rebond et renvoie ces informations à Campaign.

Le MTA qualifie le rebond SMTP et envoie cette qualification à Campaign sous la forme d’un code de rebond mappé à un motif et à une qualification de rebond Campaign.

>[!NOTE]
>
>Actuellement, les rebonds **asynchrones** sont qualifiés par le processus inMail grâce aux règles d’**[!UICONTROL e-mail entrant]**.

En savoir plus sur les diffusions en échec dans [cette section](delivery-failures.md).


### Règles MX spécifiques

Les règles MX (Mail eXchanger) correspondent aux règles de gestion de communication entre un serveur expéditeur et un serveur destinataire.

Le MTA dispose de ses propres règles MX. Il peut ainsi personnaliser le débit par domaine en fonction de votre réputation, basée sur l’historique des e-mails et les commentaires en temps réel provenant des domaines auxquels vous adressez des e-mails.

### Signature DKIM

Domain Keys Identified Mail (DKIM) est une méthode d’authentification utilisée pour détecter les adresses d’expéditeur falsifiées (usurpation de nom).

Dans Adobe Campaign, la signature de l’authentification des e-mails DKIM est effectuée par le MTA.

En savoir plus sur DKIM dans le [Guide des bonnes pratiques en matière de délivrabilité d&#39;Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=fr#authentication){target="_blank"}.

## Service de commentaires par e-mail {#email-feedback-service}

Le service de retour par e-mail (EFS) de Campaign indique le statut de chaque diffusion par e-mail envoyée avec Adobe Campaign.

Une fois la diffusion lancée, le pourcentage **[!UICONTROL Succès]** n’est plus modifié lorsque le message est relayé avec succès de Campaign au MTA. Les logs de diffusion affichent le statut **[!UICONTROL Pris en compte par le fournisseur d&#39;accès d&#39;accès]** pour chaque adresse ciblée.

Lorsque le message est effectivement diffusé aux profils ciblés et que ces informations sont renvoyées en temps réel depuis le MTA, les logs de diffusion affichent le statut **[!UICONTROL Envoyés]** pour chaque adresse ayant reçu le message avec succès. Le pourcentage **[!UICONTROL Succès]** augmente en conséquence lorsqu&#39;une diffusion est effectuée avec succès.

Lorsque des messages hard bounce sont signalés depuis le MTA, leur statut de log passe de **[!UICONTROL Pris en compte par le fournisseur d&#39;accès d&#39;accès]** à **[!UICONTROL En échec]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->.

Lorsque des messages soft bounce sont signalés depuis le MTA, leur statut de log reste inchangé (**[!UICONTROL Pris en compte par le fournisseur d&#39;accès d&#39;accès]**) : seule le [motif de l’erreur](delivery-failures.md#delivery-failure-reasons) est mis à jour<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->. Le pourcentage **[!UICONTROL Succès]** reste inchangé. L&#39;envoi des messages soft bounce fait ensuite l&#39;objet de reprises tout au long de la [période de validité](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=fr#defining-validity-period){target="_blank"} de la diffusion :

* Si une reprise est effectuée avec succès avant la fin de la période de validité, l’état du message passe à **[!UICONTROL Envoyé]** et le pourcentage **[!UICONTROL Succès]** augmente en conséquence.

* Sinon, l’état devient **[!UICONTROL Échec]**. Le <!--and **[!UICONTROL Bounces + errors]** -->pourcentage **[!UICONTROL Succès]** reste inchangé.

>[!NOTE]
>
>Pour plus d’informations sur les rebonds temporaires et définitifs, voir [cette section](delivery-failures.md#delivery-failure-reasons).
>
>Pour plus d&#39;informations sur les reprises après une diffusion temporairement en échec, voir [cette section](delivery-failures.md#retries).

Le tableau ci-dessous montre comment les KPI et les statuts des logs d’envoi sont mis à jour à chaque étape du processus d’envoi.

| Étape du processus d’envoi | Résumé des KPI | État des logs d&#39;envoi |
|--- |--- |--- |
| Le message est relayé avec succès de Campaign vers le MTA. | Le pourcentage **[!UICONTROL Succès]** n’est pas affiché (démarre à 0 %) | Pris en compte par le prestataire |
| Les messages hard bounce sont renvoyés du MTA. | Aucun changement du pourcentage **[!UICONTROL Succès]** | En échec |
| Les messages soft bounce sont renvoyés depuis le MTA. | Aucun changement du pourcentage **[!UICONTROL Succès]** | Pris en compte par le prestataire |
| Les reprises des messages soft bounce sont effectuées avec succès | Le pourcentage **[!UICONTROL Succès]** augmente en conséquence | Envoyés |
| Échec des reprises des messages soft bounce | Aucun changement du pourcentage **[!UICONTROL Succès]** | En échec |
