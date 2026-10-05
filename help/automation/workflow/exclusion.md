---
product: campaign
title: Exclusion
description: En savoir plus sur l’activité de workflow d’exclusion
feature: Workflows, Targeting Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 8ea831e2-8e6e-4ef0-ac05-f27ebf89ccb9
TQID: 'https://experienceleague.adobe.com/N3G0NbmUjk9fbgjKW957QneAHZ7Oy12seBK-AfO6puM'
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
source-wordcount: '366'
ht-degree: 100%
---
# Exclusion{#exclusion}



Une activité de type **Exclusion** crée une cible à partir d&#39;une cible principale dont on extrait une ou plusieurs autres cibles.

Pour configurer cette activité, saisissez son libellé et sélectionnez l’ensemble de personnes destinataires principal : la population de l’ensemble principal vous permet de construire le résultat. Les profils communs à l’ensemble principal et à au moins une des activités en entrée seront exclus.

![](assets/s_user_segmentation_exclu.png)

>[!NOTE]
>
>Pour plus d’informations sur la configuration et l’utilisation de l’activité d’exclusion, voir [Exclure une population (Exclusion)](targeting-workflows.md#excluding-a-population--exclusion-).

Cochez l’option **[!UICONTROL Générer le complémentaire]** si vous souhaitez exploiter la population restante. Le complémentaire contiendra la population entrante principale, moins la population sortante. Une autre transition de sortie sera alors ajoutée à l’activité, comme suit :

![](assets/s_user_segmentation_exclu_compl.png)

## Exemples d&#39;exclusion {#exclusion-examples}

L&#39;exemple suivant cherche à constituer une liste des destinataires dont l&#39;âge est compris entre 18 et 30 ans, mais en y excluant les habitants de Paris.

1. Insérez et ouvrez une activité de type **[!UICONTROL Exclusion]** suite à deux requêtes. La première requête cible les personnes destinataires résidant à Paris. La deuxième requête cible les 18 à 30 ans.
1. Indiquez l&#39;ensemble principal. Ici, l&#39;ensemble principal est la requête **18-30 ans**. Les éléments appartenant au second ensemble seront exclus du résultat final.
1. Cochez l’option **[!UICONTROL Générer le complémentaire]** si vous souhaitez exploiter les données non retenues après l’exclusion. Dans ce cas, le complémentaire comporte les personnes destinataires âgées de 18 à 30 ans habitant à Paris.
1. Approuvez la configuration de l’exclusion puis insérez une activité de mise à jour de liste au niveau du résultat. Vous pouvez également insérer une autre mise à jour de liste au niveau du complémentaire, si nécessaire.
1. Exécutez le workflow. Dans cet exemple, le résultat comporte toutes les personnes destinataires âgées de 18 à 30 ans, mais celles habitant à Paris sont exclues et sont envoyées vers le complémentaire.

   ![](assets/exclusion_example.png)

## Paramètres d&#39;entrée {#input-parameters}

* tableName
* schéma

Chacun des événements entrants doit spécifier une cible définie par ces paramètres.

## Paramètres de sortie {#output-parameters}

* tableName
* schéma
* recCount

Ce triplet de valeurs identifie la cible résultant de l&#39;exclusion. **[!UICONTROL tableName]** est le nom de la table qui enregistre les identifiants de la cible, **[!UICONTROL schema]** est le schéma de la population (généralement nms:recipient) et **[!UICONTROL recCount]** est le nombre d’éléments dans la table.

La transition associée au complément possède les mêmes paramètres.
