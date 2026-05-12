---
product: campaign
title: Signal externe
description: En savoir plus sur l’activité de workflow de signal externe
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 45cb95ec-77bf-4bab-895f-b94f6ce660fd
TQID: https://experienceleague.adobe.com/w1Sip-iisntO8WLiUhYCqr-9DeiGY1F2eiU2CUSDF7c
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 171
ht-degree: 81%

---

# Signal externe{#external-signal}



L&#39;activité **Signal externe** permet de déclencher l&#39;exécution d&#39;un ensemble de tâches dans un workflow par programmation.

Lorsqu’une tâche « Signal externe » est activée, elle est suspendue indéfiniment ou jusqu’à la fin de la période spécifiée. Sa transition est activée par l’appel SOAP **PostEvent(sessionToken, workflowId, activity, transition, parameters, complete).** Le paramètre **[!UICONTROL complete]** permet de terminer la tâche, de sorte qu’elle ne réagira pas aux appels suivants.

Reportez-vous à la documentation en ligne sur les appels SOAP pour plus d&#39;information sur la fonction PostEvent.

Vous pouvez configurer cette activité afin de définir des événements en cas d’absence de signal. Pour cela, modifiez l’activité et cliquez sur l’onglet **[!UICONTROL Expiration]**. Cliquez sur le bouton **[!UICONTROL Insérer]** pour créer et configurer un événement.

![](assets/edit_signal.png)

Le paramétrage des expirations est présenté dans la section [Expirations](define-approvals.md).

Le champ **Délai** permet de spécifier un délai d&#39;expiration exprimé dans l&#39;unité de votre choix. Voir [Attente](wait.md).

Chaque ligne représente un type d&#39;expiration et correspond à une transition.

![](assets/external_sign_diag.png)
