---
product: campaign
title: Inbox rendering dans Campaign
description: Découvrez comment capturer les rendus des e-mails et y accéder dans un rapport dédié
feature: Inbox Rendering, Monitoring, Email Rendering
role: User
version: Campaign v8, Campaign Classic v7
exl-id: a3294e70-ac96-4e51-865f-b969624528ce
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c858a28b-ea19-49b0-8d48-828717fad89c
    internal-label: Prepare and test messages
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: 2317b1ea-6db4-58c7-851f-717a69c0f5c0
    internal-label: Inbox Rendering
  - id: e519a22f-a06a-42fc-9d09-d78a3ab2c434
    internal-label: Monitoring guidelines
  - id: aef0b685-fc31-54d4-b831-a87fdb9d69de
    internal-label: Email Rendering
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 98%
---
# Rendu de la boîte de réception{#inbox-rendering}

## À propos de l&#39;inbox rendering {#about-inbox-rendering}

Avant d’appuyer sur le bouton **Envoyer**, vérifiez que l’affichage de votre message sera optimal pour les destinataires sur divers clients web, webmails et appareils.

Pour permettre cette vérification, Adobe Campaign utilise la solution web de test d’e-mail [Litmus](https://litmus.com/email-testing){target="_blank"} afin de capturer les rendus et de les rendre disponibles dans un rapport dédié. Vous pouvez ainsi prévisualiser le message envoyé dans les différents contextes dans lesquels il peut être reçu et vérifier la compatibilité auprès des principaux ordinateurs de bureau et applications.

>[!CAUTION]
>L’Inbox rendering n’est pas compatible avec les [diffusions récurrentes](../../automation/workflow/recurring-delivery.md).

Litmus est une application de validation et de prévisualisation des e-mails, riche en fonctionnalités. Elle permet aux créateurs et créatrices de contenu d’e-mail de prévisualiser le contenu de leur message dans plus de 70 outils de rendu d’e-mail, tels que la boîte de réception Gmail ou le client de messagerie Apple.

Les clients mobiles, de messagerie et webmail disponibles pour l&#39;**Inbox rendering** dans Adobe Campaign sont répertoriés sur le [site web de Litmus](https://litmus.com/email-testing){target="_blank"} (cliquez sur **View all email clients**).

>[!NOTE]
>
>L&#39;Inbox rendering n&#39;est pas nécessaire pour tester les personnalisations dans les diffusions. Celles-ci peuvent être vérifiées à l&#39;aide des outils d&#39;Adobe Campaign tels que l&#39;**[!UICONTROL aperçu]** et les [bons à tirer](preview-and-proof.md#send-proofs).

## À propos des jetons Litmus {#about-litmus-tokens}

Litmus étant un service tiers, il fonctionne selon un modèle de crédit déduit par utilisation. À chaque fois qu’un utilisateur ou une utilisatrice fait appel à la fonctionnalité Litmus, un crédit est déduit.

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

En règle générale, la fonction d’inbox rendering permet de tester le framework HTML d’un e-mail nouvellement conçu. Chaque rendu nécessite environ jusqu’à 70 jetons (en fonction du nombre d’environnements généralement testés). Cependant, dans certains cas, vous aurez peut-être besoin de plusieurs rapports d’Inbox Rendering pour tester entièrement votre diffusion. Plusieurs contrôles pourraient donc nécessiter davantage de jetons.

## Accéder au rapport d&#39;inbox rendering {#accessing-the-inbox-rendering-report}

Une fois que vous avez créé votre diffusion email et défini son contenu ainsi que la population ciblée, suivez la procédure décrite ci-après.

La création, la conception et le ciblage d&#39;une diffusion sont présentés dans cette [page](defining-the-email-content.md).


1. Dans la barre supérieure de la diffusion, cliquez sur le bouton **[!UICONTROL Inbox rendering]**.

1. Sélectionnez **[!UICONTROL Analyser]** pour commencer la capture.

   ![](assets/s_tn_inbox_rendering_button.png)

   Un BAT est envoyé. Les miniatures de rendu sont accessibles dans ce BAT quelques minutes après l’envoi des e-mails. Pour plus d&#39;informations sur l&#39;envoi de BAT, consultez[cette section](preview-and-proof.md#send-proofs).

1. Une fois envoyé, le BAT apparaît dans la liste de diffusion. Double-cliquez dessus.

   ![](assets/s_tn_inbox_rendering_delivery_list.png)

1. Accédez à l&#39;onglet **Inbox Rendering** du BAT.

   ![](assets/s_tn_inbox_rendering_tab.png)

   Le rapport d&#39;inbox rendering s&#39;affiche.

## Rapport d&#39;inbox rendering {#inbox-rendering-report}

Ce rapport présente les Inbox Renderings tels qu’ils apparaissent côté destinataire. Les rendus peuvent être différents selon le mode d’ouverture de la diffusion e-mail par la personne destinataire : dans un navigateur, sur un appareil mobile ou via une application de messagerie.

La section supérieure présente la répartition du nombre de messages reçus, indésirables (spam), non reçus ou en attente de réception au moyen d’une représentation graphique avec code-couleur.

![](assets/s_tn_inbox_rendering_summary.png){width="40%"}

Survolez le graphique avec la souris pour afficher les détails de chaque couleur. Cliquez sur un élément de la liste pour masquer ou afficher la catégorie correspondante dans le graphique.

Le corps du rapport est divisé en trois parties : **[!UICONTROL Mobile]**, **[!UICONTROL Bureau]** et **[!UICONTROL Webmails]**. Faites défiler le rapport pour afficher tous les rendus regroupés dans ces trois catégories.

![](assets/s_tn_inbox_rendering_report.png)

Pour voir les détails de chaque rapport, cliquez sur la vignette correspondante. Le rendu s’affiche pour le moyen de réception sélectionné.

![](assets/s_tn_inbox_rendering_example.png)
