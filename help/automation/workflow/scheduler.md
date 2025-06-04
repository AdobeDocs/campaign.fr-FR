---
product: campaign
title: Planificateur
description: En savoir plus sur l’activité de workflow de planificateur
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: ed70d2d3-251e-4ee8-84d4-73ad03e8dd35
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 43%

---

# Planificateur {#scheduler}



Le **Planificateur** est une tâche persistante qui active sa transition aux moments spécifiés par son planning.

L&#39;activité **[!UICONTROL Planificateur]** est à considérer comme un départ planifié. Les règles de positionnement de l&#39;activité dans le diagramme sont les mêmes que pour l&#39;activité **[!UICONTROL Début]**. L&#39;activité ne doit jamais comporter de transition entrante.

## Bonnes pratiques {#best-practices}

**Redémarrer le workflow après avoir modifié la planification** - Lorsque vous modifiez l’heure planifiée de l’activité **[!UICONTROL Planificateur]**, il est important de redémarrer le workflow. Cela permet de s’assurer que le workflow s’exécutera aux heures mises à jour. Sans redémarrer, le workflow continuera à s’exécuter selon l’ancien planning.

**Limiter la fréquence du planificateur** - Évitez de planifier des workflows pour qu’ils s’exécutent plus fréquemment que toutes les 15 minutes. Les exécuter plus souvent peut dégrader les performances du système et entraîner une congestion des bases de données.

**Utiliser un planificateur par branche** - Chaque branche de votre workflow ne doit comporter qu’une seule activité **[!UICONTROL Planificateur]**. Pour plus d&#39;informations sur les bonnes pratiques relatives à l&#39;utilisation des activités dans les workflows, consultez la page [Bonnes pratiques relatives aux workflows](workflow-best-practices.md#using-activities).

**Empêcher les exécutions simultanées de workflows** - Si un workflow est déclenché par un planificateur, gardez à l’esprit que plusieurs instances du workflow peuvent s’exécuter en même temps. Par exemple, si un planificateur déclenche le workflow toutes les heures, mais que l&#39;exécution du workflow dure plus d&#39;une heure, vous risquez de vous retrouver avec des exécutions qui se chevauchent. Pour éviter cela, pensez à configurer des vérifications pour empêcher plusieurs exécutions simultanées. [Découvrez comment empêcher l’exécution simultanée de plusieurs workflows](monitor-workflow-execution.md#preventing-simultaneous-multiple-executions).

**Compte tenu des transitions retardées** - Les transitions déclenchées par le planificateur peuvent être retardées si le workflow exécute des tâches de longue durée (comme les imports) ou si le module wfserver a été temporairement arrêté. Pour atténuer ce problème, limitez les heures d’activation du planificateur afin de vous assurer que les tâches s’exécutent dans une fenêtre temporelle définie.

## Paramétrage de l’activité Planificateur {#configuring-scheduler-activity}

Le planificateur définit le planning d&#39;activation de la transition. Pour le paramétrer, double-cliquez sur l&#39;objet graphique, puis cliquez sur **[!UICONTROL Changer…]**

![](assets/s_user_segmentation_scheduler.png)

Un assistant permet de définir la fréquence et la période de validité de l&#39;activité. Les étapes de paramétrage sont les suivantes :

1. Sélectionnez la fréquence d&#39;activation et cliquez sur **[!UICONTROL Suivant]**.

   ![](assets/s_user_segmentation_scheduler2.png)

1. Indiquez les heures et jours d’activation. Les paramètres de cette étape dépendent de la fréquence sélectionnée à l’étape précédente. Si vous choisissez de lancer l’activité plusieurs fois par jour, les options de configuration seront les suivantes :

   ![](assets/s_user_segmentation_scheduler3.png)

1. Définissez la période de validité du planning ou indiquez le nombre de fois où il sera exécuté.

   ![](assets/s_user_segmentation_scheduler4.png)

1. Vérifiez le paramétrage et cliquez sur le bouton **[!UICONTROL Terminer]** pour l&#39;enregistrer.

   ![](assets/s_user_segmentation_scheduler5.png)
