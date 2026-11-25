---
product: campaign
title: Modification des images d’activité
description: Découvrez comment modifier l’image de l’activité
feature: Workflows
role: Admin
version: Campaign v8, Campaign Classic v7
exl-id: f5580401-3305-4915-88a2-3400a32aa7aa
TQID: 'https://experienceleague.adobe.com/9i-2gtfWr0ghkIif2S-ORoXk-hTlSMHgkeRAmMW0msg'
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
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 76%
---
# Modification des images d’activité{#change-activity-images}



Les images utilisées dans les diagrammes des différents workflows peuvent être modifiées. Elles doivent toutefois respecter certaines contraintes. Les étapes de mise en œuvre sont les suivantes :

* Pour changer l’image d’arrière-plan, sélectionnez le workflow de ciblage visé et cliquez sur **[!UICONTROL Propriétés]**.

  ![Propriétés du workflow, onglet Avancé : champ Image d’arrière-plan avec l’icône Sélectionner le lien en surbrillance.](assets/s_user_segmentation_properties_tab.png)

  Cliquez sur l’icône **[!UICONTROL Choisir le lien]** situé à droite du champ **[!UICONTROL Image d’arrière-plan]** pour sélectionner l’image à utiliser.

  >[!NOTE]
  >
  >La largeur en pixels de l’image d’arrière-plan doit être un multiple de 4.

  ![Fenêtre de sélection des images répertoriant les images d’arrière-plan telles que backgrounds/grid.png, avec OK pour confirmation.](assets/s_user_segmentation_background_select.png)

  L&#39;icône **[!UICONTROL Editer le lien]** permet de visualiser l&#39;image sélectionnée.

* Pour changer l&#39;image associée à une activité, double-cliquez sur l&#39;objet et cliquez sur l&#39;onglet **[!UICONTROL Avancé]**.

  Cliquez sur l&#39;icône **[!UICONTROL Choisir le lien]** situé à droite du champ **[!UICONTROL Image]** pour sélectionner l&#39;image à utiliser.

  ![Onglet avancé d’une activité avec le champ Image mis en surbrillance, défini sur activities/dedup.png.](assets/s_user_segmentation_activity_image.png)

  L&#39;icône **[!UICONTROL Editer le lien]** permet de visualiser l&#39;image sélectionnée.

  ![Aperçu de l’image sélectionnée nms:activities/dedup.png, affiché avec l’icône Modifier le lien.](assets/s_user_segmentation_activity_image_select.png)

>[!NOTE]
>
>Les images proposées sont celles qui sont enregistrées dans le noeud **[!UICONTROL Administration > Paramétrage > Images]** de l&#39;arborescence.
>  
>Les images doivent être au format PNG, 48x48 pixels, 16 millions de couleurs et avec un arrière-plan transparent.
