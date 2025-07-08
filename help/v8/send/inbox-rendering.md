---
product: campaign
title: Inbox rendering dans Campaign
description: Découvrez comment capturer les rendus d'email et y accéder dans un rapport dédié
feature: Inbox Rendering, Monitoring, Email Rendering
role: User
version: Campaign v8, Campaign Classic v7
exl-id: a3294e70-ac96-4e51-865f-b969624528ce
source-git-commit: 11c8c4c51c7901ba0d119323c564a64b940428b7
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 100%

---

# Inbox rendering{#inbox-rendering}

## À propos de l&#39;inbox rendering {#about-inbox-rendering}

Avant d&#39;appuyer sur le bouton **Envoyer**, vérifiez que l&#39;affichage de votre message sera optimal pour les destinataires sur divers clients web, webmails et appareils.

Pour permettre cette vérification, Adobe Campaign utilise la solution web de test d&#39;email [Litmus](https://litmus.com/email-testing){target="_blank"} afin de capturer les rendus et les rendre disponibles dans un rapport dédié. Vous pouvez ainsi visualiser l&#39;affichage du message envoyé dans les différents contextes de réception et vérifier la compatibilité sur les principaux postes de travail et dans les applications majeures.

>[!CAUTION]
>L’Inbox rendering n’est pas compatible avec les [diffusions récurrentes](../../automation/workflow/recurring-delivery.md).

Litmus est une application de validation et de prévisualisation d&#39;emails offrant de nombreuses fonctionnalités. Elle permet aux créateurs de contenus d&#39;email de prévisualiser le contenu d&#39;un message dans plus de 70 outils de rendu d&#39;email, tels que la boîte de réception Gmail ou le client Apple Mail.

Les clients mobiles, de messagerie et webmail disponibles pour l&#39;**Inbox rendering** dans Adobe Campaign sont répertoriés sur le [site web de Litmus](https://litmus.com/email-testing){target="_blank"} (cliquez sur **View all email clients**).

>[!NOTE]
>
>L&#39;Inbox rendering n&#39;est pas nécessaire pour tester les personnalisations dans les diffusions. Celles-ci peuvent être vérifiées à l&#39;aide des outils d&#39;Adobe Campaign tels que l&#39;**[!UICONTROL aperçu]** et les [bons à tirer](preview-and-proof.md#send-proofs).

## À propos des jetons Litmus {#about-litmus-tokens}

Litmus étant un service tiers, il fonctionne selon un modèle de crédit déduit par utilisation. Chaque fois qu&#39;un utilisateur fait appel à la fonctionnalité Litmus, un crédit est déduit.

Dans Adobe Campaign, le crédit correspond au nombre de rendus disponibles (appelés jetons).

>[!NOTE]
>
>Le nombre de jetons Litmus disponibles dépend de la licence Campaign que vous avez achetée. Vérifiez votre contrat de licence.

Chaque fois que vous utilisez la fonctionnalité **[!UICONTROL Inbox rendering]** dans une diffusion, un rendu généré réduit les jetons disponibles d&#39;une unité.

>[!IMPORTANT]
>
>Les jetons représentent chaque rendu et non le rapport d&#39;inbox rendering complet, ce qui signifie que :
>
>* Chaque fois que le rapport d&#39;inbox rendering est généré, un jeton est déduit par client de messagerie : un jeton pour le rendu Outlook 2000, un pour le rendu Outlook 2010, un pour le rendu Apple Mail 9, etc.
>* Pour une même diffusion, si vous régénérez le rapport d&#39;inbox rendering, le nombre de jetons disponibles est à nouveau réduit en fonction du nombre de rendus générés.
>

Le nombre de jetons disponibles restants est indiqué dans le [rapport d’inbox rendering](#inbox-rendering-report).

![](assets/s_tn_inbox_rendering_tokens.png)

En règle générale, la fonctionnalité Inbox Rendering est utilisée pour tester la structure HTML d’un nouvel e-mail. Chaque rendu nécessite environ 70 jetons (en fonction du nombre d’environnements dans lequel il est généralement testé). Toutefois, dans certains cas, vous devrez peut-être générer plusieurs rapports d’Inbox Rendering pour tester entièrement votre diffusion. Plusieurs vérifications peuvent donc nécessiter des jetons supplémentaires.

## Accéder au rapport d&#39;inbox rendering {#accessing-the-inbox-rendering-report}

Une fois que vous avez créé votre diffusion email et défini son contenu ainsi que la population ciblée, suivez la procédure décrite ci-après.

Pour plus d&#39;informations sur la conception et le ciblage d&#39;une diffusion, consultez [cette section](defining-the-email-content.md).

1. Dans la barre supérieure de la diffusion, cliquez sur le bouton **[!UICONTROL Inbox rendering]**.

1. Sélectionnez **[!UICONTROL Analyser]** pour commencer la capture.

   ![](assets/s_tn_inbox_rendering_button.png)

   Un bon à tirer est envoyé. Les vignettes de rendu sont accessibles dans ce BAT quelques minutes après l&#39;envoi des e-mails. Pour plus d&#39;informations sur l&#39;envoi de BAT, consultez[cette section](preview-and-proof.md#send-proofs).

1. Une fois envoyé, le BAT apparaît dans la liste de diffusion. Double-cliquez dessus.

   ![](assets/s_tn_inbox_rendering_delivery_list.png)

1. Accédez à l&#39;onglet **Inbox Rendering** du BAT.

   ![](assets/s_tn_inbox_rendering_tab.png)

   Le rapport d&#39;inbox rendering s&#39;affiche.

## Rapport d&#39;inbox rendering {#inbox-rendering-report}

Ce rapport présente les Inbox Renderings tels qu’ils apparaissent côté destinataire. Ils peuvent être différents selon le mode d’ouverture de la diffusion email par la personne destinataire : dans un navigateur, sur un appareil mobile ou via une application de messagerie e-mail.

La section supérieure présente la répartition du nombre de messages reçus, indésirables (spam), non reçus ou en attente de réception au moyen d’une représentation graphique avec code-couleur.

![](assets/s_tn_inbox_rendering_summary.png){width="40%" align="left"}

Survolez le graphique avec la souris pour afficher les détails de chaque couleur. Cliquez sur un élément de la liste pour masquer ou afficher la catégorie correspondante dans le graphique.

Le corps du rapport est divisé en trois parties : **[!UICONTROL Mobile]**, **[!UICONTROL Bureau]** et **[!UICONTROL Webmails]**. Faites défiler le rapport pour afficher tous les rendus regroupés dans ces trois catégories.

![](assets/s_tn_inbox_rendering_report.png)

Pour voir les détails de chaque rapport, cliquez sur la vignette correspondante. Le rendu s&#39;affiche pour le moyen de réception sélectionné.

![](assets/s_tn_inbox_rendering_example.png)
