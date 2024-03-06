---
product: campaign
title: Signal externe
description: En savoir plus sur l’activité de workflow de signal externe
feature: Workflows
role: User
exl-id: 45cb95ec-77bf-4bab-895f-b94f6ce660fd
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 78%

---

# Signal externe{#external-signal}



L&#39;activité **Signal externe** permet de déclencher l&#39;exécution d&#39;un ensemble de tâches dans un workflow par programmation.

Lorsqu’une tâche « Signal externe » est activée, elle est suspendue indéfiniment ou jusqu’à la fin de la période spécifiée. Sa transition est activée par l’appel SOAP **PostEvent(sessionToken, workflowId, activité, transition, paramètres, terminer).** Le paramètre **[!UICONTROL complet]** permet à la tâche d’être terminée. Il ne réagira donc pas aux appels suivants.

Reportez-vous à la documentation en ligne sur les appels SOAP pour plus d&#39;information sur la fonction PostEvent.

Vous pouvez paramétrer cette activité afin de définir des événements en cas d&#39;absence de signal. Pour cela, éditez l&#39;activité et cliquez sur le bouton **[!UICONTROL Expiration]** . Cliquez sur le bouton **[!UICONTROL Insérer]** pour créer et configurer un événement.

![](assets/edit_signal.png)

Le paramétrage des expirations est présenté dans la section [Expirations](define-approvals.md).

Le champ **Délai** permet de spécifier un délai d&#39;expiration exprimé dans l&#39;unité de votre choix. Voir [Attente](wait.md).

Chaque ligne représente un type d&#39;expiration et correspond à une transition.

![](assets/external_sign_diag.png)
