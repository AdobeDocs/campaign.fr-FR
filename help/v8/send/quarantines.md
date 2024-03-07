---
title: Gestion des quarantaines dans Campaign
description: Comprendre la gestion des quarantaines dans Adobe Campaign
feature: Profiles, Monitoring
role: User, Data Engineer
level: Beginner
exl-id: 220b7a88-bd42-494b-b55b-b827b4971c9e
source-git-commit: e45799f0f3849d53d2c5f593bc02954b3a55fc28
workflow-type: tm+mt
source-wordcount: '1221'
ht-degree: 98%

---

# Quarantaine {#quarantine-management}

Adobe Campaign gère une liste d&#39;adresses en quarantaine pour les canaux en ligne (e-mail, SMS, notification push). Certains fournisseurs d&#39;accès à internet considèrent automatiquement les e-mails comme du spam si le taux d&#39;adresses non valides est trop élevé. La quarantaine permet donc d&#39;éviter d&#39;être ajouté à une liste bloquée par ces fournisseurs. De plus, elle réduit les coûts d&#39;envoi des SMS en excluant les numéros de téléphone erronés des diffusions.

Lors de la mise en quarantaine de leur adresse ou numéro de téléphone, les destinataires sont exclus de la cible lors de l&#39;analyse de la diffusion : vous ne pourrez pas envoyer de messages marketing, y compris des e-mails de workflow automatisés, à ces contacts. Si ces adresses en quarantaine sont également présentes dans les listes, elles seront exclues lors de l&#39;envoi vers ces listes. Une adresse e-mail peut être mise en quarantaine, par exemple, lorsque la boîte de réception est pleine, si l&#39;adresse n&#39;existe pas ou si le serveur de messagerie n&#39;est pas disponible.

<!--For more on best practices to secure and optimize your deliveries, refer to [this page](delivery-best-practices.md).-->

La **quarantaine** s&#39;applique uniquement à une **adresse**, un **numéro de téléphone** ou un **jeton d&#39;appareil**, mais pas au profil lui-même. Par exemple, un profil dont l&#39;adresse e-mail est en quarantaine peut mettre à jour son profil et saisir une nouvelle adresse, puis être ciblé de nouveau par des actions de diffusion. De même, si deux profils ont le même numéro de téléphone, ils seront tous deux affectés si le numéro est mis en quarantaine. Les adresses ou numéros de téléphone mis en quarantaine s&#39;affichent dans les [logs d&#39;exclusion](#delivery-quarantines) (pour une diffusion) ou dans la [liste de quarantaine](#non-deliverable-bounces) (pour l&#39;ensemble de la plateforme).

D&#39;un autre côté, les profils peuvent se trouver dans la **liste bloquée** comme après une désinscription (opt-out), pour un canal donné : cela signifie qu&#39;ils ne sont plus ciblés par aucun d&#39;eux. Ainsi, si un profil de la liste bloquée pour le canal e-mail comporte deux adresses e-mail, les deux adresses seront exclues de la diffusion. Vous pouvez vérifier si un profil est sur liste bloquée pour un ou plusieurs canaux dans la section **[!UICONTROL Ne plus contacter]** de l’onglet **[!UICONTROL Général]** du profil. [En savoir plus](../audiences/view-profiles.md)

>[!NOTE]
>
>Lorsque les destinataires signalent votre message comme spam ou répondent à un message SMS avec un mot-clé tel que « STOP », leur adresse ou numéro de téléphone est mis en quarantaine comme **[!UICONTROL Placé sur la liste bloquée]**. Leur profil est mis à jour en conséquence.

<!--For the email channel, email addresses are quarantined. For the mobile app channel, device tokens are quarantined. For the SMS channel, phone numbers are quarantined.?-->

## Pourquoi un e-mail, un numéro de téléphone ou un appareil est-il mis en quarantaine ? {#quarantine-reason}

Adobe Campaign gère les quarantaines en fonction du type d&#39;échec de diffusion et de sa raison. Elles sont affectées pendant la qualification des messages d&#39;erreur. Apprenez-en davantage sur la gestion des échecs de diffusion [dans cette page](delivery-failures.md).

