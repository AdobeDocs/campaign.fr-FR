---
title: Accéder aux logs de tracking
description: Découvrez comment accéder aux logs de tracking et comment les interpréter.
feature: Monitoring
role: User
level: Beginner
exl-id: df494786-5950-4646-aa9c-4dde45845057
source-git-commit: 5b23be4cb8f0896d2482e525e416713b1a6c4514
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 18%

---

# Accéder aux logs de tracking {#accessing-the-tracking-logs}

Une fois la diffusion envoyée et le tracking activé, le workflow technique **[!UICONTROL Tracking]** est chargé de récupérer les informations de tracking. Par défaut, il s&#39;exécute toutes les heures.

## Affichage du suivi dans les profils de destinataires {#recipient-tracking}

Ces informations sont remontées dans l&#39;onglet **[!UICONTROL Tracking]** du profil des destinataires ciblés par la diffusion, comme dans l&#39;exemple suivant :

![](assets/s_ncs_user_select_tracking_tab_from_recipient.png)

Cet onglet affiche toutes les URL trackées et sur lesquelles le destinataire a cliqué, notamment :

* URL sur laquelle l’utilisateur a cliqué
* Date et heure du clic
* Diffusion dans laquelle l’URL a été trouvée
* Toute autre information de suivi pertinente

Vous pouvez filtrer et trier ces informations pour analyser le comportement des destinataires et identifier les modèles d’engagement.

## Affichage du tracking dans les diffusions {#delivery-tracking}

Les informations de tracking sont également accessibles à partir de l&#39;onglet **[!UICONTROL Tracking]** de la diffusion.

![](assets/s_ncs_user_select_tracking_tab_from_del.png)

Dans cet onglet, vous pouvez afficher :

* **[!UICONTROL Statistiques de tracking]** : donne un aperçu des ouvertures, clics et autres événements de tracking
* **[!UICONTROL URL et flux de clics]** : indique les liens sur lesquels l’utilisateur a cliqué et le nombre de fois qu’il a cliqué
* **[!UICONTROL Position des clics]** : affiche une représentation visuelle de l’emplacement où les destinataires ont cliqué dans votre message
* **[!UICONTROL Logs de tracking]** : fournit des enregistrements de tracking individuels détaillés

## Dépannage du tracking {#troubleshooting}

>[!NOTE]
>
>Si l’onglet **[!UICONTROL Tracking]** d’une diffusion n’est pas visible, cela signifie que le tracking n’a pas été activé. Reportez-vous à [cette section](tracked-links.md) pour savoir comment configurer le tracking.

### Vérifier le workflow technique Tracking {#check-tracking-workflow}

Le workflow technique de Tracking doit être en cours d’exécution pour collecter les données de tracking. Le workflow technique de Tracking est disponible dans le dossier **[!UICONTROL Administration > Exploitation > Workflows techniques]**.

Pour vérifier le workflow :

1. Ouvrez le workflow **[!UICONTROL Tracking]**
1. Vérifier la date de dernière exécution
1. Vérifiez qu’il n’y a aucune erreur dans les logs de workflow.

Si le workflow n’est pas en cours d’exécution ou présente des erreurs, contactez votre administrateur ou administratrice système.

## Vérifier la collecte des données de tracking

Après avoir envoyé une diffusion dont le tracking est activé :

1. Attendez que le workflow Tracking s’exécute (par défaut, toutes les heures)
1. Ouvrez la diffusion et accédez à l&#39;onglet **[!UICONTROL Tracking]**
1. Vérifier l’affichage des données de tracking
1. Si aucune donnée n’apparaît, vérifiez que :
   * Le tracking a été activé dans les paramètres de la diffusion
   * Le workflow technique de tracking est en cours d’exécution
   * Les destinataires ont ouvert l’e-mail et cliqué sur les liens

## Rubriques connexes {#related-topics}

* [Découvrez comment configurer des liens suivis](tracked-links.md)
* [Découvrez comment tester le tracking.](testing-tracking.md)
* [Présentation des rapports de suivi](../reporting/delivery-reports.md#tracking-indicators)

