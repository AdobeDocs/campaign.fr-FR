---
product: campaign
title: Créer des campagnes récurrentes et périodiques
description: Découvrez comment créer et exécuter des campagnes récurrentes et périodiques
feature: Campaigns, Cross Channel Orchestration, Programs
source-git-commit: 72467caf94e652ede70c00f1ea413012fc4c7e1f
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 54%

---


# Les opérations récurrentes et périodiques {#recurring-and-periodic-campaigns}

A **campagne récurrente** est une opération basée sur un modèle spécifique dont les workflows sont configurés pour être exécutés selon un planning associé. Le ciblage est dupliqué à chaque exécution et les différents traitements et populations cibles sont suivis.  Une fois paramétrées, les campagnes récurrentes créent automatiquement un nouveau workflow (en dupliquant le modèle de workflow) et l&#39;exécutent. Par exemple, si vous devez envoyer un rappel mensuel à un segment d’audience, configurez une campagne récurrente afin qu’au début de chaque année, elle crée 12 workflows, un pour chaque mois. [En savoir plus](#create-a-recurring-campaign)

A **campagne périodique** est une opération basée sur un modèle spécifique qui permet de créer des instances d&#39;opération selon un planning d&#39;exécution. Les instances d&#39;opération sont créées automatiquement à partir d&#39;un modèle d&#39;opération périodique, selon la fréquence définie dans le planning du modèle. [En savoir plus](#create-a-periodic-campaign)

## Création d’une campagne récurrente {#create-a-recurring-campaign}

Les campagnes récurrentes sont créées à partir d’un modèle spécifique qui définit le modèle de workflow à exécuter et le planning d’exécution.

### Création d’un modèle pour les campagnes récurrentes {#create-the-campaign-template}

Pour créer un modèle pour les campagnes récurrentes, procédez comme suit :

1. Ouvrez l’explorateur Campaign et accédez à **[!UICONTROL Ressources > Modèles > Modèles d’opération]**.
1. Dupliquer la version intégrée **[!UICONTROL Campagne récurrente]** modèle.
   ![](assets/recurring-campaign-duplicate.png)
1. Saisissez le libellé du modèle et renseignez la durée de l&#39;opération.
1. Pour ce type d&#39;opération, un onglet **[!UICONTROL Planning]** est ajouté afin de créer le planning d&#39;exécution du modèle. Utilisez cet onglet pour définir les dates d&#39;exécution des opérations basées sur ce modèle.
   ![](assets/recurring-campaign-schedule.png)

   Le mode de paramétrage du planning d&#39;exécution correspond au **[!UICONTROL Planificateur]** du workflow. [En savoir plus](../workflow/scheduler.md).

   >[!CAUTION]
   >
   >Le paramétrage du planning d&#39;exécution doit être effectué avec précaution. Les opérations récurrentes dupliquent le ou les workflows de leur modèle selon le planning spécifié. Cette opération peut surcharger votre base de données.