Deux types ou erreurs peuvent être capturés :

* **Erreur de type Hard** : l&#39;adresse e-mail, le numéro de téléphone ou l&#39;appareil est immédiatement mis en quarantaine.
* **Erreur de type Soft** : les erreurs soft incrémentent un compteur d&#39;erreurs et peuvent mettre en quarantaine un e-mail, un numéro de téléphone ou un jeton d&#39;appareil. Campaign effectue des [reprises](delivery-failures.md#retries) : lorsque le compteur d&#39;erreurs atteint le seuil limite, l&#39;adresse, le numéro de téléphone ou le jeton de l&#39;appareil est mis en quarantaine. [En savoir plus](delivery-failures.md#retries).

Dans la liste des adresses en quarantaine, le champ **[!UICONTROL Raison de l&#39;erreur]** indique pourquoi l&#39;adresse sélectionnée a été mise en quarantaine. [En savoir plus](#identifying-quarantined-addresses-for-the-entire-platform).


Si un utilisateur qualifie un e-mail comme spam, le message est automatiquement redirigé vers une boîte e-mail technique gérée par Adobe. L&#39;adresse e-mail de l&#39;utilisateur est alors automatiquement mise en quarantaine avec le statut **[!UICONTROL Sur liste bloquée]**. Ce statut ne concerne que l&#39;adresse. Le profil n&#39;est pas placé sur liste bloquée afin que l&#39;utilisateur puisse continuer à recevoir des SMS et des notifications push. Apprenez-en davantage sur les feedback loops dans la section [Guide des bonnes pratiques de diffusion](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=fr#feedback-loops){target="_blank"}.

>[!NOTE]
>
>La quarantaine dans Adobe Campaign respecte la casse. Veillez à importer les adresses e-mail en minuscules, de telle sorte qu&#39;elles ne soient pas reciblées ultérieurement.

## Accéder aux adresses en quarantaine {#access-quarantined-addresses}

Les adresses en quarantaine peuvent être affichées pour une diffusion spécifique ou l&#39;ensemble de la plateforme.

### Quarantaines pour une diffusion{#delivery-quarantines}

Les adresses de quarantaine sont répertoriées pendant la phase de préparation de la diffusion, dans les logs de diffusion du tableau de bord de la diffusion.

Pour chaque diffusion, vous pouvez également consulter le rapport **[!UICONTROL Synthèse des diffusions]**, qui indique le nombre d&#39;adresses en quarantaine dans la cible de diffusion et affiche :

* le nombre d&#39;adresses mises en quarantaine lors de l&#39;analyse de la diffusion,
* le nombre d&#39;adresses passées en quarantaine suite à l&#39;action de diffusion.

### Adresses de non-délivrabilité et de rebond{#non-deliverable-bounces}

Pour afficher la liste des adresses en quarantaine **pour l&#39;ensemble de la plateforme**, les administrateurs de Campaign peuvent accéder à **[!UICONTROL Administration > Campaign Management > Gestion des échecs > Échecs et adresses]**. Cette section répertorie les éléments en quarantaine pour les canaux **e-mail**, **SMS** et **notification push**.

![](assets/tech-quarantine.png)

>[!NOTE]
>
>Le nombre de quarantaines augmente avec le temps. Par exemple, si l&#39;on considère que la durée de vie d&#39;une adresse e-mail est de trois ans et que la table des destinataires augmente de 50 % tous les ans, l&#39;augmentation des quarantaines peut être calculée comme suit :
>
>Fin de l&#39;année 1 : (1 &#42; 0,33) / (1 + 0,5) = 22 %.
>
Fin de l&#39;année 2 : ((1,22 &#42; 0,33) + 0,33) / (1,5 + 0,75) = 32,5 %.

En outre, le rapport intégré **[!UICONTROL Non-délivrables et rebonds]**, disponible à partir de la section **Rapports** de cette page d’accueil, affiche des informations sur les adresses en quarantaine, les types d’erreurs rencontrées et une répartition des échecs par domaine. Vous pouvez filtrer les données pour une diffusion spécifique ou personnaliser ce rapport si nécessaire.

En savoir plus sur les adresses de rebond dans [Guide des bonnes pratiques de délivrabilité](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html?lang=fr){target="_blank"}.

### E-mail en quarantaine {#quarantined-recipient}

Vous pouvez consulter le statut de l&#39;adresse e-mail de n&#39;importe quel destinataire.

Pour cela, sélectionnez le profil du destinataire et cliquez sur l&#39;onglet **[!UICONTROL Diffusions]**. Pour toutes les diffusions vers ce destinataire, vous pouvez déterminer si l&#39;adresse a échoué, a été mise en quarantaine lors de l&#39;analyse, etc.

Pour chaque dossier, vous ne pouvez afficher que les destinataires dont l&#39;adresse e-mail est en quarantaine, avec le filtre intégré **[!UICONTROL E-mail en quarantaine]**, comme ci-dessous :

![](assets/quarantine-filter.png)


## Supprimer une adresse de la quarantaine {#remove-a-quarantined-address}

Les adresses qui correspondent à des conditions spécifiques sont automatiquement supprimées de la liste de quarantaine par le workflow intégré **Nettoyage de la base**.

Les adresses sont automatiquement supprimées de la liste de quarantaine dans les cas suivants :

* Les adresses dont l&#39;état est **[!UICONTROL En erreur]** seront supprimées de la liste de quarantaine après une diffusion réussie.
* Les adresses dont l’état est **[!UICONTROL En erreur]** seront supprimées de la liste de quarantaine si le dernier rebond temporaire a eu lieu il y a plus de 10 jours. Pour plus d&#39;informations sur la gestion des erreurs de type Soft, consultez [cette section](#soft-error-management).
* Les adresses dont l&#39;état est **[!UICONTROL En erreur]** et qui ont rebondi avec l&#39;erreur **[!UICONTROL Boîte pleine]** sont supprimées de la liste de quarantaine après 30 jours.

Leur état devient ensuite **[!UICONTROL Valide]**.

>[!CAUTION]
>
Les destinataires avec une adresse dont le statut est **[!UICONTROL En quarantaine]** ou **[!UICONTROL Sur liste bloquée]** ne seront jamais supprimés, même s&#39;ils reçoivent un e-mail.

Vous pouvez également supprimer manuellement une adresse de la liste de quarantaine. Pour supprimer une adresse de la quarantaine, vous pouvez :

* Changer son statut en **[!UICONTROL Valide]** depuis le nœud **[!UICONTROL Administration > Campaign Management > Gestion des échecs > Échecs et bounce]**.

  ![](assets/tech-quarantine-status.png)

Vous devrez peut-être effectuer des mises à jour en bloc sur la liste de quarantaine, par exemple en cas de panne du FAI, où les e-mails sont marqués comme des rebonds par erreur, car ils ne peuvent pas être correctement diffusés à leur destination.

Pour ce faire, créez un workflow et ajoutez une requête sur votre table de quarantaine pour filtrer toutes les destinations concernées, de façon à ce qu’elles puissent être supprimées de la liste de quarantaine et incluses dans les prochaines diffusions e-mail de Campaign.

Vous trouverez ci-dessous les instructions recommandées pour cette requête :

* **Texte d&#39;erreur (texte de la quarantaine)** contenant « Momen_Code10_InvalidRecipient »
* **Domaine d’e-mail (@domain)** égal à domain1.com OU **domaine d’email (@domain)** égal à domain2.com OU **domaine d’email (@domain)** égal à domain3.com
* **Mise à jour du statut (@lastModified)** sur ou après `MM/DD/YYYY HH:MM:SS AM`
* **Mise à jour du statut (@lastModified)** le ou avant `MM/DD/YYYY HH:MM:SS PM`

Une fois que vous disposez de la liste des destinations concernées, ajoutez une activité **[!UICONTROL Mise à jour de données]** pour définir leur statut sur **[!UICONTROL Valide]**, de façon à ce qu’elles soient supprimées de la liste de quarantaine par le workflow **[!UICONTROL Nettoyage de la base de données]**. Vous pouvez également les supprimer simplement de la table de quarantaine.

