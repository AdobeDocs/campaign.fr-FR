---
title: Envoi et surveillance des messages transactionnels
description: Découvrez comment envoyer et surveiller des messages transactionnels
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: 084607f6-47d8-40c0-89ba-bfbb88fc2e53
source-git-commit: c044b391c900e8ff82147f2682e2e4f91845780c
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 69%

---

# Envoi et surveillance des messages transactionnels {#delivery-execution}

## Envoi de messages{#send-transactional-msg}

Une fois l&#39;enrichissement terminé et qu&#39;un modèle de diffusion a été associé à l&#39;événement, la diffusion est envoyée depuis l&#39;instance d&#39;exécution.

>[!NOTE]
>
>Les messages transactionnels sont prioritaires sur toute autre diffusion.

Toutes les diffusions sont regroupées dans le dossier **[!UICONTROL Administration > Exploitation > Message Center > Défaut > Diffusions]**.

Par défaut, elles sont classées dans un sous-dossier correspondant au mois d&#39;envoi. Cela peut être modifié dans les propriétés du modèle de message.

## Surveillance des messages {#monitor-transactional-msg}

Pour surveiller vos messages transactionnels, vérifiez les [logs de diffusion](send.md).

Les diffusions transactionnelles envoyées à partir de l&#39;instance d&#39;exécution sont synchronisées à nouveau vers l&#39;instance de pilotage par le biais d&#39;un workflow technique (**[!UICONTROL instance d&#39;exécution Message Center]**) qui s&#39;exécute toutes les heures.

>[!NOTE]
>
>Les diffusions hebdomadaires accumulent les événements en fonction de la dernière mise à jour de l&#39;événement, et non de la date de création de l&#39;événement. Par conséquent, lors de l&#39;extraction de logs de diffusion de messagerie transactionnelle à partir de l&#39;instance de pilotage, l&#39;identifiant de diffusion associé à chaque identifiant de log de diffusion peut changer au fil du temps lorsque le journal est mis à jour (par exemple, lorsqu&#39;un retour entrant est reçu pour l&#39;événement).

<!--
To monitor the activity and running of the execution instance(s), see [Transactional messaging reports](transactional-messaging-reports.md).-->

## Créer des rapports{#reporting-transactional-msg}

Adobe Campaign propose plusieurs rapports qui permettent de contrôler l&#39;activité et le bon fonctionnement des instances d&#39;exécution.

Ces rapports Message Center sont accessibles à partir de l&#39;onglet **[!UICONTROL Rapports]** de l&#39;**instance de pilotage**.

![](assets/mc-reports.png)

### Historique des événements de Message Center {#history-events}

Le **[!UICONTROL Historique des événements Message Center]** Ce rapport présente une vue d&#39;ensemble de l&#39;activité du module Message Center, c&#39;est-à-dire le nombre d&#39;événements traités et envoyés sous forme de messages transactionnels.

Lors de l&#39;ouverture du rapport, les informations affichées par défaut correspondent au taux de messages transactionnels envoyés avec succès. Pour visualiser davantage de niveaux, vous pouvez déplier ou replier les différents noeuds et positionner le pointeur de la souris pour mettre en surbrillance le niveau voulu.

Pour chaque période de temps, vous pouvez visualiser les données propres à chacun des types d&#39;événements. La colonne **[!UICONTROL Evénements]** correspond au nombre d&#39;événements reçus par l&#39;instance de pilotage. Le calcul du nombre d&#39;événements transformés en message transactionnel personnalisé se trouve dans la colonne **[!UICONTROL Envoyés]**.


### Temps de traitement Message Center {#processing-time}

Le **[!UICONTROL Temps traitement Message Center]** affiche les principaux indicateurs relatifs à la file d’attente temps réel. Ce rapport est également accessible à partir du **[!UICONTROL Surveillance]** sur l’instance de pilotage.

![](assets/mc-processing-time-report.png)

Vous pouvez choisir d&#39;afficher les statistiques globales ou relatives à une instance d&#39;exécution particulière. Vous pouvez également filtrer les données par canal et sur une période spécifique.

