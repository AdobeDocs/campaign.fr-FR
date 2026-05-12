---
product: campaign
title: Cycle de vie d'un workflow
description: En savoir plus sur le cycle de vie d’un workflow
feature: Workflows
version: Campaign v8, Campaign Classic v7
exl-id: 4356b90c-9d7c-49ef-88cd-716b2ccdb7f0
TQID: https://experienceleague.adobe.com/lrXuOzmsLhy3AfYLPzKfLd1-IVfB5r9xZZqoMdihYus
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 261
ht-degree: 55%

---

# Cycle de vie d&#39;un workflow {#workflow-life-cycle}



Le cycle de vie d&#39;un workflow comporte trois grandes étapes.

* **En édition**

  Il s’agit de la phase de conception initiale : lorsqu’un nouveau workflow est créé, son statut est « En édition ». Le workflow n’est pas encore géré par le serveur et peut être modifié sans risque.

* **Démarré**

  Une fois la phase de conception initiale terminée, le workflow peut être démarré. Au cours de cette phase, l’instance est gérée par le serveur et les tâches individuelles sont exécutées. Le workflow peut toujours être modifié avec certaines précautions.

* **Terminé**

  Un workflow est terminé lorsqu&#39;il n&#39;a plus de tâche en cours ou lorsqu&#39;un opérateur a arrêté explicitement l&#39;instance.

Par exemple, dans le workflow ci-dessous, les activités **Début** et **Diffusion** sont entourées tandis que l’activité **Validation** clignote.

![](assets/new-workflow-6.png)

Cela signifie que les deux premières activités ont été exécutées avec succès et que la validation est en cours, c&#39;est-à-dire que l&#39;activité est créée mais pas encore complétée.

Les caractères **574 -Ok** affichés au-dessus de la transition suivant l&#39;activité **Diffusion** signifient que la préparation de la diffusion a ciblé 574 destinataires et que l&#39;opération a été effectuée avec succès. Ces informations, qui sont ajoutées aux transitions lors de leur exécution, sont calculées par les activités qui traitent les données.

Le workflow est donc démarré et attend la décision d&#39;un opérateur du groupe spécifié dans l&#39;activité **Validation**. Les opérateurs et opératrices du groupe ayant une adresse e-mail ou un numéro de mobile renseigné reçoivent une notification.

Pour plus d&#39;informations sur la manière de surveiller vos workflows, voir [cette section](monitor-workflow-execution.md).
