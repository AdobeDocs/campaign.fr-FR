---
product: campaign
title: Début et Fin
description: En savoir plus sur les activités de workflow de début et de fin
feature: Workflows
version: Campaign v8, Campaign Classic v7
exl-id: 1de622bc-967b-403b-86e0-2ad32cb432e3
TQID: https://experienceleague.adobe.com/Y6nuELN3qjtuXhruC9MgmyqxzptNTJgfZ0XLGleQ3A4
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 140
ht-degree: 21%

---

# Début et Fin{#start-and-end}



Les activités **[!UICONTROL Début]** et **[!UICONTROL Fin]** vous permettent de marquer graphiquement le début et la fin d’un workflow. Ces activités n’ont aucun impact fonctionnel et sont donc facultatives.

* **[!UICONTROL Début]**

  L&#39;exécution d&#39;un workflow démarre par les activités sans transition entrante et les activités de type Début.

  ![](assets/s_user_segmentation_start_stop.png)

* **[!UICONTROL Fin]**

  Vous pouvez paramétrer l&#39;activité **[!UICONTROL Fin]** pour interrompre toutes les tâches en cours. Pour ce faire, double-cliquez sur l’activité pour afficher ses propriétés, puis cochez l’option appropriée.

  ![](assets/s_user_segmentation_end.png)

  Les données de la table de travail sont automatiquement supprimées lorsque l&#39;activité de fin est activée. Si cela n’est pas nécessaire, et pour éviter des charges inutiles, vous pouvez choisir de désactiver la transition à la sortie de la dernière activité. Par exemple, au niveau d&#39;une sortie de diffusion, si aucun traitement n&#39;est planifié, désélectionnez l&#39;option correspondante comme dans l&#39;exemple ci-dessous :

  ![](assets/s_advuser_delivery_option_no_output.png)
