---
product: campaign
title: Début et Fin
description: En savoir plus sur les activités de workflow de début et de fin
feature: Workflows
version: Campaign v8, Campaign Classic v7
exl-id: 1de622bc-967b-403b-86e0-2ad32cb432e3
TQID: 'https://experienceleague.adobe.com/Y6nuELN3qjtuXhruC9MgmyqxzptNTJgfZ0XLGleQ3A4'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '140'
ht-degree: 100%
---
# Début et Fin{#start-and-end}



Les activités **[!UICONTROL Début]** et **[!UICONTROL Fin]** permettent de marquer graphiquement le début et la fin d’un workflow. Elles n’ont pas d’impact fonctionnel et sont donc facultatives.

* **[!UICONTROL Début]**

  L&#39;exécution d&#39;un workflow démarre par les activités sans transition entrante et les activités de type Début.

  ![](assets/s_user_segmentation_start_stop.png)

* **[!UICONTROL Fin]**

  Vous pouvez paramétrer l’activité **[!UICONTROL Fin]** afin qu’elle interrompe toutes les tâches en cours. Pour cela, double-cliquez sur l’activité pour afficher ses propriétés et cochez l’option correspondante.

  ![](assets/s_user_segmentation_end.png)

  Les données de la table de travail sont automatiquement supprimées lorsque l’activité de fin est activée. Si cela n’est pas nécessaire, et pour éviter des charges inutiles, vous pouvez désactiver la transition à la sortie de la dernière activité. Par exemple, si aucun traitement n’est planifié au niveau d’une sortie de diffusion, désélectionnez l’option correspondante, comme dans l’exemple ci-dessous :

  ![](assets/s_advuser_delivery_option_no_output.png)
