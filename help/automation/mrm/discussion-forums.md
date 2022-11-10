---
product: campaign
title: Forums de discussion
description: Découvrez comment utiliser les forums de discussion de Campaign
exl-id: c2336507-beea-4ddb-aa8c-1ec591eb5683
source-git-commit: 72fc29c49fca5767133be4a9927b57b3cfb51a14
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 32%

---

# Forums de discussion{#discussion-forums}

Les opérateurs Adobe Campaign peuvent utiliser les forums de discussion pour partager des informations. Les éléments suivants ont chacun leur propre forum : plans, programmes, campagnes, ressources marketing, simulations, stocks. Chaque opérateur a également un forum personnel. Toutes les discussions sont publiques, même sur des forums personnels.

Les opérateurs peuvent s&#39;abonner à des forums afin de recevoir un email de notification à chaque message posté dans ceux-ci.

## Accéder à un forum {#accessing-a-forum}

Pour accéder à un forum, accédez à un tableau de bord et cliquez sur le bouton **[!UICONTROL Forum]** dans le coin supérieur droit.

![](assets/mrm-forum-icon.png)

Les messages et leurs réponses sont affichés du plus récent au plus ancien.

Pour démarrer un nouveau thread, cliquez sur le bouton **[!UICONTROL Ajouter une discussion]** dans le coin supérieur droit. Le **[!UICONTROL Forum de discussion]** apparaît (voir ci-dessous).

![](assets/mrm-forum-new-thread.png)


Saisissez votre texte dans la zone **[!UICONTROL Message]** et, le cas échéant, un titre pour la discussion dans le champ **[!UICONTROL Sujet]**.

Les opérateurs qui ont déjà posté un message dans ce forum sont notifiés par défaut. Vous pouvez sélectionner un opérateur supplémentaire à avertir. Pour notifier plusieurs opérateurs, sélectionnez un groupe d&#39;opérateurs.

Vous pouvez ajouter une pièce jointe au message à l’aide de la fonction  **[!UICONTROL Parcourir..]** bouton . La pièce jointe sera également incluse dans l&#39;email de notification. Les pièces jointes ne peuvent être envoyées qu’une seule fois : pour envoyer plusieurs fichiers, vous devez les compresser dans un fichier .zip.

>[!CAUTION]
>
>Une fois un message posté dans le forum, il ne peut plus être modifié ni supprimé.

## Poster un message dans le forum personnel d&#39;un opérateur {#posting-to-the-personal-forum-of-an-operator}

Vous pouvez poster un message dans le forum d&#39;un opérateur. Les forums personnels sont publics et tous les opérateurs peuvent voir votre message. L&#39;opérateur reçoit un email de notification chaque fois qu&#39;une personne publie sur son forum personnel.

Pour accéder au forum d&#39;un opérateur, vous pouvez :

* Accédez au **[!UICONTROL Administration > Gestion des accès > Opérateurs]** dossier de l&#39;explorateur Campaign, sélectionnez l&#39;opérateur pour ouvrir son tableau de bord, puis cliquez sur le bouton **[!UICONTROL Forum]** dans le coin supérieur droit.
* Recherchez le nom de l&#39;opérateur dans l&#39;interface utilisateur d&#39;Adobe Campaign (via un message posté dans le forum par cet opérateur, une tâche qui lui est assignée) et cliquez dessus pour accéder au tableau de bord de l&#39;opérateur.

## S&#39;abonner à un forum {#subscribing-to-a-forum}

S&#39;abonner à un forum permet de suivre toutes les discussions. Une fois abonné, vous recevez une notification par email chaque fois qu&#39;un message est posté sur le forum.

Pour répondre à un message, cliquez dans le corps de l&#39;email, puis connectez-vous à l&#39;interface web d&#39;Adobe Campaign.

* Pour vous abonner à un forum, cliquez sur le bouton **[!UICONTROL Suivre les discussions]** dans le bandeau au-dessus de la liste des messages, à droite.

   Le bandeau devient bleu et indique que vous êtes abonné au forum.

* Pour vous désabonner d&#39;un forum, cliquez sur le bouton **[!UICONTROL Se désabonner]** dans le bandeau.

* Dans votre tableau de bord personnel, vous pouvez voir la liste des forums auxquels vous êtes abonné afin de pouvoir accéder à ceux-ci plus rapidement. Cliquez sur le lien **[!UICONTROL Abonnements aux forums de discussion]** pour afficher la liste, puis cliquez sur le nom de l&#39;élément désiré pour accéder à son forum.

   ![](assets/forum-subscribed.png)


## Dépannage de la diffusion de notification {#checking-notification-delivery}

Si les opérateurs abonnés à un forum ne reçoivent pas les notifications comme prévu :

* Vérifiez que les opérateurs ont bien une adresse email renseignée dans leur profil.
* Accédez au **[!UICONTROL Administration > Exploitation > Workflows techniques > Processus de campagne]** dossier de l&#39;explorateur Campaign et vérifiez les **[!UICONTROL Traitements dans les forums de discussion]** Le workflow est démarré sans erreur.
* Vérifiez les logs de diffusion :

   * Sur la page d’accueil d’Adobe Campaign, accédez à **[!UICONTROL Campagnes > Navigation > Diffusions]**, puis ouvrez le **[!UICONTROL Notification du forum de discussion]** diffusion.
   * Dans l&#39;explorateur Campaign, accédez à **[!UICONTROL Administration > Exploitation > Objets créés automatiquement > Diffusions techniques > Notifications de workflow]**, puis cliquez sur **[!UICONTROL Notifications des forums de discussion]**.
   Dans la boîte **[!UICONTROL Notification des forums de discussion]**, les logs de diffusion se trouvent dans l&#39;onglet **[!UICONTROL Édition > Diffusion]**. Consultez également les onglets **[!UICONTROL Tracking > Journal]** et **[!UICONTROL Causes d&#39;exclusion]**.
