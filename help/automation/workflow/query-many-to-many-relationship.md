---
product: campaign
title: Requête avec une relation multiple-à-multiple
description: Découvrez comment exécuter des requêtes à l’aide d’une relation multiple-à-multiple
feature: Query Editor
role: User, Data Engineer
exl-id: c320054d-7f67-4b12-aaa7-785945bf0c18
source-git-commit: 28742db06b9ca78a4e952fcb0e066aa5ec344416
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 64%

---

# Requête avec une relation multiple-à-multiple {#querying-using-a-many-to-many-relationship}



Dans cet exemple, vous allez récupérer les destinataires non contactés au cours des 7 derniers jours. Cette requête concerne toutes les diffusions.

Ce cas indique par ailleurs comment paramétrer un filtrage découlant du choix d&#39;un élément de collection (ou noeud orange). Les éléments de collection sont disponibles dans la fenêtre **[!UICONTROL Champ à sélectionner]**.

* Quelle table doit-on sélectionner ?

  La table des destinataires (**nms:recipient**).

* Quels sont les champs à sélectionner en colonne de sortie ?

  Clé primaire, Nom, Prénom et Email.

* En fonction de quels critères seront filtrées les informations ?

  En fonction des logs de diffusion des destinataires. Ils remontent jusqu&#39;à 7 jours avant la date du jour.

Les étapes sont les suivantes :

1. Ouvrez le Requêteur générique et sélectionnez la table des Destinataires **[!UICONTROL (nms:recipient)]**.
1. Dans la fenêtre **[!UICONTROL Données à extraire]**, sélectionnez les champs **[!UICONTROL Clé primaire]**, **[!UICONTROL Prénom]**, **[!UICONTROL Nom]** et **[!UICONTROL Email]**.

   ![](assets/query_editor_nveau_33.png)

1. Dans la fenêtre de tri, ordonnez les noms alphabétiquement.

   ![](assets/query_editor_nveau_34.png)

1. Dans la fenêtre **[!UICONTROL Filtrage des données]**, choisissez **[!UICONTROL Critères de filtrage]**.
1. Dans la fenêtre **[!UICONTROL Elément de la cible]**, la condition de filtrage qui permet d&#39;extraire de la base les profils qui n&#39;ont aucun log de tracking pour les 7 derniers jours est réalisée en deux étapes. En effet, l&#39;élément de collection que vous allez sélectionner est un lien n-n.

   * Tout d&#39;abord, sélectionnez l&#39;élément de collection (noeud orange) **[!UICONTROL Logs de diffusion des destinataires (broadlog)]** pour la première colonne **[!UICONTROL Valeur]**.

     ![](assets/query_editor_nveau_67.png)

     Sélectionnez l&#39;opérateur **[!UICONTROL n&#39;existent pas tel que]**. Il n&#39;y a pas de seconde valeur à sélectionner dans cette ligne.

   * Le contenu de la deuxième condition de filtrage dépend de la première. Ici, le **[!UICONTROL Date de l’événement]** le champ est proposé directement dans **[!UICONTROL Logs de diffusion des destinataires]** , car il existe un lien vers cette table.

     ![](assets/query_editor_nveau_36.png)

     Sélectionner **[!UICONTROL Date de l’événement]** par le **[!UICONTROL supérieur ou égal à]** opérateur. Sélectionner le **[!UICONTROL Il y a jours (7)]** valeur. Pour ce faire, cliquez sur **[!UICONTROL Modifier l’expression]** dans le **[!UICONTROL Valeur]** champ . Dans le **[!UICONTROL Type de formule]** fenêtre, sélectionner **[!UICONTROL Traitement sur les dates]** et **[!UICONTROL Date actuelle moins jours]**, en indiquant « 7 » comme valeur.

     ![](assets/query_editor_nveau_37.png)

     La condition de filtrage est paramétrée.

     ![](assets/query_editor_nveau_38.png)

1. Dans le **[!UICONTROL Formatage des données]** , modifiez la casse des noms de famille. Cliquez sur le lien **[!UICONTROL Nom]** ligne dans le **[!UICONTROL Transformation]** Colonne et sélection **[!UICONTROL Passer en majuscules]** dans le menu déroulant.

   ![](assets/query_editor_nveau_39.png)

1. Utilisez la fonction **[!UICONTROL Ajouter un champ calculé]** pour insérer une colonne dans la fenêtre de prévisualisation des données.

   Dans cet exemple, ajoutez un champ calculé avec les noms et prénoms des destinataires dans une seule colonne. Cliquez sur le lien **[!UICONTROL Ajout d’un champ calculé]** fonction. Dans le **[!UICONTROL Exporter la définition des champs calculés]** , saisissez un libellé et un nom interne, puis choisissez la **[!UICONTROL Expression JavaScript]** tapez . Saisissez ensuite l’expression suivante :

   ```
   var rep = source._firstName+" - "+source._lastName
   return rep
   ```

   ![](assets/query_editor_nveau_40.png)

   Clic **[!UICONTROL OK]**. Le **[!UICONTROL Formatage des données]** La fenêtre est configurée.

   Pour plus d&#39;informations sur l&#39;ajout de champs calculés, consultez cette section.

1. Le résultat s&#39;affiche dans la fenêtre **[!UICONTROL Prévisualisation des données]**. Les destinataires non contactés dans les 7 jours antérieurs à la date courante sont affichés. Ils sont ordonnés alphabétiquement. Les noms sont en majuscules. La colonne supplémentaire qui regroupe les prénoms et les noms est bien là.

   ![](assets/query_editor_nveau_41.png)
