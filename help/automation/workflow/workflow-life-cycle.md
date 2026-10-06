---
product: campaign
title: Cycle de vie d'un workflow
description: En savoir plus sur le cycle de vie d’un workflow
feature: Workflows
version: Campaign v8, Campaign Classic v7
exl-id: 4356b90c-9d7c-49ef-88cd-716b2ccdb7f0
TQID: 'https://experienceleague.adobe.com/lrXuOzmsLhy3AfYLPzKfLd1-IVfB5r9xZZqoMdihYus'
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
source-wordcount: '261'
ht-degree: 100%
---
# Cycle de vie d&#39;un workflow {#workflow-life-cycle}



Le cycle de vie d&#39;un workflow comporte trois grandes étapes.

* **En édition**

  Il s’agit de la phase de conception initiale : lorsqu’un nouveau workflow est créé, son statut est « En cours d’édition ». Le workflow n’est pas encore pris en charge par le serveur et peut être modifié sans risque.

* **Démarré**

  Une fois la phase de conception terminée, le workflow peut être démarré. Au cours de cette phase, l’instance est gérée par le serveur et les tâches individuelles sont exécutées. Le workflow peut toujours être modifié avec certaines précautions.

* **Terminé**

  Un workflow est terminé lorsqu&#39;il n&#39;a plus de tâche en cours ou lorsqu&#39;un opérateur a arrêté explicitement l&#39;instance.

Par exemple, dans le workflow ci-dessous, les activités **Début** et **Diffusion** sont entourées tandis que l’activité **Validation** clignote.

![](assets/new-workflow-6.png)

Cela signifie que les deux premières activités ont été exécutées avec succès et que la validation est en cours, c&#39;est-à-dire que l&#39;activité est créée mais pas encore complétée.

Les caractères **574 -Ok** affichés au-dessus de la transition suivant l’activité **Diffusion** signifient que la préparation de la diffusion a ciblé 574 personnes destinataires et que l’opération s’est terminée correctement. Ces informations, ajoutées sur les transitions au moment de l’exécution, sont calculées par les activités traitant des données.

Le workflow est donc démarré et attend la décision d&#39;un opérateur du groupe spécifié dans l&#39;activité **Validation**. Les opérateurs et opératrices du groupe ayant une adresse e-mail ou un numéro de mobile renseigné reçoivent une notification.

Pour plus d&#39;informations sur la manière de surveiller vos workflows, voir [cette section](monitor-workflow-execution.md).
