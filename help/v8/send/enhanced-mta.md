---
title: À propos du MTA amélioré dans Adobe Campaign
description: Découvrez la portée et les spécificités de lʼenvoi dʼe-mails avec le MTA amélioré dʼAdobe Campaign
feature: Email
role: Data Engineer
level: Beginner
exl-id: f2c26351-8ed7-498a-ac83-d4c583fb98f3
source-git-commit: 0fa0db62f45097755bebcbf434614c4c835d886a
workflow-type: tm+mt
source-wordcount: '1011'
ht-degree: 68%

---

# À propos du MTA amélioré {#sending-with-enhanced-mta}

Le **MTA amélioré d’Adobe Campaign** (Mail Transfer Agent) fournit une infrastructure d’envoi mise à niveau permettant une délivrabilité, une réputation, un débit, un reporting, une gestion des bounces, une montée d’adresses IP et une gestion des paramètres de connexion optimaux.

Il est mis en oeuvre pour tous les clients de Campaign v8 afin d’améliorer l’évolutivité, d’augmenter le débit de diffusion et d’accélérer l’envoi d’emails. Ces améliorations sont possibles grâce à de nouvelles techniques de diffusion adaptatives qui modifient en temps réel les paramètres d’envoi des emails en fonction des retours des fournisseurs d’accès à Internet.

## Utilisation et avantages

**Qu’est-ce que le MTA amélioré ?**

Adobe Campaign utilise un MTA (Mail Transfer Agent) qui exécute le MTA de messagerie commercial de SparkPost appelé **Moment**.

Momentum offre une technologie MTA innovante et extrêmement performante. Elle comprend une gestion des retours plus intelligente et une fonctionnalité d&#39;optimisation de la délivrabilité automatisée qui aide les expéditeurs à atteindre et à maintenir des taux de remise optimaux aux boîtes de réception.

**Quels sont les avantages ?**

* Le MTA amélioré permet une augmentation massive de la vitesse de débit globale et une réduction significative des soft bounces.
* Il utilise la dernière technologie MTA pour vous fournir des vitesses de débit optimales pour votre diffusion email.
* En s&#39;adaptant instantanément et automatiquement aux retours qu&#39;il reçoit, il garantit également une diffusion par email plus précise et plus intelligente avec des données de diffusion en temps réel.

## Spécificités du MTA amélioré {#enhanced-mta-impacts}

### Qualification des retours

Pour **synchrone** messages d’erreur d’échec de diffusion, le MTA amélioré détermine le type et la qualification de bounce et renvoie ces informations à Campaign.

Le MTA amélioré qualifie le retour SMTP et envoie cette qualification à Campaign sous la forme d’un code de retour mappé à un motif et à une qualification de retour Campaign.

