---
product: campaign
title: Changement de dimension dans un workflow
description: Découvrez comment utiliser l’activité « Changement de dimension ».
feature: Workflows, Targeting Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 71f36413-377a-4be6-921c-9e794fe882fd
TQID: https://experienceleague.adobe.com/BkGTNKy7N35h3jO5-Ao2x2-nClcv96wqT2AqIsAXlSA
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 450
ht-degree: 74%

---

# Changement de dimension{#change-dimension}

Utilisez l’activité **[!UICONTROL Changement de dimension]** pour changer la dimension de ciblage au fur et à mesure que vous créez une audience. Cette activité déplace l’axe en fonction du modèle de données et de la dimension d’entrée. Par exemple, vous passez de la dimension « contrats » à la dimension « clients ».

Vous pouvez également utiliser cette activité pour définir les colonnes supplémentaires de la nouvelle cible et définir les critères de déduplication des données.

>[!IMPORTANT]
>
>Notez que les activités **[!UICONTROL Changer la dimension]** et **[!UICONTROL Modifier la source de données]** ne doivent pas être ajoutées sur une même ligne. Si vous devez utiliser les deux activités consécutivement, veillez à inclure une activité **[!UICONTROL Enrichissement]** entre les deux. Cela garantit une bonne exécution et évite les erreurs et conflits potentiels.

Pour configurer l’activité de **[!UICONTROL changement de dimension]**, respectez les étapes suivantes :

1. Sélectionnez la nouvelle dimension de ciblage à partir du champ **[!UICONTROL Changement de dimension]**.

   ![](assets/s_user_change_dimension_param1.png)

1. Lors du changement de dimension, vous pouvez conserver tous les éléments ou les sélectionner pour les conserver dans la sortie. Dans l’exemple suivant, la valeur maximale. nombre de doublons défini sur 2.

   ![](assets/s_user_change_dimension_limit.png)

   Lorsque vous choisissez de ne conserver qu&#39;un seul enregistrement, une collection apparaît dans le schéma de travail : cette collection représente tous les enregistrements qui ne seront pas ciblés dans le résultat final (puisqu&#39;un seul enregistrement est conservé). Comme toutes les autres collections, celle-ci permet de calculer des agrégats ou de récupérer des informations en colonnes.

   Par exemple, si on passe de la dimension des **[!UICONTROL Clients]** à celle des **[!UICONTROL Destinataires]**, il sera possible de cibler les clients d&#39;un magasin, en précisant le nombre d&#39;achats réalisés.

1. Si vous choisissez de ne pas conserver tous les enregistrements, vous pouvez configurer le mode de gestion des doublons.

   ![](assets/s_user_change_dimension_param2.png)

   Les flèches bleues permettent de définir l&#39;ordre de priorité de traitement des doublons.

   Dans l’exemple ci-dessus, les destinataires seront dédupliqués d’abord sur leur adresse e-mail puis, au besoin, sur leur numéro de compte.

1. L&#39;onglet **[!UICONTROL Résultat]** permet d&#39;ajouter des informations complémentaires.

   Vous pouvez par exemple récupérer le numéro du département à partir du code postal en utilisant une fonction de type **Substring**. Pour cela :

   * Cliquez sur le lien **[!UICONTROL Ajouter des données...]** et sélectionnez **[!UICONTROL Données liées à la dimension de filtrage]**.

     ![](assets/wf_change-dimension_sample_01.png)

     >[!NOTE]
     >
     >Pour plus d’informations sur la création et la gestion des colonnes additionnelles, reportez-vous à la section [Ajouter des données](query.md#add-data).

   * Choisissez la dimension de ciblage précédente (avant le basculement d&#39;axe) et sélectionnez le **[!UICONTROL Code Postal]** dans la sous-arborescence **[!UICONTROL Localisation]** du destinataire, puis cliquez sur **[!UICONTROL Editer l&#39;expression]**.

     ![](assets/wf_change-dimension_sample_02.png)

   * Cliquez sur **[!UICONTROL Sélection avancée]** et choisissez **[!UICONTROL Editer la formule à partir d&#39;une expression]**.

     ![](assets/wf_change-dimension_sample_03.png)

   * Utilisez les fonctions proposées dans la liste et indiquez le calcul à réaliser.

     ![](assets/wf_change-dimension_sample_04.png)

   * Pour finir, saisissez le libellé de la colonne que vous venez de créer.

     ![](assets/wf_change-dimension_sample_05.png)

1. Exécutez le workflow pour afficher le résultat de cette configuration. Comparez les données contenues dans les tableaux avant et après l’activité de changement de dimension, comparez également la structure des tableaux de workflow, comme dans les exemples suivants :

   ![](assets/wf_change-dimension_sample_06.png)

   ![](assets/wf_change-dimension_sample_07.png)
