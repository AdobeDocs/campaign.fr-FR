---
title: Gestion des quarantaines dans Campaign
description: Présentation de la gestion des quarantaines dans Adobe Campaign
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: 220b7a88-bd42-494b-b55b-b827b4971c9e
source-git-commit: c316da3c431e42860c46b5a23c73a7c129abf3ac
workflow-type: tm+mt
source-wordcount: '1170'
ht-degree: 36%

---

# Quarantaines {#quarantine-management}

Adobe Campaign gère une liste d&#39;adresses en quarantaine pour les canaux en ligne (email, SMS, notification push). Certains fournisseurs d&#39;accès Internet considèrent automatiquement les emails comme du spam si le taux d&#39;adresses invalides est trop élevé. La quarantaine permet donc d&#39;éviter d&#39;être ajouté à une liste bloquée par ces fournisseurs. De plus, elles réduisent les coûts d’envoi des SMS en excluant les numéros de téléphone erronés des diffusions.

Lors de la mise en quarantaine de leur adresse ou numéro de téléphone, les destinataires sont exclus de la cible lors de l&#39;analyse de la diffusion : vous ne pourrez pas envoyer de messages marketing, y compris des emails de workflow automatisés, à ces contacts. Si ces adresses en quarantaine sont également présentes dans les listes, elles seront exclues lors de l&#39;envoi vers ces listes. Une adresse email peut être mise en quarantaine, par exemple, lorsque la boîte de messagerie est pleine, si l’adresse n’existe pas ou si le serveur de messagerie n’est pas disponible, par exemple.

<!--For more on best practices to secure and optimize your deliveries, refer to [this page](delivery-best-practices.md).-->

