---
product: campaign
title: Union
description: En savoir plus sur l’activité de workflow d’union
feature: Workflows, Targeting Activity
version: Campaign v8, Campaign Classic v7
exl-id: 4109e198-bf9d-4dd2-92a1-16bbadbe30e8
TQID: 'https://experienceleague.adobe.com/-P-pc2ps970pfhgXZfv8atoVKGB-vS0B8vBdrR0DLZQ'
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
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 95%
---
# Union{#union}

Une **[!UICONTROL Union]** regroupe le résultat de plusieurs activités entrantes dans une cible unique. La cible est créée avec tous les résultats reçus : toutes les activités antérieures doivent donc être terminées pour que l’union soit exécutée.

![](assets/s_user_segmentation_union.png)

>[!NOTE]
>
>Pour plus d&#39;informations sur la configuration et l&#39;utilisation de l&#39;activité **[!UICONTROL Union]**, consultez [cette page](targeting-workflows.md#combining-several-targets--union-).

## Exemple d&#39;union {#union-example}

Dans l’exemple suivant, les résultats de deux requêtes sont réunis afin de mettre à jour la liste. Les deux requêtes ciblent les personnes destinataires. Les résultats sont donc basés sur la même table.

1. Insérez une activité de type **[!UICONTROL Union]** directement après les deux requêtes et avant une activité de mise à jour de liste puis ouvrez-la.
1. Indiquez éventuellement un libellé.
1. Sélectionnez la méthode de réconciliation **[!UICONTROL Uniquement les clés]** dans la mesure où dans cet exemple, les populations issues des requêtes contiennent des données homogènes.
1. Si vous avez ajouté des données additionnelles au niveau des requêtes, vous pouvez éventuellement choisir de ne conserver que celles qui sont communes.
1. Si vous souhaitez limiter la taille de la population finale, cochez l&#39;option **[!UICONTROL Limiter la taille de la population générée]**.

   Définissez cette dernière en indiquant le nombre de destinataires maximal et en choisissant la requête dont la population sera prioritaire.

1. Validez l&#39;activité **[!UICONTROL Union]** puis configurez l&#39;activité [Mise à jour de liste](list-update.md).
1. Démarrez le workflow. Le nombre de résultats s’affiche et la liste définie au niveau de l’activité de mise à jour de liste est créée ou mise à jour. Cette liste contient l’ensemble des personnes destinataires des deux requêtes ou le nombre défini à l’étape précédente, le cas échéant.

   ![](assets/union_example.png)

## Paramètres d&#39;entrée {#input-parameters}

* tableName
* schéma

Chacun des événements entrants doit spécifier une cible définie par ces paramètres.

## Paramètres de sortie {#output-parameters}

* tableName
* schéma
* recCount

Ce triplet de valeurs identifie la cible résultant de l&#39;union. **[!UICONTROL tableName]** est le nom de la table qui enregistre les identifiants de la cible, **[!UICONTROL schema]** est le schéma de la population (généralement nms:recipient) et **[!UICONTROL recCount]** est le nombre d’éléments dans la table.
