---
title: Prise en main du tracking des messages
description: En savoir plus sur les fonctionnalités de tracking dans Adobe Campaign
feature: Monitoring, Email
role: User
level: Beginner
exl-id: f3de901f-519f-42ae-846c-f20c7cb560df
source-git-commit: 57e177dc6c30502f2ed3bb08b18586fa5399e89c
workflow-type: tm+mt
source-wordcount: '456'
ht-degree: 73%

---

# Prise en main du tracking des messages {#get-started-tracking}

Grâce à ses fonctionnalités de tracking, Adobe Campaign permet de tracker les messages envoyés et de vérifier le comportement des destinataires : ouverture, clics sur les liens, désinscription, etc.

Ces informations sont récupérées dans l&#39;onglet **[!UICONTROL Tracking]** du profil de chaque destinataire de la diffusion. Cet onglet présente tous les liens URL trackés sur lesquels le destinataire sélectionné dans la liste a cliqué. Il s’agit de l’accumulation de toutes les URL trackées dans les diffusions qui sont toujours présentes dans l’écran de diffusion. La liste peut être configurée et contient généralement les informations suivantes : l’URL sur laquelle l’utilisateur ou l’utilisatrice a cliqué, la date et l’heure du clic et le document dans lequel l’URL a été trouvée.

Le **tableau de bord des diffusions** est également un outil essentiel pour surveiller les diffusions et les problèmes potentiels rencontrés lors de l’envoi des messages.

Le diagramme suivant présente les étapes de la conversation entre l’utilisateur ou l’utilisatrice et les différents serveurs.

<img src="assets/tracking-diagram.png" width="70%">

>[!NOTE]
>
>La configuration du tracking est effectuée par Adobe pour les déploiements de Managed Cloud Services.

## Tracking des messages {#message-tracking}

**Liens trackés**

Vous pouvez suivre la réception des messages et l&#39;activation des liens insérés dans le contenu des messages pour mieux comprendre le comportement des destinataires.

[En savoir plus sur les liens suivis](tracked-links.md)

**Tracking des URL**

Les options de tracking peuvent être paramétrées en activant ou en désactivant les URL suivies.

[En savoir plus sur les options de tracking des URL](url-tracking.md)

**Personnalisation des liens trackés**

Les fonctionnalités de tracking de Campaign vous permettent d&#39;ajouter des liens dans les e-mails, qui peuvent être personnalisés et qui prennent en charge le tracking.

[En savoir plus sur le tracking des liens personnalisés](personalized-links.md)

**Logs de tracking**

Le workflow technique de **Tracking** récupère les données de tracking une fois que la diffusion a été envoyée et que le tracking a été activé. Ces données figurent dans l&#39;onglet Tracking de votre diffusion.

[En savoir plus sur les logs de tracking](tracking-logs.md)

**Test du tracking**

Avant d&#39;envoyer vos messages avec votre tracking, vous pouvez tester ce dernier sur votre page miroir, vos logs d&#39;e-mail et vos liens.

[En savoir plus sur le tracking des tests](testing-tracking.md)

## Rapports de tracking {#tracking-reports}

**Statistiques de tracking**

Ce rapport fournit des statistiques sur les ouvertures, les clics et les transactions et vous permet de suivre l&#39;impact marketing de la diffusion.

[En savoir plus sur les rapports de tracking](../reporting/delivery-reports.md#tracking-indicators)

**URL et flux de clics**

Ce rapport présente la liste des pages visitées suite au lancement d&#39;une diffusion.

[En savoir plus sur les URL et les flux de clics](../reporting/delivery-reports.md#urls-and-click-streams)

**Personnes et destinataires**

À l’aide de cet exemple, comprenez mieux la différence de tracking entre une ou plusieurs personnes et un destinataire dans Adobe Campaign.

[En savoir plus sur les personnes et les destinataires ciblés](../reporting/metrics-calculation.md#targeted-persons---recipients)

**Indicateurs de tracking**

Ce rapport combine les indicateurs clés pour le tracking du comportement des destinataires à la réception de la diffusion, tels que les taux d’ouvertures, les taux de clics et les flux de clics.

[En savoir plus sur les indicateurs de tracking](../reporting/delivery-reports.md#tracking-indicators)

**Calcul des indicateurs**

Les différents tableaux contiennent la liste des indicateurs utilisés dans les différents rapports et leur formule de calcul en fonction du type de diffusion.

[En savoir plus sur le calcul des indicateurs](../reporting/metrics-calculation.md)


