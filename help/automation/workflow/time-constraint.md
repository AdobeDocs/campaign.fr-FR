---
product: campaign
title: Contrainte horaire
description: En savoir plus sur l’activité de workflow de contrainte horaire
feature: Workflows
version: Campaign v8, Campaign Classic v7
exl-id: 0a922827-456d-425c-be04-d9efbb152c92
TQID: 'https://experienceleague.adobe.com/H5or5WZXA8Nl2OBYo6EkFGAwEguMYDCKs1CqLbzODkk'
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
source-wordcount: '107'
ht-degree: 65%
---
# Contrainte horaire{#time-constraint}

Une activité **Contrainte horaire** permet de reporter l’exécution d’une tâche ou de l’abandonner.

Saisissez le libellé de l’activité et indiquez la période pendant laquelle la tâche de workflow est autorisée à s’exécuter. Le workflow ne s’exécutera que pendant cette fenêtre d’exécution définie et restera en pause en dehors de celle-ci.

Lorsque l’option **[!UICONTROL Retenter plus tard si hors plage d’exécution]** est sélectionnée, elle vous permet de relancer la tâche en dehors de la période d’exécution. Si vous souhaitez que l’action du workflow soit définitivement abandonnée après sa suspension, désélectionnez cette option.

![](assets/s_user_scheduled_wait.png)
