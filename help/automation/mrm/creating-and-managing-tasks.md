---
product: campaign
title: Créer et gérer les tâches
description: Créer et gérer les tâches
feature: Campaigns, Resource Management
role: User
exl-id: 730d1712-53a6-4bf7-9aac-523b06bd0d0a
TQID: https://experienceleague.adobe.com/LggpejZ5h1fYPh3efYx2f7x3DEhqVlvPndjgNkNUUCs
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 3934
ht-degree: 63%

---

# Création et gestion de tâches{#creating-and-managing-tasks}

Adobe Campaign vous permet de créer des tâches et de gérer leur cycle de vie complet directement dans l’application. La mise en œuvre des programmes et des campagnes peut être découpée en tâches qui sont assignées à des opérateurs Adobe Campaign ou à des prestataires externes. Ce mode de fonctionnement permet de créer un environnement de collaboration ouvert incluant tous les participants au programme et les participants externes.

Les tâches peuvent être créées, visualisées et surveillées à partir de la liste des tâches ou du tableau de bord de la campagne. Elles peuvent également être visualisées et suivies dans les plannings du plan marketing, des programmes et des campagnes.

Les tâches sont attachées à des campagnes et peuvent avoir des dépendances, c&#39;est-à-dire des tâches associées. Chaque tâche a un statut, une priorité, une charge estimée et les coûts associés.

Toutes les tâches sont regroupées dans une liste accessible à partir de l&#39;onglet **Campagnes**. Pour plus d&#39;informations, consultez la section [Accéder aux tâches](#accessing-tasks).

Elles peuvent être affichées dans le planning du programme auquel elles appartiennent.

![](assets/campaign-calendar.png)

## Accéder aux tâches {#accessing-tasks}

### Afficher les tâches {#displaying-tasks}

Les tâches sont affichées dans la liste des tâches accessible à partir de l&#39;onglet **[!UICONTROL Campagnes]**.

![](assets/campaign-task-dashboard.png)

Vous pouvez visualiser toutes les tâches de l’opérateur ou de l’opératrice courant(e).

Pour plus d&#39;informations, voir les sections [Etat d&#39;exécution d&#39;une tâche](#execution-status-of-a-task) et [Etat d&#39;avancement d&#39;une tâche](#progress-status-of-a-task).

### Filtrer les tâches {#filtering-tasks}

Cette vue filtre automatiquement toutes les tâches afin de n’afficher que les **tâches de l’opérateur ou de l’opératrice courant(e)**. Vous pouvez également filtrer les tâches à partir des champs de la section supérieure de la fenêtre.

### Modifier les tâches {#editing-tasks}

Cliquez sur une tâche pour la modifier.

![](assets/edit-a-task.png)

## Créer une nouvelle tâche {#creating-a-new-task}

Pour créer une tâche, procédez comme suit :

1. Accédez au lien **[!UICONTROL Tâches]** dans l’onglet **[!UICONTROL Campagnes]** et cliquez sur **[!UICONTROL Créer]**.

   ![](assets/create-a-task-from-dashboard.png)

1. Saisissez le nom de la tâche, puis sélectionnez la campagne à laquelle elle est rattachée.
1. Définissez les dates de début et de fin.
1. Cliquez sur **[!UICONTROL Enregistrer]** pour créer la tâche.

   ![](assets/new-task-edit.png)

Vous pouvez également créer une tâche à partir du tableau de bord d&#39;une opération : dans ce cas, elle est automatiquement associée à l&#39;opération à partir de laquelle elle a été créée.

![](assets/add-a-task-in-a-campaign.png)

Une fois créée, la tâche est ajoutée au planning et au tableau de bord de la campagne, ainsi qu’à la liste des tâches. Pour modifier une tâche, cliquez sur son nom dans la liste des tâches ou sélectionnez-la dans le planning ou le tableau de bord de la campagne, puis cliquez sur le bouton **[!UICONTROL Ouvrir]**.

Une fois créée, vous pouvez configurer la tâche en définissant les paramètres suivants :

