---
product: campaign
title: Test
description: En savoir plus sur l’activité de workflow de test
feature: Workflows
version: Campaign v8, Campaign Classic v7
exl-id: 0d4d13f6-7128-44d3-ad5c-4ed02257ee64
TQID: 'https://experienceleague.adobe.com/dXkGOQ-OD-KUwWx29DcE7FqYzbDSF-M6ox8-8cTurjA'
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
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 85%
---
# Test{#test}



Une activité de type **Test** active la première transition qui satisfait la condition qui lui est associée. Si aucune condition n’est satisfaite et que l’option **[!UICONTROL Utiliser le branchement par défaut]** est activée, la transition par défaut sera activée.

Une condition est une expression JavaScript qui doit être déterminée par « true » ou « false ». Pour saisir l’expression, cliquez sur l’icône située à droite du nom de la condition, puis sélectionnez **[!UICONTROL Modifier...]**.

![Tester le tableau des conditions d&#39;activité avec le menu de personnalisation ouvert sur l&#39;option Modifier et la zone Utiliser la connexion par défaut](assets/edit_test.png)

Pour plus d’informations sur toutes les autres fonctions JavaScript et méthodes SOAP du serveur applicatif accessibles via workflow, consultez la [documentation JSAPI](https://experienceleague.adobe.com/fr/tools/campaign-api){target="_blank"}.

Vous pouvez insérer directement des variables également depuis cet éditeur. Pour plus d&#39;informations sur l&#39;utilisation des variables, consultez la section [Variables](javascript-scripts-and-templates.md#variables).

Les conditions peuvent être ajoutées, supprimées, ordonnées depuis la fenêtre d&#39;édition des propriétés de l&#39;activité, mais aussi modifiées depuis la transition.

Si le résultat d’un calcul doit être réutilisé par différentes conditions, il est possible de le calculer dans le script d’initialisation de l’activité. Le résultat doit être stocké dans une variable de la tâche pour être accessible par les scripts de conditions (task.vars.xxx).