>[!NOTE]
>
>Actuellement **asynchrone** les bounces ne sont pas qualifiés par le MTA amélioré, mais par le processus inMail via la fonction **[!UICONTROL Email entrant]** règles. Voir à ce sujet la section [Documentation de Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html#bounce-mail-qualification){target=&quot;_blank&quot;}. <!--Refer to [bounce mail qualification](delivery-failures.md#bounce-mail-qualification)-->

En savoir plus sur les diffusions en échec dans [cette section](delivery-failures.md).

### Période de validité

Le paramètre de la période de validité dans vos diffusions Campaign ne sera utilisé par le MTA amélioré que s’il est défini sur **3,5 jours ou moins**. Si vous définissez une valeur supérieure à 3,5 jours dans Campaign, elle ne sera pas prise en compte.

Par exemple, si la période de validité est définie sur la valeur par défaut de 5 jours dans Campaign, les messages soft bounce seront placés dans la file d’attente de reprise du MTA amélioré et ne feront l’objet d’une reprise que pendant 3,5 jours à compter du moment où ils ont atteint le MTA amélioré. Dans ce cas, la valeur définie dans Campaign ne sera pas utilisée.

Une fois qu’un message figure dans la file d’attente du MTA amélioré depuis 3,5 jours et qu’il n’a pas été diffusé, il expire et son état est mis à jour de **[!UICONTROL Envoi]** à **[!UICONTROL Échec]** dans les logs de diffusion.

Pour plus d’informations sur la période de validité, voir la section [Documentation de Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target=&quot;_blank&quot;}.

### Reprises

Les reprises des erreurs soft et l&#39;intervalle qui les sépare sont déterminés par le MTA amélioré en fonction du type et de la gravité des réponses des retours provenant du domaine d&#39;email du message.

>[!NOTE]
>
>Les paramètres de reprise dans les propriétés de la diffusion ne sont pas utilisés par Campaign.

En savoir plus sur les reprises dans [cette section](delivery-failures.md#retries).

### Règles MX spécifiques

Les règles MX (Mail eXchanger) correspondent aux règles de gestion de communication entre un serveur expéditeur et un serveur destinataire.

Le MTA amélioré dispose de ses propres règles MX. Il peut ainsi personnaliser le débit par domaine en fonction de votre réputation, basée sur l&#39;historique des emails et les commentaires en temps réel provenant des domaines auxquels vous adressez des emails.

### Signature DKIM

Domain Keys Identified Mail (DKIM) est une méthode d&#39;authentification utilisée pour détecter les adresses d&#39;expéditeur falsifiées (usurpation de nom).

Dans Adobe Campaign, la signature de l’authentification des emails DKIM est effectuée par le MTA amélioré.

En savoir plus sur DKIM dans la section [Guide des bonnes pratiques en matière de délivrabilité des Adobes](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=fr#authentication){target=&quot;_blank&quot;}.

## Service de retour d&#39;e-mail
 {#email-feedback-service}

Grâce à la fonctionnalité Service de retour d&#39;e-mail (EFS - Email Feedback Service), l&#39;état de chaque email est signalé avec précision, car les retours sont capturés directement depuis le MTA (Message Tranfer Agent) amélioré.


Une fois la diffusion lancée, le pourcentage **[!UICONTROL Succès]** n&#39;est plus modifié lorsque le message est relayé avec succès de Campaign vers le MTA amélioré.

Les logs de diffusion affichent le statut **[!UICONTROL Pris en compte par le prestataire]** pour chaque adresse ciblée.

Lorsque le message est effectivement diffusé aux profils ciblés et que ces informations sont renvoyées en temps réel du MTA amélioré, les logs de diffusion affichent l&#39;état **[!UICONTROL Envoyés]** pour chaque adresse ayant reçu le message avec succès. Le pourcentage **[!UICONTROL Succès]** augmente en conséquence lorsqu&#39;une diffusion est effectuée avec succès.

Lorsque des messages hard bounce sont signalés depuis le MTA amélioré, leur statut de log passe de **[!UICONTROL Pris en compte par le prestataire]** à **[!UICONTROL En échec]**<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->.

Lorsque des messages soft bounce sont signalés depuis le MTA amélioré, leur statut de log reste inchangé (**[!UICONTROL pris en compte par le prestataire]**) : seule la [raison de l’erreur](delivery-failures.md#delivery-failure-reasons) est mise à jour<!-- and the **[!UICONTROL Bounces + errors]** percentage is increased accordingly-->. Le pourcentage **[!UICONTROL Succès]** reste inchangé. Les messages rebonds par soft sont ensuite relancés tout au long de la diffusion. [période de validité](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target=&quot;_blank&quot;} :

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
| Le message est relayé avec succès de Campaign vers le MTA amélioré | Le pourcentage **[!UICONTROL Succès]** n’est pas affiché (démarre à 0 %) | Pris en compte par le prestataire |
| Les messages hard bounce sont renvoyés du MTA amélioré. | Aucun changement du pourcentage **[!UICONTROL Succès]** | En échec |
| Les messages soft bounce sont renvoyés du MTA amélioré. | Aucun changement du pourcentage **[!UICONTROL Succès]** | Pris en compte par le fournisseur de services |
| Les reprises des messages soft bounce sont effectuées avec succès | Le pourcentage **[!UICONTROL Succès]** augmente en conséquence | Envoyés |
| Échec des reprises des messages soft bounce | Aucun changement du pourcentage **[!UICONTROL Succès]** | En échec |
