---
product: campaign
title: Composition de diffusion
description: En savoir plus sur l’activité de workflow de composition de diffusion
feature: Workflows, Targeting Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 3c06b329-b2d8-4ac8-ab9b-3ab3e525d109
TQID: 'https://experienceleague.adobe.com/-uyRqPAXzP-l05tmEfq4ZcJizCiGpTfY0qu-6tQ8cU0'
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
  - id: ff84ab2f-a7c2-4ced-a3c8-5113f4348d99
    internal-label: Targeting Activity
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 100%
---
# Composition de diffusion{#delivery-outline}

L’activité de **composition de diffusion** vous permet d’utiliser une composition dans un workflow de campagne. La composition doit avoir été créée au préalable dans la campagne.

Pour configurer l’activité, il vous suffit de sélectionner la composition de votre choix ainsi que la date prévue de contact. Vous pouvez ajouter des règles de filtrage en ajoutant des typologies ou des règles de typologie.

## Exemple : Insérer une offre via une composition de diffusion {#example--inserting-an-offer-via-a-delivery-outline}

L’activité de **composition de diffusion**, disponible dans les workflows de campagne, vous permet de présenter des offres référencées dans une composition de diffusion de la campagne en cours.

>[!NOTE]
>
>Le package **Interaction** doit être installé.

1. Dans un workflow, placez une activité de composition de diffusion avant une activité de diffusion.
1. Dans l&#39;activité de composition, définissez la composition que vous souhaitez utiliser.
1. Complétez les champs disponibles en fonction de votre diffusion.
1. Deux cas se présentent :

   * Si vous souhaitez appeler le moteur d’offre, cochez la case **[!UICONTROL Limiter le nombre de propositions sélectionnées]**. Précisez l’emplacement et le nombre de propositions qui seront présentées dans la diffusion.

     Les poids et règles d&#39;éligibilité des offres seront pris en compte par le moteur d&#39;offres.

   * Si vous ne cochez pas la case, toutes les offres de la composition de diffusion seront présentées, sans appel au moteur d&#39;offres.

   La prévisualisation prend en compte le nombre d’offres défini dans la diffusion. Lors de l’exécution d’un workflow, c’est le nombre défini dans la composition de diffusion qui est pris en compte.

   ![](assets/int_compo_offre_wf1.png)
