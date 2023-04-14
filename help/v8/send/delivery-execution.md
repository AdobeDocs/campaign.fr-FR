---
title: Exécution de la diffusion des messages transactionnels
description: En savoir plus sur l'exécution et la surveillance de la diffusion des messages transactionnels
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
source-git-commit: c61f03252c7cae72ba0426d6edcb839950267c0a
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 74%

---


# Exécution de la diffusion {#delivery-execution}

Une fois l&#39;enrichissement terminé et qu&#39;un modèle de diffusion a été associé à l&#39;événement, la diffusion est envoyée depuis l&#39;instance d&#39;exécution.

>[!NOTE]
>
>Les messages transactionnels sont prioritaires sur toute autre diffusion.

Toutes les diffusions sont regroupées dans le dossier **[!UICONTROL Administration > Exploitation > Message Center > Défaut > Diffusions]**.

Par défaut, elles sont classées dans un sous-dossier correspondant au mois d&#39;envoi. Ce tri peut être modifié dans les propriétés du modèle de message.

## Surveillance de message transactionnel {#transactional-message-monitoring}

Pour surveiller vos messages transactionnels, vérifiez les [logs de diffusion](send.md).

Les diffusions transactionnelles envoyées à partir de l&#39;instance d&#39;exécution sont synchronisées à nouveau vers l&#39;instance de pilotage par le biais d&#39;un workflow technique (**[!UICONTROL instance d&#39;exécution Message Center]**) qui s&#39;exécute toutes les heures.

>[!NOTE]
>
>Les diffusions hebdomadaires accumulent les événements en fonction de la dernière mise à jour de l&#39;événement, et non de la date de création de l&#39;événement. Par conséquent, lors de l’extraction de logs de diffusion de messagerie transactionnelle à partir de l’instance de pilotage, l’identifiant de diffusion associé à chaque identifiant de log de diffusion peut changer au fil du temps lorsque le journal est mis à jour (par exemple, lorsqu’un retour entrant est reçu pour l&#39;événement).

<!--
To monitor the activity and running of the execution instance(s), see [Transactional messaging reports](transactional-messaging-reports.md).-->