* Le ou la responsable et les participant(e)s. [En savoir plus](#manager-and-participants)
* Le planning de création. [En savoir plus](#execution-schedule)
* Les coûts engagés. [En savoir plus](#expenses-and-revenues)

Vous pouvez également ajouter des [validant(e)s](#reviewers) et des [documents de référence](#documents-referenced).

Le cycle de vie d’une tâche est présenté dans [cette section](#life-cycle).

### Responsable et intervenants {#manager-and-participants}

Par défaut, la tâche est assignée à l’opérateur ou à l’opératrice qui l’a créée. Une notification est envoyée à l’opérateur ou l’opératrice lorsque la tâche nécessite une action.

Vous pouvez sélectionner un autre opérateur ou une autre opératrice dans la liste déroulante **[!UICONTROL Affecté à]**.

![](assets/task-assigned-to.png)

>[!NOTE]
>
>La gestion des opérateurs et des opératrices est présentée dans cette [section](../../v8/start/gs-permissions.md).
>
>L’opérateur ou l’opératrice responsable de la tâche est la seule personne habilitée à clore la tâche.

Vous pouvez ajouter d’autres opérateurs et opératrices qui s’attelleront à la réalisation de la tâche. Ces personnes ne sont pas autorisées à clôturer la tâche ; ils peuvent seulement approuver la tâche qui leur est assignée.

Pour ajouter des opérateurs et des opératrices à la tâche, procédez comme suit :

1. Cliquez sur l’icône **[!UICONTROL Ressources]** dans la barre d’outils de la tâche.

   ![](assets/add-task-resources.png)

1. Cliquez sur **[!UICONTROL Ajouter]** et sélectionnez les opérateurs et opératrices concernés.
1. Saisissez le taux d’utilisation. Celui-ci représente la charge de travail affectée à l’opérateur ou à ’opératrice pendant la durée d’exécution de la tâche. Ce taux est donné à titre indicatif et est exprimé en pourcentage.

   ![](assets/define-operator-task-workload.png)

   Par exemple, pour une tâche dont le planning de réalisation est fixé à 10 jours, un opérateur pour lequel le taux d’utilisation est de 50 % sera mobilisé pour la moitié de son temps de travail sur la réalisation de cette tâche, pendant les 10 jours prévus.

   Pour chaque opérateur ou opératrice, vous pouvez indiquer une charge planifiée ainsi qu’une charge réalisée. Ces durées sont également fournies à titre d’information uniquement.

1. Vous pouvez configurer un rappel à partir du lien **[!UICONTROL Ajouter un rappel...]**. Une notification par e-mail sera envoyée à tous les opérateurs et opératrices impliqués dans la tâche avant sa date de fin.

   ![](assets/task-op-add-a-reminder.png)

1. Vous pouvez également envoyer une notification avant le début de la tâche. Pour configurer ce paramètre, sélectionnez la date dans le champ **[!UICONTROL Notification initiale]**.
1. Lorsque la date de fin est atteinte et que la tâche n’est pas fermée, une notification peut être envoyée à la personne désignée ou au groupe de personnes désignées sélectionné dans la liste déroulante **[!UICONTROL Assignation]**.


Le tableau de bord de l&#39;opérateur permet de consulter sa charge de travail, c&#39;est-à-dire les autres tâches.

![](assets/operator-dashboard.png)

### Validation de la tâche {#reviewers}

En plus des participant(e)s, vous pouvez définir des opérateurs et opératrices qui examineront la tâche une fois qu’elle sera fermée.

Pour ce faire, cliquez sur l’option **[!UICONTROL Activer la validation de la tâche]** dans la section inférieure de la fenêtre **[!UICONTROL Ressources]**. Il peut s’agir d’un opérateur ou d’une opératrice individuel(le), d’un groupe d’opérateurs ou d’opératrices ou d’une liste d’opérateurs ou d’opératrices.

Pour désigner une liste d’opérateurs ou d’opératrices, cliquez sur le lien **[!UICONTROL Editer...]** situé à droite du champ désignant le premier validant ou la première validante et ajoutez autant d’opérateurs et d’opératrices supplémentaires que nécessaire, comme dans l’exemple ci-dessous :

![](assets/enable-task-approval.png)

Vous pouvez définir un planning de validation pour la tâche dans la section inférieure de la fenêtre de configuration. Par défaut, les validant(e)s disposent de trois jours à partir de la date de soumission pour valider une tâche. Vous pouvez également ajouter un rappel qui sera automatiquement envoyé aux opérateurs et opératrices concernés avant la date limite de validation.

La personne responsable de la tâche peut se charger de la validation, même si d’autres opérateurs et opératrices ont déjà été assignés pour le faire. Si aucun validant n&#39;est défini, les notifications seront envoyées au responsable de la tâche. Tous les autres opérateurs et opératrices Adobe Campaign disposant des droits d’**[!UICONTROL Administrateur ou administratrice]** sont également habilités à valider la tâche. Toutefois, ils ne reçoivent pas de notifications.

### Documents référencés {#documents-referenced}

Vous pouvez ajouter des [documents et des ressources marketing](managing-marketing-resources.md) à une tâche.

Procédez comme suit :

1. Ouvrez la tâche et cliquez sur l’icône **[!UICONTROL Documents]** dans la barre d’outils de la tâche.

   ![](assets/add-documents-to-a-task.png)

1. Cliquez sur **[!UICONTROL Ajouter]** et sélectionnez le document à ajouter à votre tâche. Appliquez le même processus pour les ressources marketing.


Les documents référencés sont ajoutés aux notifications envoyées aux opérateurs impliqués dans la tâche. Ils sont également ajoutés dans le tableau de bord de la tâche.

![](assets/s_ncs_user_task_notification_documents.png)

### Planning d&#39;exécution {#execution-schedule}

La période de validité d’une tâche est indiquée dans les champs **[!UICONTROL Début]** et **[!UICONTROL Fin]**. La charge planifiée exprime la charge de travail à effectuer pendant la période. Elle est exprimée en jours ou en heures.

>[!NOTE]
>
>Le cycle de vie d&#39;une tâche est présenté dans la section [Cycle de vie](#life-cycle).

De plus, le champ **[!UICONTROL Charge réalisée]**, exprimé également en jours ou en heures, permet de mettre à jour manuellement l&#39;état d&#39;avancement de la charge de travail par rapport à la charge planifiée.

![](assets/s_ncs_user_task_percentage_done_enter.png)

L&#39;**[!UICONTROL Etat d&#39;avancement]** de la tâche, exprimé en pourcentage, est mis à jour automatiquement en fonction du travail réalisé par les différents opérateurs impliqués dans la tâche. Il peut être saisi manuellement.

Cette information est visualisable dans le tableau de bord de la tâche.

![](assets/s_ncs_user_task_percentage_done_from_dashboard.png)

Elle est également affichée dans celui de l&#39;opération.

![](assets/s_ncs_user_task_percentage_done_from_op.png)

Si la date de fin du planning de réalisation de la tâche a été atteinte et que la tâche n&#39;est pas terminée, la tâche sera **[!UICONTROL En retard]**. Un message d&#39;avertissement s&#39;affiche également pour alerter les opérateurs.

Pour plus d&#39;informations, voir la section [Etat d&#39;avancement d&#39;une tâche](#progress-status-of-a-task).

### Dépenses et revenus {#expenses-and-revenues}

Vous pouvez définir les dépenses liées et les revenus prévisionnels pour chaque tâche. Elles sont calculées puis consolidées pour l’opération à laquelle la tâche est rattachée.

Pour indiquer ces informations, cliquez sur l&#39;icône **[!UICONTROL Dépenses et revenus]** située dans la barre d&#39;outils de la tâche.

![](assets/s_ncs_user_task_edit_costs.png)

Par défaut, le budget imputé est celui de l&#39;opération à laquelle est rattachée la tâche. Elle s’affiche dans les détails de la tâche.

>[!NOTE]
>
>Pour plus d’informations sur les dépenses et les budgets, reportez-vous à [cette section](../campaigns/providers-stocks-and-budgets.md#cost-commitment--calculation-and-charging).

Dans cette fenêtre, vous pouvez également définir les objectifs à atteindre. Les objectifs sont exprimés en termes de revenus prévisionnels pour la tâche.

### Prestataires {#service-providers}

Un prestataire externe peut être impliqué dans la gestion de la tâche.

Pour cela, modifiez les propriétés de la tâche et sélectionnez le prestataire concerné. Les postes de coûts associés au prestataire sont automatiquement listés dans la section centrale de la fenêtre.

Sélectionnez les postes de coûts liés à l&#39;exécution de la tâche. Pour cela, sélectionnez le type de coût et, au besoin, ajoutez un montant à surcharger.

![](assets/s_ncs_user_task_edit_simple_costs_tab.png)

>[!NOTE]
>
>La méthode de gestion des budgets et des coûts est présentée dans la section [Maîtriser les coûts](controlling-costs.md).

Lorsqu&#39;un prestataire est sélectionné, il est affiché dans le tableau de bord de la tâche :

![](assets/s_ncs_user_task_supplier_view.png)

### Tâches en retard {#late-tasks}

Une tâche est en retard si elle a atteint sa date de fin alors qu&#39;elle n&#39;a pas le statut **[!UICONTROL Terminée]**. Par défaut, aucun opérateur n&#39;est alerté lorsqu&#39;une tâche est en retard. Vous pouvez paramétrer l&#39;envoi d&#39;un email de notification : tous les opérateurs peuvent être notifiés, même s&#39;ils ne sont pas impliqués dans la tâche.

Dans la boîte **[!UICONTROL Ressources]**, ajoutez l’opérateur au champ **[!UICONTROL Affectation]**. Pour avertir plusieurs personnes, sélectionnez un groupe d&#39;opérateurs.

![](assets/mrm_task_alert_if_late.png)

### Notifications initiales {#initial-notifications}

Lorsque vous créez ou modifiez une tâche dont la date de début se situe dans le futur, Adobe Campaign vous propose d&#39;envoyer un email au responsable de la tâche pour lui signaler le début de celle-ci.

![](assets/mrm_task_first_notif.png)

Cependant, si la tâche que vous êtes en train de créer est éloignée dans le temps, il peut être préférable de planifier l&#39;envoi de la notification avant le début de la tâche. Par exemple, si la tâche débute dans un mois, vous pouvez en avertir le responsable une semaine avant le début de la tâche.

Pour programmer une notification, dans la boîte **[!UICONTROL Ressources]**, utilisez le champ **[!UICONTROL Notification initiale]**.

![](assets/mrm_task_alert_before.png)

* Pour les tâches dans les opérations, choisissez une date et une heure précises.
* Pour les tâches dans les modèles d’opération, le moment de la notification est exprimé en temps restant avant le début de la tâche (par exemple, si vous entrez 2j dans le champ **[!UICONTROL Notification initiale]**, l’e-mail sera envoyé 2 jours avant la date début de la tâche).

Si vous avez programmé une notification, lorsque vous enregistrez la tâche, Adobe Campaign vous proposera quand même d&#39;envoyer une notification immédiatement. Vous pouvez décider de l’envoyer, mais cela ne remplacera pas la notification planifiée.

### Tâche liée à un programme {#task-linked-to-a-program}

Vous pouvez créer des tâches directement dans un programme pour gérer les actions relatives à leur organisation globale et non à une campagne spécifique (par exemple, une réunion pour discuter du thème des campagnes à venir dans le programme). La tâche apparaîtra dans le planning du programme.

Pour créer une tâche directement rattachée à un programme :

1. Ouvrez le planning du programme : sur la page d&#39;accueil, accédez à **[!UICONTROL Campagnes > Parcourir > Autres choix > Programmes]**. Le planning global du programme s’ouvre dans la section droite de la fenêtre.
1. Dans le planning, cliquez sur le programme désiré : une fenêtre décrivant le programme apparaît.
1. Dans cette fenêtre, cliquez sur **[!UICONTROL Ouvrir]**. Le planning du programme s’ouvre.
1. Cliquez sur le bouton **[!UICONTROL Ajouter]** au-dessus du planning à droite, puis cliquez sur **[!UICONTROL Ajouter une tâche]**.

![](assets/mrm_task_create_from_prg.png)

### Disponibilité des opérateurs {#operator-availability}

Dans le tableau de bord de la tâche, une icône en regard du nom de l’opérateur indique qu’il est déjà en train de travailler sur une autre tâche ou un autre événement pendant la période couverte par la tâche. La tâche dont l’opérateur est responsable ou à laquelle il participe apparaît dans le champ **[!UICONTROL Affecté à]** ou dans la zone **[!UICONTROL Ressources]** de la tâche.

![](assets/mrm_task_alert_operator_busy.png)

### Tâche dans un workflow {#task-in-a-workflow}

Utiliser un élément **[!UICONTROL Tâche]** dans un workflow d&#39;opération permet de définir deux scénarios en fonction de si la tâche est validée ou non.

![](assets/mrm_task_in_workflow.png)

Dans les workflows d&#39;opération, l&#39;activité **[!UICONTROL Tâche]** se trouve dans l&#39;onglet **[!UICONTROL Ordonnancement]**.

## Types de tâches {#types-of-task}

Lorsque vous créez des tâches à partir d&#39;une campagne, vous pouvez créer des tâches spécifiques. Le type de tâche est défini dans le modèle sélectionné.

![](assets/s_ncs_user_task_select_template.png)

Les tâches suivantes peuvent être planifiées :

* [Tâche de contrôle](#control-tasks),
* [Tâche de groupement](#grouping-task),
* [Tâche de groupement](#grouping-task),
* [Tâche de notification](#notification-task).

>[!NOTE]
>
>Les tâches de type **[!UICONTROL Tâche de contrôle]** et **[!UICONTROL Tâche de groupement]** ne peuvent être créées **que** depuis le tableau de bord de l&#39;opération.\
>Elles sont affichées dans la vue d&#39;ensemble des tâches de l&#39;opérateur auquel elles sont assignées. Voir [Accéder aux tâches](#accessing-tasks).

### Tâche de contrôle {#control-tasks}

Une tâche de type **[!UICONTROL Tâche de contrôle]** est attachée à la validation d&#39;une diffusion : validation du ciblage, du contenu, du fichier d&#39;extraction, du budget ou du BAT.

![](assets/s_ncs_user_task_new_control.png)

Une fois créée, la tâche est ajoutée dans le tableau de bord de l&#39;opération.

![](assets/s_ncs_user_task_edit_from_board.png)

Vous pouvez alors l&#39;éditer et en préciser les paramètres.

### Tâche de création de ressource marketing {#marketing-resource-creation-task}

Une tâche de création de ressource marketing peut être utilisée pour gérer la création et la publication d’une ressource marketing. Si vous gérez une ressource via une tâche et non via la ressource elle-même, vous pouvez :

* Piloter le processus de création de la ressource à partir d&#39;une opération.
* Visualiser le processus de création de la ressource dans un planning.
* Maîtriser le planning de création de la ressource (rappels, notifications).
* Comptabiliser et contrôler les coûts liés à l&#39;élaboration de la ressource.
* Valider et publier la ressource via la tâche (si l&#39;option correspondante est activée).

#### Interaction entre la tâche et sa ressource associée {#interaction-between-the-task-and-its-linked-resource}

La tâche de création d&#39;une ressource marketing interagit avec la ressource qui lui est associée. Cela signifie :

* Le planning d&#39;élaboration de la ressource et les coûts liés à celle-ci sont gérés via la tâche.
* Les opérateurs peuvent travailler normalement sur la ressource (télécharger le fichier vers ou depuis le serveur, verrouiller et déverrouiller la ressource) : cela n&#39;a pas d&#39;incidence sur la tâche.
* La validation et la publication de la ressource peuvent être faites via la tâche : si l&#39;option **[!UICONTROL Publier la ressource marketing]** est activée, la ressource est automatiquement validée et publiée lorsque la tâche est terminée. Si cette option n&#39;est pas activée, il n&#39;y a pas d&#39;interaction entre la tâche et la ressource : une action effectuée dans l&#39;une n&#39;aura aucune incidence sur l&#39;autre.

  Vous pouvez utiliser une série de tâches liées pour définir un cycle de validation complet. Cochez l’option **[!UICONTROL Publier la ressource marketing]** uniquement pour la dernière tâche : toutes les tâches doivent être terminées avant la publication de la ressource. De plus, lorsque vous créez une tâche de ressource marketing enfant, la ressource est automatiquement sélectionnée dans la tâche enfant.

   * **Via la ressource** : si vous soumettez la ressource à validation ou la validez, ces actions n&#39;auront aucun effet sur la tâche.
   * **Via la tâche** : si l&#39;option **[!UICONTROL Publier la ressource marketing]** est cochée dans la tâche, la ressource est automatiquement validée et publiée lorsque la tâche est terminée (voir ci-dessus). Si cette option n&#39;est pas cochée, il n&#39;y a pas d&#39;interaction entre la tâche et la ressource : une action effectuée dans l&#39;une n&#39;aura aucune incidence sur l&#39;autre.

#### Paramétrer une tâche de création de ressource marketing {#configuring-a-marketing-resource-creation-task}

La personne qui vérifie la tâche n’est pas nécessairement la même personne que celle qui vérifie le contenu défini dans la ressource. Cependant, si l’option **[!UICONTROL Publier la ressource marketing]** est cochée (voir ci-dessous), la personne chargée de la révision de la tâche est autorisée à valider le contenu de la ressource, puisque terminer la tâche valide automatiquement la ressource (ou, si aucune personne n’est définie pour réviser la tâche, la personne responsable de la tâche).

![](assets/mrm_task_asset_creation.png)

Dans le champ **[!UICONTROL Ressource marketing]**, définissez la ressource que vous souhaitez gérer via cette tâche. Vous pouvez ainsi :

* Sélectionner une ressource existante : la liste déroulante propose toutes les ressources dont le statut est **[!UICONTROL En édition]**.
* Créer une ressource : cliquez sur l&#39;icône **[!UICONTROL Choisir le lien]**, puis sur l&#39;icône **[!UICONTROL Créer]**.

L&#39;option **[!UICONTROL Publier la ressource marketing]** permet d&#39;automatiser la publication d&#39;une ressource : lorsque la tâche est **[!UICONTROL Terminée]**, l&#39;état de la ressource passe automatiquement à **[!UICONTROL Publiée]**, même si elle n&#39;avait pas été soumise à validation ni validée,y compris si le validant qui termine la tâche n&#39;est pas le validant de contenu défini dans la ressource.

Le bouton **[!UICONTROL Publier la ressource]** est rendu disponible et le réviseur de la publication de la ressource reçoit une notification par e-mail pour l’informer qu’elle est prête à être publiée. Sous l’onglet **[!UICONTROL Modifier > Tracking]**, les options de révision et de publication par le réviseur de la tâche deviennent visibles. Si un workflow de post-traitement des ressources a été défini, il est exécuté maintenant.

![](assets/mrm_resource_audit_tab.png)

### Tâche de groupement {#grouping-task}

La tâche de type **[!UICONTROL Tâche de groupement]** permet de regrouper plusieurs tâches et de synchroniser la gestion de leur état d&#39;avancement et de leur validation.

Les tâches de groupement n&#39;ont ni dépenses ni ressources associées.

Toutes les tâches regroupées pour une tâche de regroupement sont visibles dans son propre tableau de bord. Vous pouvez ainsi filtrer la liste des tâches pour n’afficher que celles qui vous intéressent.

Les tâches de groupement comprennent un lien permettant de créer rapidement une tâche groupée.

Pour créer une tâche groupée à partir d&#39;une tâche de groupement, dans le tableau de bord de l&#39;opération, cliquez sur le nom de la tâche de groupement pour afficher sa description, puis cliquez sur **[!UICONTROL Ajouter une tâche]**.

![](assets/mrm_task_grouped_create.png)

Cependant, si vous avez déjà créé une tâche que vous voulez rattacher à une tâche de groupement, vous pouvez toujours le faire via le champ **[!UICONTROL Regroupé à]** de la boîte **[!UICONTROL Propriétés]** de la tâche à grouper.

![](assets/s_ncs_user_task_group_with.png)

### Tâche de notification {#notification-task}

Les tâches de notification permettent de planifier l&#39;envoi d&#39;emails (à un opérateur, un groupe d&#39;opérateurs, un prestataire, etc.). Vous pouvez ainsi planifier des rappels, par exemple pour informer une personne qu’une campagne se termine bientôt, ou pour envoyer des documents avant le début d’une campagne afin que les opérateurs puissent la préparer. Vous pouvez ainsi suivre vos communications au sein de votre campagne ou programme et avoir un œil plus attentif sur les actions réalisées.

#### Cycle de vie {#life-cycle}

Les tâches de notification ne nécessitent pas d’approbation. Cela signifie que leur cycle de vie est plus simple que celui d&#39;une tâche standard :

![](assets/mrm_task_notif_lifecycle.png)

Une tâche de notification peut avoir les états suivants :

* **[!UICONTROL Planifiée]** tant que l&#39;email n&#39;a pas été envoyé
* **[!UICONTROL En cours]** une fois que l&#39;email a été envoyé mais la date de fin n&#39;est pas atteinte
* **[!UICONTROL Terminée]** une fois que la date de fin est atteinte.

#### Configuration {#configuration}

![](assets/mrm_task_notif_dashboard.png)

Lors de sa création, les éléments suivants doivent être renseignés dans la tâche :

* **[!UICONTROL Affecté à]** : l&#39;opérateur ou le groupe d&#39;opérateurs/opératrices qui recevra l&#39;email. Si vous réaffectez la tâche une fois l&#39;email envoyé, l&#39;email ne sera pas envoyé au nouvel opérateur (pour cela, vous devez réinitialiser la tâche et modifier sa date de début).
* **Date de début de la tâche** : date à laquelle l’e-mail de notification sera envoyé. Cette date doit avoir lieu ultérieurement au moment de l&#39;enregistrement de la tâche.
* **Date de fin de la tâche** : date à laquelle la tâche prend le statut **[!UICONTROL Terminé]**. Par défaut, la date de fin est identique à la date de début. Cependant, donner une durée à la tâche permet, si besoin, de symboliser dans le planning le temps dont dispose l&#39;opérateur pour agir.
* **[!UICONTROL Description]** : le texte saisi ici apparaîtra dans le corps de l’e-mail de notification.

  ![](assets/mrm_task_notif_dashboard_msg.png)

Vous pouvez ajouter une pièce jointe à la tâche et à l’e-mail de notification. Pour ce faire, cliquez sur l’icône **[!UICONTROL Documents]** dans la barre d’outils située dans le coin supérieur droit.

## Cycle de vie {#life-cycle-1}

### Liens entre les tâches {#links-between-tasks}

Le bouton **[!UICONTROL Propriétés]** de chaque tâche permet de définir les liens entre les tâches d&#39;une campagne. Il est possible de fractionner ces tâches en sous-tâches à l&#39;aide d&#39;un regroupement (voir la section [Tâches liées](#linked-tasks)) ou de définir des dépendances entre les tâches (voir la section[Tâches de groupement](#grouping-tasks)).

#### Tâches liées {#linked-tasks}

Utilisez le champ **[!UICONTROL Tâche liée]** pour associer des tâches à une tâche de groupement. Pour plus d&#39;informations, consultez la section [Types de tâches](#types-of-task).

Dans l&#39;exemple suivant, la validation des ciblages est découpée en quatre sous-tâches.

![](assets/s_ncs_user_task_linked_tasks.png)

Chaque sous-tâche est une tâche standard, liée à la tâche principale.

![](assets/s_ncs_user_task_depends_on.png)

#### Tâches de groupement {#grouping-tasks}

Utilisez le champ **[!UICONTROL Regroupé à]** pour faire dépendre la réalisation d&#39;une tâche de la réalisation d&#39;une autre tâche.

![](assets/s_ncs_user_task_group_with.png)

La dépendance entre les tâches est matérialisée par des flèches dans le tableau de bord de l&#39;opération.

![](assets/s_ncs_user_task_dependencies_from_board.png)

Dans le cas de tâches groupées, Adobe Campaign attribue automatiquement la date de fin de la tâche parent comme date de début de la tâche enfant. Par exemple, si une tâche **Créer une invitation** se termine le 15 octobre à 3:30PM, la tâche enfant **Envoyer un e-mail d&#39;invitation** démarrera le 15 octobre à 3:30PM.

De plus, si vous retardez la fin d&#39;une tâche parent, certaines de ses tâches enfants peuvent être décalées : il s&#39;agit des tâches enfants dont le statut est **[!UICONTROL Planifié]** et dont la date de début est antérieure à la nouvelle date de fin de la tâche parent. La durée de la tâche reste la même. Si la date de début d&#39;une tâche enfant est postérieure à la nouvelle date de fin de la tâche parent, la tâche enfant n&#39;est pas affectée.

**Exemple**

Une tâche parent planifiée pour finir le mardi 9 octobre à 17h a 2 tâches enfants, la tâche A et la tâche B. La tâche A est planifiée pour commencer le 10 octobre à 14h et la tâche B, planifiée pour commencer le 12 octobre à 8h.

Reportons la tâche parent : elle se termine maintenant le 11 octobre à 13h. Seule la tâche A est reportée et démarrera le 11 octobre à 13h.

![](assets/mrm_task_parent_postpones_child.png)

### Statut d&#39;exécution d&#39;une tâche {#execution-status-of-a-task}

Les statuts des tâches peuvent être affichés dans la vue d’ensemble des tâches. Le statut de réalisation d&#39;une tâche est mis à jour automatiquement en fonction des actions des opérateurs.

Une tâche peut être : **[!UICONTROL Planifiée]**, **[!UICONTROL En cours]**, **[!UICONTROL Terminée]**, **[!UICONTROL Annulée]**, **[!UICONTROL En attente de validation]** ou **[!UICONTROL Refusée]**.

* A sa création, une tâche est **[!UICONTROL Planifiée]** si sa date de début se situe dans le futur. Il conserve ce statut jusqu’à ce que sa date de début soit atteinte.
* Une fois qu’elle a été lancée, la tâche est **[!UICONTROL En cours]**. Lorsque la personne responsable de la tâche la ferme, elle passe à **[!UICONTROL Terminé]**.
* Si une personne chargée de la révision a été définie, la tâche est **[!UICONTROL En attente de validation]** entre le moment où la personne responsable la clôt et le moment où la personne chargée de la révision la valide. Si le réviseur ou la réviseuse la refuse, la tâche aura le statut **[!UICONTROL Refusé]**.
* Une tâche peut être annulée par son responsable depuis le tableau de bord ou à partir de la **[!UICONTROL Vue d&#39;ensemble des tâches]** en cliquant sur le bouton **[!UICONTROL Annuler]**.
* Pour planifier une tâche, saisissez une date de début dans le futur. Vous pouvez ensuite envoyer une première notification aux opérateurs Adobe Campaign impliqués dans l&#39;exécution de la tâche. Voir à ce sujet la section [Cycle de vie complet d&#39;une tâche](#complete-task-life-cycle).

>[!NOTE]
>
>* Le statut de la tâche est mis à jour automatiquement.
>* Même si la période de validité est terminée, les tâches qui n’ont pas été fermées apparaissent toujours dans la liste des tâches en cours. Un avertissement est affiché pour alerter les opérateurs que la tâche est en retard.
>

### Statut d&#39;avancement d&#39;une tâche {#progress-status-of-a-task}

En plus de son statut d&#39;exécution, une tâche peut être associée à un statut d&#39;avancement : **[!UICONTROL En retard]**, **[!UICONTROL A valider]**, **[!UICONTROL A faire aujourd&#39;hui]** ou **[!UICONTROL A faire cette semaine]**. Ces informations sont automatiquement renseignées en fonction du planning de la tâche.

Vous pouvez filtrer la liste des tâches par Statut de réalisation de la tâche ou Etat d&#39;avancement de la tâche.

Pour plus d&#39;informations, consultez la section [Accéder aux tâches](#accessing-tasks).

### Cycle de vie complet d&#39;une tâche {#complete-task-life-cycle}

Voici les différentes étapes du cycle de vie complet d&#39;une tâche pour laquelle le responsable a défini des intervenants et des validants.

1. Le responsable crée la tâche et renseigne les différents champs. Pour plus d&#39;informations, consultez la section [Créer une nouvelle tâche](#creating-a-new-task).

   Lors de la création, et à chaque modification d&#39;une tâche **planifiée dans le futur** (tant que la date de début de la tâche n&#39;a pas été atteinte), vous avez la possibilité d&#39;envoyer un email de notification aux intervenants ainsi qu&#39;au responsable, les informant qu&#39;une nouvelle tâche a été planifiée.

   ![](assets/s_ncs_user_task_planed_send_message.png)

   Pour envoyer cette première notification, cliquez sur **[!UICONTROL Oui]**. Cette notification leur indique la tâche suivante et inclut des détails sur le contenu et le nombre de jours restants avant son échéance.

   A la création d&#39;une tâche planifiée dans le futur, celle-ci passe à l&#39;état **[!UICONTROL Planifiée]**.

1. À la date de début de la tâche, la personne responsable et les intervenantes et intervenants reçoivent un e-mail de notification les informant que la tâche a commencé. La tâche passe au statut **[!UICONTROL En cours]**.
1. Lorsqu&#39;un intervenant a terminé la partie qui lui a été assignée, il valide la tâche, au choix :

   * à partir de l&#39;email de notification.
   * à partir de la console ou de l’interface web, au niveau du tableau de bord de la tâche.

     ![](assets/s_ncs_user_task_start_rea.png)

1. À chaque validation d’un intervenant ou d’une intervenante, le statut de progression du traitement est mis à jour.

   ![](assets/s_ncs_user_task_percentage_done_op.png)

1. Le réviseur reçoit un e-mail de notification l’informant que l’opérateur a terminé la partie qui lui a été assignée.

   Cette personne peut suivre la progression dans le tableau de bord de la tâche.

   ![](assets/s_ncs_user_task_follow_from_dashboard.png)

1. Lorsqu’il ou elle estime que la tâche est terminée, le ou la responsable peut alors la clore de différentes manières : en cliquant sur le lien dans l’e-mail de notification envoyé à la date de début de la tâche, à partir de la console cliente ou dans l’interface web.

   ![](assets/s_ncs_user_task_console_ressource_validation.png)

   >[!NOTE]
   >
   >Le responsable peut clore la tâche à tout moment, même en l&#39;absence d&#39;approbation. Le statut de progression passe automatiquement à 100 %.

1. La tâche passe alors à l&#39;état **[!UICONTROL A valider]**, et un email de notification est envoyé au validant.

   Il ou elle approuve la tâche à partir de l’e-mail de notification, de la console cliente ou de l’interface web.

   Il peut agir depuis le tableau de bord de l&#39;opération :

   ![](assets/s_ncs_user_task_console_validation.png)

   Il peut également utiliser le bouton de validation de la tâche :

   ![](assets/s_ncs_user_task__validation.png)

   >[!NOTE]
   >
   >La tâche ne passe à l&#39;état **[!UICONTROL A valider]** que si vous avez activé l&#39;option **[!UICONTROL Activer la validation de la tâche]** dans la fenêtre des **[!UICONTROL Ressources]** de la tâche.\
   >Si le validant refuse la tâche, elle passe alors à l&#39;état **[!UICONTROL Refusée]**, et le cycle de vie de la tâche recommence automatiquement.

1. Le statut de la tâche passe à **[!UICONTROL Terminé]**. Une notification est envoyée à toutes les personnes impliquées.

   >[!NOTE]
   >
   >Une fois la tâche terminée, son cycle de vie peut être réinitialisé par la personne responsable. Pour ce faire, ouvrez la tâche et cliquez sur le lien **[!UICONTROL Réinitialiser la tâche pour l’exécuter à nouveau...]** au bas du tableau de bord.