Les indicateurs affichés dans la section **[!UICONTROL Indicateurs sur la période]** sont calculés sur la période sélectionnée :

* **[!UICONTROL Temps moyen dans la file (s)]** : temps moyen passé dans Message Center pour les événements traités avec succès. Seul le temps de traitement est pris en compte.
* **[!UICONTROL Temps moyen d&#39;envoi des messages (s)]** : temps moyen passé dans Message Center pour les événements traités avec succès. Seul le temps d&#39;envoi par les mta est pris en compte.
* **[!UICONTROL Temps moyen de traitement (s)]** : temps moyen passé dans Message Center pour les événements traités avec succès. Ce calcul prend en compte le temps de traitement et le temps d&#39;envoi par les mta.
* **[!UICONTROL Maximum des événements en file]** : nombre maximum d&#39;événements présents dans la file Message Center à un même moment.
* **[!UICONTROL Minimum des événements en file]** : nombre minimum d&#39;événements présents dans la file Message Center à un même moment.
* **[!UICONTROL Moyenne des événements en file]** : nombre moyen d&#39;événements présents dans la file Message Center à un même moment.

>[!NOTE]
>
>Les seuils d&#39;avertissement (orange) et d&#39;alerte (rouge) des indicateurs sont paramétrables dans l&#39;assistant de déploiement d&#39;Adobe Campaign. Voir [Seuils de suivi](#thresholds).



### Qualité de service Message Center {#service-level}

Le **[!UICONTROL Qualité de service Message Center]** affiche les statistiques de diffusion relatives aux messages transactionnels ainsi que la répartition des erreurs. Vous pouvez cliquer sur un type d&#39;erreur pour en afficher les détails.

Ce rapport est également accessible à partir du **[!UICONTROL Surveillance]** sur l’instance de pilotage.

Vous pouvez choisir d&#39;afficher les statistiques globales ou relatives à une instance d&#39;exécution particulière. Vous pouvez également filtrer les données par canal et sur une période spécifique.

Les indicateurs affichés dans la section **[!UICONTROL Indicateurs sur la période]** sont calculés sur la période sélectionnée :

* **[!UICONTROL Entrant (débit evt/h)]** : moyenne horaire du nombre d&#39;événements entrés dans la file Message Center.
* **[!UICONTROL Entrant (volume evt)]** : nombre d&#39;événements entrés dans la file Message Center.
* **[!UICONTROL Sortant (débit msg/h)]** : moyenne horaire du nombre d&#39;événements sortant avec succès de Message Center (envoyés par une diffusion).
* **[!UICONTROL Sortant (volume msg)]** : nombre d&#39;événements sortant avec succès de Message Center (envoyés par une diffusion).
* **[!UICONTROL Temps moyen d&#39;envoi (s)]** : temps moyen passé dans Message Center pour les événements traités avec succès. Ce calcul prend en compte le temps de traitement et le temps d&#39;envoi par les mta.
* **[!UICONTROL Taux d&#39;erreur]** : nombre d&#39;événements en erreur par rapport au nombre d&#39;événements entrés dans la file Message Center. Les erreurs suivantes sont prises en compte : erreur de routage, événement expiré (événement resté trop longtemps dans la file d&#39;attente), erreur de diffusion, ignoré par la diffusion (quarantaine, etc.).

>[!NOTE]
>
>Les seuils d&#39;avertissement (orange) et d&#39;alerte (rouge) des indicateurs sont paramétrables dans l&#39;assistant de déploiement d&#39;Adobe Campaign. Voir [Seuils de suivi](#thresholds).

### Surveillance des seuils {#thresholds}

Vous pouvez configurer les seuils d’avertissement (orange) et d’alerte (rouge) des indicateurs qui apparaissent dans la variable **Qualité de service Message Center** et **Temps traitement Message Center** rapports.

Pour ce faire, procédez comme suit :

1. Ouvrez l’assistant de déploiement dans la **instance d&#39;exécution** et accédez à la **[!UICONTROL Message Center]** page.
1. Utilisez les flèches pour modifier les seuils.

   ![](assets/mc-thresholds.png)
