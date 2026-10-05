---
product: campaign
title: Requête incrémentale
description: En savoir plus sur l’activité de workflow de requête incrémentale
feature: Workflows, Targeting Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 3e9f92c3-080f-441b-a15a-2ec9d056d1f9
TQID: 'https://experienceleague.adobe.com/tUbJMqAfHEEm-PBuyCiu4dclE-AsEUxY0nXMTJA1BBE'
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
source-wordcount: '379'
ht-degree: 100%
---
# Requête incrémentale{#incremental-query}



Une requête incrémentale permet de sélectionner périodiquement une cible selon un critère, mais d&#39;exclure les personnes qui ont déjà été ciblées sur ce critère les fois précédentes.

La population déjà ciblée est mémorisée par instance de workflow et par activité, c’est-à-dire que deux workflows démarrés à partir du même modèle ne partagent pas le même log. Toutefois, deux tâches basées sur la même requête incrémentale dans le même workflow utilisent le même log.

La requête est définie selon le même mode que pour les requêtes standard, mais son exécution est planifiée.

**Rubriques connexes :**

* [Cas pratique : mise à jour de la liste trimestrielle à l’aide d’une requête incrémentielle](quarterly-list-update.md)
* [Créer une requête](query.md#creating-a-query)

>[!CAUTION]
>
>Si le résultat d’une requête incrémentale est égal à **0** lors de l’une de ses exécutions, le workflow est mis en pause jusqu’à la prochaine exécution programmée de la requête. Les transitions et les activités qui suivent la requête incrémentale ne sont donc pas traitées avant l’exécution suivante.

Pour ce faire :

1. Dans l’onglet **[!UICONTROL Planification et historique]**, sélectionnez l’option **[!UICONTROL Planifier l’exécution]**. La tâche reste active une fois créée et ne sera déclenchée qu’aux heures spécifiées par le planning d’exécution de la requête. En revanche, si l&#39;option est désactivée, la requête est exécutée immédiatement **et une seule fois**.
1. Cliquez sur le bouton **[!UICONTROL Changer]**.

   Dans la fenêtre **[!UICONTROL Assistant d’édition d’un planning]** qui s’affiche, vous pouvez configurer le type de fréquence, la périodicité des événements et la période de validité des événements.

   ![](assets/s_user_segmentation_wizard_11.png)

1. Cliquez sur **[!UICONTROL Terminer]** pour enregistrer le planning.

   ![](assets/s_user_segmentation_wizard_valid.png)

1. La section inférieure de l&#39;onglet **[!UICONTROL Planification &amp; Historique]** permet de sélectionner le nombre de jours d&#39;historique à prendre en compte.

   ![](assets/edit_request_inc.png)

   * **[!UICONTROL Jours d&#39;historique]**

     Les personnes destinataires déjà ciblées dans les exécutions précédentes peuvent être consignées dans un log selon un nombre de jours maximum à partir de celui où elles ont été ciblées. Si cette valeur est égale à zéro, les personnes destinataires ne sont jamais purgées du log.

   * **[!UICONTROL Conserver l&#39;historique au démarrage]**

     Cette option permet de ne pas effacer l&#39;historique lors de l&#39;activation de l&#39;activité.

   * **[!UICONTROL Nom de la table SQL]**

     Ce champ permet de surcharger la table SQL par défaut contenant les données d&#39;historique.

## Paramètres de sortie {#output-parameters}

* tableName
* schéma
* recCount

Ce jeu de trois valeurs identifie la population ciblée par la requête. **[!UICONTROL tableName]** est le nom de la table qui enregistre les identifiants de la cible, **[!UICONTROL schema]** est le schéma de la population (généralement nms:recipient) et **[!UICONTROL recCount]** est le nombre d’éléments dans la table.
