---
product: campaign
title: Attente
description: En savoir plus sur l’activité de workflow d’attente
feature: Workflows
version: Campaign v8, Campaign Classic v7
exl-id: a9bcb214-5c87-4b26-804a-22b868905022
TQID: 'https://experienceleague.adobe.com/pCmFiYzA61DTXdDZCO14diygPbfuvZkXIbKVgbtXmQQ'
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
source-wordcount: '193'
ht-degree: 100%
---
# Attente{#wait}



Une activité **Attente** active sa transition après un délai pouvant aller de quelques secondes à plusieurs mois. Une tâche d’attente n’est pas bloquante, le workflow peut exécuter d’autres tâches en parallèle pendant que celle-ci est en attente.

L&#39;éditeur permet de saisir le libellé et la durée d&#39;attente, comme dans l&#39;exemple ci-dessous :

![](assets/edit_wait.png)

Dans le champ **[!UICONTROL Durée]**, la valeur peut être exprimée dans l’unité de votre choix (en fonction des paramètres régionaux définis pour l’opérateur ou l’opératrice) :

* Si les paramètres régionaux ne sont pas définis : **s** pour les secondes, **m** pour les minutes, **h** pour les heures, **d** pour les jours, **y** pour les années. Lors de la validation, la valeur est automatiquement convertie dans l’unité la plus lisible.

  L&#39;unité par défaut est le jour (**j**).

* Tandis que si, par exemple, les paramètres régionaux sont définis sur &#39;Français&#39; : **s** pour les secondes, **mn** pour les minutes, **h** pour les heures, **j** pour les jours, **m** pour les mois, **a** pour les années. Lors de la validation, la valeur est automatiquement traduite dans l&#39;unité la plus lisible, comme dans l&#39;exemple ci-dessus : **90s** a été traduit en **1mn 30s**.

  L&#39;unité par défaut est le jour (**j**).
