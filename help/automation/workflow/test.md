---
product: campaign
title: Test
description: En savoir plus sur l’activité de workflow de test
feature: Workflows
version: Campaign v8, Campaign Classic v7
exl-id: 0d4d13f6-7128-44d3-ad5c-4ed02257ee64
TQID: https://experienceleague.adobe.com/dXkGOQ-OD-KUwWx29DcE7FqYzbDSF-M6ox8-8cTurjA
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
source-git-commit: 2425b8e500380076d56bccec41ac821f7c867d92
workflow-type: tm+mt
source-wordcount: 197
ht-degree: 96%

---

# Test{#test}



Une activité de type **Test** active la première transition qui satisfait la condition qui lui est associée. Si aucune condition n’est satisfaite et que l’option **[!UICONTROL Utiliser le branchement par défaut]** est activée, la transition par défaut sera activée.

Une condition est une expression JavaScript qui doit être déterminée par « true » ou « false ». Pour saisir l’expression, cliquez sur l’icône située à droite du nom de la condition, puis sélectionnez **[!UICONTROL Modifier...]**.

![](assets/edit_test.png)

Pour plus d’informations sur toutes les autres fonctions JavaScript et méthodes SOAP du serveur applicatif accessibles via workflow, consultez la [documentation JSAPI](https://experienceleague.adobe.com/fr/tools/campaign-api){target="_blank"}.

Vous pouvez insérer directement des variables également depuis cet éditeur. Pour plus d’informations sur l’utilisation des variables, consultez [cette section](javascript-scripts-and-templates.md#variables).

Les conditions peuvent être ajoutées, supprimées, ordonnées depuis la fenêtre d&#39;édition des propriétés de l&#39;activité, mais aussi modifiées depuis la transition.

Si le résultat d’un calcul doit être réutilisé par différentes conditions, il est possible de le calculer dans le script d’initialisation de l’activité. Le résultat doit être stocké dans une variable de la tâche pour être accessible par les scripts de conditions (task.vars.xxx).
