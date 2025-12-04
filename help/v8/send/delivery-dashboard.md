---
title: Surveiller vos diffusions dans l’interface utilisateur de Campaign
description: Découvrez comment accéder à la liste des diffusions et utiliser le tableau de bord des diffusions pour surveiller vos diffusions
feature: Monitoring
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '1200'
ht-degree: 70%

---

# Surveiller vos diffusions dans l’interface utilisateur de Campaign {#delivery-dashboard}

La surveillance de vos diffusions est essentielle pour vous assurer que vos campagnes sont efficaces et atteignent vos clients. Adobe Campaign met à votre disposition des outils pour accéder à vos diffusions et surveiller leurs performances via la liste des diffusions et le tableau de bord des diffusions.

## Accéder à la liste des diffusions {#list-of-deliveries}

Vous pouvez accéder aux diffusions à partir de la liste des diffusions accessible depuis le nœud **[!UICONTROL Gestion de campagne > Diffusions]** de l&#39;arborescence.

![](assets/deliveries-list.png)

Par défaut, la liste des diffusions affiche les noms et états des diffusions créées dans le nœud sélectionné. Elle affiche également le nombre de messages à envoyer, traités et envoyés avec succès.

* Le nombre de **[!UICONTROL messages à envoyer]** correspond au nombre de destinataires ciblés après analyse de la diffusion et avant envoi.
* Le nombre de messages de la colonne **[!UICONTROL succès]** correspond au nombre de messages émis par le serveur et bien reçus par le destinataire.
* Le nombre de messages **[!UICONTROL traités]** correspond au nombre de messages reçus avec succès auquel s’ajoute le nombre de messages en erreur.

>[!NOTE]
>
>Pour les diffusions volumineuses, vous pouvez mettre à jour ces valeurs. Pour cela, sélectionnez la diffusion concernée et cliquez ensuite avec le bouton droit de la souris. Sélectionnez **[!UICONTROL Action > Recalculer les indicateurs de diffusion et de tracking]** et utilisez ensuite l’assistant pour mettre à jour ces informations.

## Présentation du tableau de bord des diffusions {#delivery-dashboard-overview}

Le **tableau de bord de la diffusion** est la clé pour suivre les diffusions et les erreurs éventuelles rencontrées lors de l&#39;envoi des messages.

Il vous permet de récupérer des informations sur une diffusion et de les modifier si nécessaire. Veuillez noter que le contenu de ces onglets n&#39;est plus modifiable lorsque la diffusion a été envoyée.

Vous trouverez ci-dessous les informations à surveiller à l&#39;aide des différents onglets disponibles dans le tableau de bord :