1. Indiquez une valeur dans le champ **[!UICONTROL Créer d&#39;avance pour]** afin de créer les workflows correspondants pour la période indiquée.
1. Dans le **[!UICONTROL Ciblage et workflows]** , concevez le modèle de workflow à utiliser dans les opérations à partir de ce modèle. Ce workflow contient généralement les paramètres de ciblage et une ou plusieurs diffusions.

   >[!NOTE]
   >
   >Ce workflow doit être enregistré comme un modèle de workflow récurrent. Pour cela, éditez les propriétés du workflow et sélectionnez l&#39;option **[!UICONTROL Modèle de workflow récurrent]** dans l&#39;onglet **[!UICONTROL Exécution]**.

   ![](assets/recurring-campaign-wf-properties.png)

### Créer l&#39;opération récurrente {#create-the-recurring-campaign}

Pour créer l&#39;opération récurrente et exécuter ses workflows selon le planning défini dans le modèle, vous devez :

1. Créez une nouvelle opération à partir de votre modèle d&#39;opération récurrente.
1. Renseignez le planning d&#39;exécution du workflow, dans la **[!UICONTROL Planification]** . Le planning de l&#39;opération permet de renseigner pour chaque ligne la date de début de création ou d&#39;exécution du workflow automatique.

   Pour chaque ligne, il est possible d&#39;ajouter les options supplémentaires suivantes :

   * Activez la variable **[!UICONTROL A valider]** pour forcer les demandes de validation de diffusion dans le workflow.
   * Activez la variable **[!UICONTROL A démarrer]** pour démarrer le workflow une fois la date de début atteinte.

   Le champ **[!UICONTROL Créer d&#39;avance pour]** permet de créer l&#39;ensemble des workflows couvrant la période renseignée.

   A l&#39;exécution du workflow **[!UICONTROL Traitements sur les opérations]**, les workflows dédiés sont créés selon les occurrences définies dans le planning de l&#39;opération. Ainsi, un workflow est créé pour chaque date d&#39;exécution.

1. Les workflows récurrents sont créés automatiquement à partir du modèle de workflow présent dans l&#39;opération. Ils sont visibles à partir de l&#39;onglet **[!UICONTROL Ciblages et workflows]** de l&#39;opération.

   ![](assets/recurring-wf-created.png)

   Le libellé d&#39;une instance de workflow récurrent est composé du libellé de son modèle et du numéro du workflow. Les deux informations sont séparées par un caractère #.

   Les workflow créés à partir du planning y sont automatiquement associés, dans la colonne **[!UICONTROL Workflow]** de l&#39;onglet **[!UICONTROL Planning]**.

   ![](assets/recurring-wf-schedule-executed.png)

   Chaque workflow peut être édité à partir de cet onglet.

   >[!NOTE]
   >
   >La date de début de la ligne de planning associée au workflow est disponible à partir d&#39;une variable du workflow avec la syntaxe suivante :\
   >`$date(instance/vars/@startPlanningDate)`

## Création d’une campagne périodique {#create-a-periodic-campaign}

Une campagne périodique est une opération basée sur un modèle spécifique qui permet de créer des instances de campagnes selon un planning d’exécution. Les instances de campagnes sont créées automatiquement sur la base d’un modèle de campagne périodique, selon la fréquence définie dans le planning du modèle.

### Création du modèle de campagne {#create-the-campaign-template-1}

1. Ouvrez l’explorateur Campaign et accédez à **[!UICONTROL Ressources > Modèles > Modèles d’opération]**.
1. Dupliquer la version intégrée **[!UICONTROL Campagne périodique]** modèle.
1. Renseignez les propriétés du modèle.

   >[!NOTE]
   >
   >L&#39;opérateur auquel est affecté le modèle doit disposer des permissions adéquates pour créer les opérations dans le programme sélectionné.

1. Créez le workflow associé à ce modèle. Ce workflow est dupliqué dans chaque opération périodique créée par le modèle.

   >[!NOTE]
   >
   >Ce workflow est un modèle de workflow. Il ne peut pas être exécuté à partir du modèle d&#39;opération.

1. Renseignez son planning d&#39;exécution selon le même mode que pour un modèle d&#39;opération récurrente : cliquez sur le bouton **[!UICONTROL Ajouter]** et définissez les dates de début et de fin, ou complétez le planning d&#39;exécution à partir du lien.

   >[!CAUTION]
   >
   >Les modèles d&#39;opérations périodiques créent de nouvelles opérations selon le planning défini ci-dessus. Il doit donc être renseigné avec précaution afin de ne pas surcharger la base Adobe Campaign.

1. Une fois la date de début d&#39;exécution atteinte, l&#39;opération correspondante est automatiquement créée. Elle reprend l&#39;ensemble des caractéristiques de son modèle.

   Chaque opération peut être éditée à partir du planning du modèle.

   Chaque opération périodique contient les mêmes éléments. Une fois créée, elle est ensuite gérée comme une opération standard.
