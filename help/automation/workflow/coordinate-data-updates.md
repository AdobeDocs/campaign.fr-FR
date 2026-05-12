---
product: campaign
title: Coordonner les mises à jour de données
description: Coordonner les mises à jour de données
feature: Workflows, Data Management
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 9faf7ee7-07c1-415b-b234-a945994792c7
TQID: https://experienceleague.adobe.com/DmafsXGIr-CWPruj9mDR-XmcnWHeMk75-Sm-70-aCk4
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 304
ht-degree: 70%

---

# Coordonner les mises à jour de données{#coordinating-data-updates}



Ce cas pratique présente la création d’un workflow permettant de gérer des mises à jour concomitantes lors de l’utilisation de plusieurs exécutions d’un workflow.

Le but est de vérifier que le processus de mise à jour est terminé avant d&#39;exécuter une autre opération de mise à jour. Pour ce faire, nous allons configurer une variable d’instance et laisser le workflow tester si l’instance est en cours d’exécution afin de décider de continuer ou non l’exécution du workflow et d’effectuer la mise à jour.

![](assets/uc_dataupdate_wkf.png)

Ce workflow se compose de :

* une activité **Planificateur** exécutant le workflow à une fréquence spécifique,
* une activité **Test** vérifiant si le workflow est déjà en cours d&#39;exécution,
* des activités **Requête** et **Mise à jour de données** si le workflow n&#39;est pas déjà en cours d&#39;exécution, suivies d&#39;une activité **Fin** réinitialisant la variable d&#39;instance du workflow à la valeur false.
* une activité **Fin** si le workflow est déjà en cours d&#39;exécution.

Pour créer le workflow, procédez comme suit :

1. Ajoutez une activité **Planificateur**, puis configurez sa fréquence selon vos besoins.
1. Ajoutez une activité **Test** pour vérifier si le workflow est déjà en cours d&#39;exécution, puis configurez-la comme indiqué ci-dessous.

   >[!NOTE]
   >
   >« isRunning » est le nom de la variable d&#39;instance choisi pour cet exemple. Il ne s’agit pas d’une variable intégrée.

   ![](assets/uc_dataupdate_test.png)

1. Ajoutez une activité **Fin** au branchement **Non**. Ainsi, rien ne sera exécuté si le workflow est déjà en cours d&#39;exécution.
1. Ajoutez les activités souhaitées au branchement **Oui**. Dans le cas présent, il s&#39;agit des activités **Requête** et **Mise à jour des données**.
1. Ouvrez la première activité, puis ajoutez la commande **instance.vars.isRunning = true** dans l&#39;onglet **[!UICONTROL Avancé]**. Ainsi, la variable d&#39;instance est définie comme étant en cours d&#39;exécution.

   ![](assets/uc_dataupdate_query.png)

1. Ajoutez une activité **Fin** à l&#39;extrémité du branchement **[!UICONTROL Oui]**, puis la commande **instance.vars.isRunning = false** dans l&#39;onglet **[!UICONTROL Avancé]**.

   De cette manière, aucune action ne sera exécutée tant que le workflow sera en cours d&#39;exécution.

   ![](assets/uc_dataupdate_end.png)

**Rubriques connexes :**

* [Empêcher les exécutions multiples simultanées](monitor-workflow-execution.md#preventing-simultaneous-multiple-executions)
* [Activité Mise à jour de données](update-data.md)