**Quarantaine** s’applique uniquement à un événement **address**, un **numéro de téléphone** ou un **jeton de périphérique**, mais pas au profil lui-même. Par exemple, un profil dont l’adresse e-mail est en quarantaine peut mettre à jour son profil et saisir une nouvelle adresse, puis être ciblé de nouveau par des actions de diffusion. De même, si deux profils ont le même numéro de téléphone, ils seront tous deux affectés si le numéro est mis en quarantaine. Les adresses ou numéros de téléphone mis en quarantaine s’affichent dans les [logs d&#39;exclusion](#delivery-quarantines) (pour une diffusion) ou dans la [liste de quarantaine](#non-deliverable-bounces) (pour l&#39;ensemble de la plateforme).

D’un autre côté, les profils peuvent se trouver dans la variable **liste bloquée** comme après une désinscription (opt-out), pour un canal donné : cela signifie qu’ils ne sont plus ciblés par aucun d’eux. Par conséquent, si un profil sur la liste bloquée du canal email comporte deux adresses email, les deux adresses seront exclues de la diffusion. Vous pouvez vérifier si un profil est sur liste bloquée pour un ou plusieurs canaux dans la section **[!UICONTROL Ne plus contacter]** de l’onglet **[!UICONTROL Général]** du profil. [En savoir plus](../audiences/view-profiles.md).

>[!NOTE]
>
>Lorsque les destinataires signalent votre message comme du spam ou répondent à un message SMS avec un mot-clé tel que &quot;STOP&quot;, leur adresse ou numéro de téléphone est mis en quarantaine comme **[!UICONTROL Placé sur la liste bloquée]**. Leur profil est mis à jour en conséquence.
>
> Pour le canal email, les adresses email sont mises en quarantaine. Pour le canal des applications mobiles, les jetons de l’appareil sont mis en quarantaine. Pour le canal SMS, les numéros de téléphone sont mis en quarantaine.

## Pourquoi un email, un téléphone ou un appareil est-il mis en quarantaine ? {#quarantine-reason}

Adobe Campaign gère les quarantaines en fonction du type de diffusion en échec et de sa raison. Elles sont affectées pendant la qualification des messages d’erreur. En savoir plus sur la gestion des échecs de diffusion [dans cette page](delivery-failures.md).

Deux types ou erreurs peuvent être capturés :

* **Erreur de type Hard**: l’adresse email, le numéro de téléphone ou l’appareil est immédiatement mis en quarantaine.
* **Erreur de type Soft**: les erreurs soft incrémentent un compteur d’erreurs et peuvent mettre en quarantaine un email, un numéro de téléphone ou un jeton d’appareil. Performances de la campagne [reprises](delivery-failures.md#retries).: lorsque le compteur d’erreurs atteint le seuil limite, l’adresse, le numéro de téléphone ou le jeton de l’appareil est mis en quarantaine. [En savoir plus](delivery-failures.md#retries).


Dans la liste des adresses en quarantaine, le champ **[!UICONTROL Raison de l&#39;erreur]** indique pourquoi l&#39;adresse sélectionnée a été mise en quarantaine. [En savoir plus](#identifying-quarantined-addresses-for-the-entire-platform).


Si un utilisateur qualifie un email comme du spam, le message est automatiquement redirigé vers une boîte email technique gérée par Adobe. L’adresse e-mail de l’utilisateur est alors automatiquement mise en quarantaine avec le statut **[!UICONTROL Sur liste bloquée]**. Ce statut ne concerne que l’adresse. Le profil n’est pas placé sur liste bloquée afin que l’utilisateur puisse continuer à recevoir des SMS et des notifications push. En savoir plus sur les boucles de rétroaction dans la section [Guide des bonnes pratiques de diffusion](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=fr#feedback-loops).

>[!NOTE]
>
>La quarantaine dans Adobe Campaign respecte la casse. Veillez à importer les adresses email en minuscules, de telle sorte qu&#39;elles ne soient pas reciblées ultérieurement.

## Accéder aux adresses en quarantaine {#access-quarantined-addresses}

Les adresses en quarantaine peuvent être affichées pour une diffusion spécifique ou l&#39;ensemble de la plateforme.

### Quarantaines pour une diffusion{#delivery-quarantines}

Les adresses de quarantaine sont répertoriées pendant la phase de préparation de la diffusion, dans les logs de diffusion du tableau de bord de la diffusion.

Pour chaque diffusion, vous pouvez également vérifier la variable **[!UICONTROL Synthèse des diffusions]** rapport : il indique le nombre d&#39;adresses en quarantaine dans la cible de la diffusion et affiche :

* le nombre d&#39;adresses mises en quarantaine lors de l&#39;analyse de la diffusion,
* le nombre d&#39;adresses passées en quarantaine suite à l&#39;action de diffusion.

### Adresses de non-délivrabilité et de rebond{#non-deliverable-bounces}

Pour afficher la liste des adresses en quarantaine **pour l’ensemble de la plateforme**, les administrateurs de Campaign peuvent accéder à  **[!UICONTROL Administration > Campaign Management > Gestion des échecs > Echecs et adresses]**. Cette section répertorie les éléments mis en quarantaine pour **email**, **SMS** et **Notification push** canaux.

![](assets/tech-quarantine.png)

>[!NOTE]
>
>Le nombre de quarantaines augmente avec le temps. Par exemple, si l&#39;on considère que la durée de vie d&#39;une adresse email est de trois ans et que la table des destinataires augmente de 50% tous les ans, l&#39;augmentation des quarantaines peut être calculée comme suit :
>
>Fin de l’année 1 : (1)&#42;0,33)/(1+0,5)=22 %.
>
>Fin de l’année 2 : (1.22)&#42;0,33)+0,33)/(1,5+0,75)=32,5 %.

En outre, la variable **[!UICONTROL Echecs et retours]** rapport intégré, disponible à partir de la **Rapports** de cette page d&#39;accueil, affiche des informations sur les adresses en quarantaine, les types d&#39;erreurs rencontrées et une répartition des échecs par domaine. Vous pouvez filtrer les données pour une diffusion spécifique ou personnaliser ce rapport si nécessaire.

En savoir plus sur les adresses de rebond dans [Guide des bonnes pratiques de délivrabilité](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html?lang=fr)

### Email en quarantaine {#quarantined-recipient}

Vous pouvez consulter le statut de l&#39;adresse email de n&#39;importe quel destinataire.

Pour cela, sélectionnez le profil du destinataire et cliquez sur le bouton **[!UICONTROL Diffusions]** . Pour toutes les diffusions vers ce destinataire, vous pouvez déterminer si l&#39;adresse a échoué, a été mise en quarantaine lors de l&#39;analyse, etc.

Pour chaque dossier, vous ne pouvez afficher que les destinataires dont l&#39;adresse email est en quarantaine, avec la variable **[!UICONTROL Email en quarantaine]** filtre intégré, comme ci-dessous :

![](assets/quarantine-filter.png)


## Sortie dʼune adresse de quarantaine {#remove-a-quarantined-address}

Les adresses qui correspondent à des conditions spécifiques sont automatiquement supprimées de la liste de quarantaine par la fonction **Nettoyage de la base** workflow intégré.

Les adresses sont automatiquement supprimées de la liste de quarantaine dans les cas suivants :

* Les adresses dont l&#39;état est **[!UICONTROL En erreur]** seront supprimées de la liste de quarantaine après une diffusion réussie.
* Les adresses dont l&#39;état est **[!UICONTROL En erreur]** seront supprimées de la liste de quarantaine si la dernière erreur de type Soft a eu lieu il y a plus de 10 jours. Pour plus d&#39;informations sur la gestion des erreurs de type Soft, consultez [cette section](#soft-error-management).
* Les adresses dont l&#39;état est **[!UICONTROL En erreur]** et qui ont rebondi avec l&#39;erreur **[!UICONTROL Boîte pleine]** sont supprimées de la liste de quarantaine après 30 jours.

Leur état devient ensuite **[!UICONTROL Valide]**.

>[!CAUTION]
>
>Les destinataires avec une adresse dont le statut est **[!UICONTROL En quarantaine]** ou **[!UICONTROL Sur liste bloquée]** ne seront jamais supprimés, même s&#39;ils reçoivent un e-mail.

Vous pouvez également supprimer manuellement une adresse de la liste de quarantaine. Pour retirer une adresse de la quarantaine, vous pouvez :

* Remplacez son état par **[!UICONTROL Valide]** de la **[!UICONTROL Administration > Campaign Management > Gestion des échecs > Echecs et adresses]** noeud .

   ![](assets/tech-quarantine-status.png)

* Remplacez son état par **[!UICONTROL Placé sur la liste autorisée]**: dans ce cas, l&#39;adresse reste sur la liste des quarantaines, mais elle sera systématiquement ciblée, même en cas d&#39;erreur.

>[!CAUTION]
>
>Si vous supprimez une adresse de la liste de quarantaine, vous recommencerez à l’envoyer à cette adresse. Cela peut avoir de graves répercussions sur votre délivrabilité et votre réputation IP, ce qui peut éventuellement entraîner le blocage de votre adresse IP ou de votre domaine d’envoi. Procédez avec précaution lorsque vous envisagez de supprimer une adresse de quarantaine. Si vous avez besoin d’aide, contactez l’assistance Adobe.