* [Synthèse des diffusions](#delivery-summary)
* [Rapports sur les diffusions](#delivery-reports)
* [Logs de diffusion, pages miroir, exclusions](#delivery-logs-and-history)
* [Logs et historique de tracking des diffusions](#tracking-logs)
* [Rendu des diffusions](#delivery-rendering)
* [Suivi de la diffusion](#delivery-audit-)

![](assets/s_ncs_user_del_details.png)

**Rubriques connexes :**

* [Comprendre les diffusions en échec](delivery-failures.md)
* [Gestion des quarantaines](quarantines.md)
* [Bonnes pratiques relatives à la diffusion](../start/delivery-best-practices.md)
* [Gestion de la délivrabilité](about-deliverability.md)

## Synthèse des diffusions {#delivery-summary}

L&#39;onglet **[!UICONTROL Résumé]** contient les caractéristiques de la diffusion : état de la diffusion, canal utilisé, informations sur l&#39;expéditeur, objet, informations relatives à l&#39;exécution.

## Rapports sur les diffusions {#delivery-reports}

Le lien **[!UICONTROL Rapports]**, accessible à partir de l&#39;onglet **[!UICONTROL Résumé]**, vous permet de consulter un ensemble de rapports liés à la dernière diffusion : rapport général de diffusion, rapport détaillé, rapport de diffusion, distribution des messages en échec, taux d&#39;ouverture, clics et transactions, etc.

Le contenu de cet onglet peut être configuré en fonction de vos besoins. Pour plus d’informations sur les rapports de la diffusion, consultez [cette section](../reporting/delivery-reports.md).

![](assets/delivery-report.png)

## Logs, historique et exclusions de diffusion {#delivery-logs-and-history}

L&#39;onglet **[!UICONTROL Diffusion]** propose un historique des occurrences de cette diffusion. Il contient les logs de diffusion, c&#39;est-à-dire la liste des messages envoyés et leur statut. Il permet de visualiser l&#39;état de la diffusion pour chaque destinataire et les messages associés.

Pour une diffusion, vous pouvez afficher par exemple seulement les destinataires pour lesquels l&#39;envoi a échoué ou ceux dont l&#39;adresse est en quarantaine. Pour cela, cliquez sur le bouton **[!UICONTROL Filtres]** et choisissez **[!UICONTROL Par Statut]**. Sélectionnez ensuite le statut dans la liste déroulante affichée au-dessus de la liste. Différents statuts sont répertoriés dans la page [statuts de diffusion](delivery-statuses.md).

>[!NOTE]
>
>La liste des logs de diffusion peut être personnalisée, comme toute liste dans Campaign. Vous pouvez, par exemple, ajouter une colonne pour connaître l&#39;adresse IP qui a envoyé chaque email dans une diffusion. La configuration de l&#39;affichage des listes est présentée dans [cette section](../config/ui-settings.md#customize-lists).

![](assets/s_ncs_user_delivery_delivery_tab.png)

Le lien **[!UICONTROL Afficher la page miroir de ce message...]** vous permet d&#39;afficher la page miroir du contenu de la diffusion sélectionnée dans la liste dans une nouvelle fenêtre.

La page miroir est disponible uniquement pour les diffusions pour lesquelles un contenu HTML a été défini. Pour plus d&#39;informations, consultez la section [&#x200B; Lien vers la page miroir &#x200B;](mirror-page.md).

![](assets/s_ncs_user_wizard_miror_page_link.png)

## Logs et historique de tracking des diffusions {#tracking-logs}

L’onglet **[!UICONTROL Tracking]** liste l’historique du tracking pour cette diffusion. Cet onglet affiche les données de tracking des messages envoyés, à savoir toutes les URL qui ont fait l’objet d’un tracking par Adobe Campaign. Les données de tracking sont mises à jour toutes les heures.

>[!NOTE]
>
>Si le tracking n’est pas activé pour une diffusion, cet onglet n’est pas affiché.

La configuration du suivi est effectué dans l’assistant de diffusion, à l’étape concernée. Voir à ce sujet la section [Comment configurer des liens suivis](tracking.md).

Les données de **[!UICONTROL tracking]** sont interprétées dans les rapports de diffusion. Consultez [cette section](../reporting/delivery-reports.md).

![](assets/s_ncs_user_delivery_tracking_tab.png)

## Rendu de la boîte de réception {#delivery-rendering}

L&#39;onglet **[!UICONTROL Inbox rendering]** permet de prévisualiser le message dans les différents contextes dans lesquels il peut être reçu et de vérifier la compatibilité auprès des principaux ordinateurs de bureau et applications.

Ainsi, vous pouvez vérifier que l&#39;affichage de votre message sera optimal pour les destinataires sur divers clients web, webmails et appareils.

Voir à ce propos [cette section](inbox-rendering.md).


## Suivi de la diffusion {#delivery-audit-}

L&#39;onglet **[!UICONTROL Audit]** contient le log des diffusions et tous les messages concernant les BAT.

Le bouton **[!UICONTROL Actualiser]** permet de mettre à jour les données. Utilisez le bouton **[!UICONTROL Filtres]** pour définir un filtre sur les données.

Des icônes spécifiques permettent de repérer les erreurs ou avertissements. Voir [Analyse de la diffusion](delivery-analysis.md).

Le sous-onglet **[!UICONTROL BAT]** vous permet de voir la liste des BAT qui ont été envoyés.

![](assets/s_ncs_user_delivery_log_tab.png)

Vous pouvez modifier les informations affichées dans cette fenêtre (ainsi que celles des onglets **[!UICONTROL Diffusion]** et **[!UICONTROL Tracking]**) en sélectionnant les colonnes à afficher. Pour cela, cliquez sur l&#39;icône **[!UICONTROL Configurer la liste]**, située en bas à droite. La configuration de l&#39;affichage des listes est présentée dans [cette section](../config/ui-settings.md#customize-lists).

## Synchronisation du tableau de bord des diffusions {#delivery-dashboard-synchronization}

Dans le tableau de bord des diffusions, vous souhaitez vérifier les messages traités et les logs de diffusion pour vous assurer que la diffusion a bien été envoyée.

Certains indicateurs ou statuts peuvent être incorrects ou ne pas être à jour. Ce problème peut être résolu à l&#39;aide des solutions suivantes :

* Si le statut de votre diffusion est incorrect, vérifiez que toutes les validations nécessaires ont été effectuées pour cette diffusion ou que les workflows techniques **[!UICONTROL operationMgt]** et **[!UICONTROL deliveryMgt]** s&#39;exécutent sans erreur.

* Si le compteur de diffusions ne correspond pas à votre diffusion, essayez de recalculer les indicateurs en procédant comme suit : cliquez avec le bouton droit sur la diffusion en question dans l&#39;explorateur Adobe Campaign et sélectionnez **[!UICONTROL Actions]** > **[!UICONTROL Recalculer les indicateurs d&#39;envoi et de tracking]** pour effectuer une nouvelle synchronisation. Pour plus d’informations sur les indicateurs de tracking, voir cette [section](../reporting/delivery-reports.md#tracking-indicators).

Vous pouvez également effectuer un tracking de vos diffusions à l&#39;aide de différents rapports dans le tableau de bord des diffusions. Pour plus d’informations à ce sujet, consultez cette [section](../reporting/delivery-reports.md).

>[!NOTE]
>
>En tant qu&#39;utilisateur de Campaign v8 Managed Cloud Services, l&#39;infrastructure est surveillée et gérée par Adobe. Si vous rencontrez des problèmes persistants avec les indicateurs de diffusion ou la synchronisation des tableaux de bord, contactez l’Assistance clientèle d’Adobe.

## Résolution des problèmes de lenteur des diffusions {#troubleshooting-slow-deliveries}

Si votre diffusion semble prendre plus de temps que d&#39;habitude après avoir cliqué sur le bouton **[!UICONTROL Envoyer]**, vérifiez les causes potentielles suivantes :

### Problèmes de réputation des adresses IP

Certains fournisseurs de messagerie ont peut-être ajouté vos adresses IP à une liste bloquée. Vérifiez vos logs de diffusion (broadlogs) dans l’onglet **[!UICONTROL Diffusion]** pour détecter les messages rebonds indiquant des problèmes de réputation. Consultez la section [supervision de la délivrabilité](monitoring-deliverability.md) pour obtenir des conseils sur la gestion de la réputation.

### Taille et complexité de la diffusion

Votre diffusion peut être trop volumineuse pour être traitée rapidement. Cela peut se produire avec :

Une personnalisation JavaScript lourde qui nécessite un traitement des données important pour chaque destinataire.

Diffusion pesant plus de 60 kilo-octets en raison d’un contenu HTML volumineux, d’images incorporées ou d’une personnalisation poussée.

Pour en savoir plus sur les directives relatives au contenu et les bonnes pratiques de personnalisation, voir [Bonnes pratiques de diffusion](../start/delivery-best-practices.md). La taille maximale recommandée est d’environ 35 Ko pour des performances optimales.

### Performances du système

Des problèmes système peuvent empêcher les serveurs de traiter efficacement les diffusions. Si vous suspectez des problèmes de performances, recherchez des erreurs de délai d’expiration ou des problèmes de communication dans les logs de diffusion.

>[!NOTE]
>
>En tant qu’utilisateur de Campaign v8 Managed Cloud Services, la surveillance de l’infrastructure serveur est gérée par Adobe. Si vous rencontrez des problèmes de performances persistants lors de l’envoi de la diffusion, contactez l’Assistance clientèle d’Adobe avec vos logs de diffusion.

