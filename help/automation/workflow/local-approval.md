---
product: campaign
title: Validation en local
description: Validation en local
feature: Workflows, Approvals
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 172b6827-ddfc-4c6e-87c9-eb49e73ab3ab
TQID: 'https://experienceleague.adobe.com/wVcQzhDcvinh3rooWklkMsf-KQvWepqYcgcgrHlbdXg'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: ce296ecd-3d06-45ab-83c3-37214e8ce31c
    internal-label: Approvals
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 100%
---
# Validation en local{#local-approval}

Intégrée à un workflow de ciblage, l&#39;activité **[!UICONTROL Validation en local]** permet de mettre en place un processus de validation des destinataires avant l&#39;envoi d&#39;une diffusion.

![](assets/local_validation_0.png)

>[!CAUTION]
>
>Pour utiliser cette activité, vous devez avoir acquis le module Marketing distribué, qui est une option de Campaign. Veuillez vérifier votre contrat de licence.

Pour un exemple de l’activité **[!UICONTROL Validation en local]** avec un modèle de distribution, consultez la section [Utiliser l’activité Validation en local](local-approval-activity.md).

Renseignez tout d&#39;abord libellé de l&#39;activité et le champ **[!UICONTROL Action à effectuer]** :

![](assets/local_validation_1.png)

* Sélectionnez l&#39;option **[!UICONTROL Notification pour la validation de la cible]** pour envoyer un email de notification aux responsables locaux, avant la diffusion, afin qu&#39;ils valident les destinataires qui leur sont assignés.

* **Requête incrémentale** : permet d&#39;effectuer une requête et d&#39;en planifier l&#39;exécution. Pour plus d&#39;informations, consultez la section [Requête incrémentale](incremental-query.md).

  ![](assets/local_validation_intro_3.png)

## Notification pour la validation de la cible {#target-approval-notification}

Dans ce cas, l&#39;activité **[!UICONTROL Validation en local]** se place entre le ciblage en amont et la diffusion :

![](assets/local_validation_2.png)

Les champs à renseigner dans le cas d&#39;une notification pour la validation de la cible sont les suivants :

![](assets/local_validation_3.png)

* **[!UICONTROL Contexte de distribution]** : sélectionnez l’option **[!UICONTROL Spécifié dans la transition]** si vous utilisez une activité de type **[!UICONTROL Partage]** pour limiter la population ciblée. Dans ce cas, le modèle de répartition est renseigné dans l’activité de partage. Si vous ne limitez pas la population ciblée, sélectionnez ici l’option **[!UICONTROL Explicite]** et renseignez le modèle de répartition dans le champ **[!UICONTROL Répartition des données]**.

  Pour plus d’informations sur la création d’un modèle de distribution de données, voir [Limiter le nombre d&#39;enregistrements des sous-ensembles par répartition de données](split.md#limiting-the-number-of-subset-records-per-data-distribution).

* **[!UICONTROL Gestion de la validation :]**

  * Sélectionnez le modèle de diffusion et l’objet qui seront utilisés pour l’e-mail de notification. Un modèle par défaut est disponible : **[!UICONTROL Notification de validation locale]**. Vous pouvez également ajouter une description qui apparaîtra au-dessus des listes de personnes destinataires dans les notifications d’approbation et de commentaires.
  * Indiquez le **[!UICONTROL Type de validation]** correspondant à la date limite de validation (date ou date limite à partir du début de la validation). À cette date, le workflow recommence et les personnes destinataires qui n’ont pas été approuvées ne sont pas prises en compte dans le ciblage. Une fois les notifications envoyées, l’activité est mise en file d’attente afin que les personnes responsables locales puissent approuver leurs contacts.

    >[!NOTE]
    >
    >Par défaut, lorsque la validation débute, l&#39;activité est mise en attente pendant trois jours.

    Vous pouvez également ajouter un ou plusieurs rappels pour informer les personnes responsables locales que l’échéance approche. Pour ce faire, cliquez sur le lien **[!UICONTROL Ajouter un rappel]**.

* **[!UICONTROL Complémentaire]** : L&#39;option **[!UICONTROL Générer le complémentaire]** permet de générer un second ensemble contenant toutes les cibles non validées.

  >[!NOTE]
  >
  >Par défaut, cette option est désactivée.

## Rapport de retour de diffusion {#delivery-feedback-report}

Dans ce cas, l&#39;activité **[!UICONTROL Validation en local]** se place après la diffusion :

![](assets/local_validation_4.png)

Les champs à renseigner dans le cas d&#39;un rapport de retour de diffusion sont les suivants :

![](assets/local_validation_workflow_4.png)

* Sélectionnez l’option **[!UICONTROL Spécifié dans la transition]** si la diffusion a été saisie au cours d’une activité précédente. Sélectionnez **[!UICONTROL Explicite]** pour définir la diffusion dans l’activité d’approbation locale.
* Sélectionnez le modèle de diffusion et l’objet de l’e-mail de notification. Il existe un modèle par défaut : **[!UICONTROL Notification de validation locale]**.

## Exemple : validation de la diffusion d&#39;un workflow {#example--approving-a-workflow-delivery}

Cet exemple montre comment configurer un processus de validation pour une diffusion de workflow. Pour plus d’informations sur la création de workflows de diffusion, voir la section [Exemple : workflow de diffusion](delivery.md#example--delivery-workflow).

Pour valider une diffusion, un opérateur ou une opératrice peut utiliser la page web dont l’URL est fournie dans l’e-mail envoyé ou valider directement à partir de la console cliente.

* Validation Web

  L’e-mail envoyé aux opérateurs et opératrices du groupe Administration permet d’approuver la cible de la diffusion. Le message reprend le texte défini en remplaçant l’expression JavaScript par la valeur calculée (ici, « 574 »).

  Pour valider la diffusion, cliquez sur le lien correspondant et connectez-vous à la console cliente Adobe Campaign.

  ![](assets/new-workflow-valid-webaccess.png)

  Sélectionnez votre choix et cliquez sur le bouton **[!UICONTROL Soumettre]**.

  ![](assets/new-workflow-valid-webaccess-confirm.png)

* Approbation à partir de la console cliente

  Dans l’arborescence, le nœud **[!UICONTROL Administration > Exploitation > Objets créés automatiquement > Approbations en attente]** contient la liste des tâches que les opérateurs et opératrices actuellement connectés doivent valider. La liste doit afficher une ligne. Double-cliquez sur cette ligne pour répondre. La fenêtre suivante s’affiche :

![](assets/new-workflow-7.png)

Sélectionnez l’option **Oui**, puis cliquez sur le bouton **[!UICONTROL Approuver]**. Un message vous informe que la réponse est enregistrée.

Revenez sur l’écran des workflows : au bout de quelques dizaines de secondes, le diagramme se présente comme suit :

![](assets/new-workflow-8.png)

Le workflow a exécuté la tâche **[!UICONTROL Agir sur une diffusion]**, qui consiste ici à démarrer la diffusion précédemment créée. Le workflow s’est terminé sans erreurs.
