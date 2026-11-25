---
product: campaign
title: Requête avec une relation multiple-à-multiple
description: Découvrez comment exécuter des requêtes à l’aide d’une relation multiple-à-multiple
feature: Query Editor
role: User, Developer
version: Campaign v8, Campaign Classic v7
exl-id: c320054d-7f67-4b12-aaa7-785945bf0c18
TQID: 'https://experienceleague.adobe.com/BnWR5Pz41h-CeMuyGKXKBmhRHGcuSShWerJpOWAN7W0'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: f5293531-9312-4099-bfa3-9e67df6a8750
    internal-label: Query Editor
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 77%
---
# Requête avec une relation multiple-à-multiple {#querying-using-a-many-to-many-relationship}



Dans cet exemple, vous allez récupérer les personnes destinataires non contactées au cours des 7 derniers jours. Cette requête concerne toutes les diffusions.

Cet exemple indique par ailleurs comment paramétrer un filtrage découlant du choix d’un élément de collection (ou nœud orange). Les éléments de collection sont disponibles dans la fenêtre **[!UICONTROL Champ à sélectionner]**.

* Quelle table doit-on sélectionner ?

  Table des personnes destinataires (**nms:recipient**)

* Quels sont les champs à sélectionner en colonne de sortie ?

  Clé primaire, Nom, Prénom et Email.

* En fonction de quels critères seront filtrées les informations ?

  En fonction des logs de diffusion des destinataires. Ils remontent jusqu&#39;à 7 jours avant la date du jour.

Les étapes sont les suivantes :

1. Ouvrez le requêteur générique et choisissez la table Personnes destinataires **[!UICONTROL (nms:recipient)]**.
1. Dans la fenêtre **[!UICONTROL Données à extraire]**, sélectionnez les champs **[!UICONTROL Clé primaire]**, **[!UICONTROL Prénom]**, **[!UICONTROL Nom]** et **[!UICONTROL Email]**.

   ![Fenêtre de données à extraire avec clé de Principal, prénom, nom et e-mail répertoriés comme colonnes de sortie](assets/query_editor_nveau_33.png)

1. Dans la fenêtre de tri, ordonnez les noms alphabétiquement.

   ![Fenêtre de tri avec l&#39;option Trier définie sur Oui pour la colonne Nom](assets/query_editor_nveau_34.png)

1. Dans la fenêtre **[!UICONTROL Filtrage des données]**, choisissez **[!UICONTROL Critères de filtrage]**.
1. Dans la fenêtre **[!UICONTROL Élément de la cible]**, la condition de filtrage qui permet d’extraire les profils qui n’ont aucun log de tracking sur les 7 derniers jours est réalisée en deux étapes. L’élément que vous devez sélectionner est un lien multiple à multiple.

   * Tout d&#39;abord, sélectionnez l&#39;élément de collection (noeud orange) **[!UICONTROL Logs de diffusion des destinataires (broadlog)]** pour la première colonne **[!UICONTROL Valeur]**.

     ![Champ à sélectionner pour la fenêtre avec l&#39;élément de collection Logs de diffusion des destinataires (broadLog) sélectionné](assets/query_editor_nveau_67.png)

     Sélectionnez l’opérateur **[!UICONTROL n’existent pas en tant que]**. Il n’est pas nécessaire de sélectionner de seconde valeur dans cette ligne.

   * Le contenu de la seconde condition de filtrage découle directement du choix de la première. Ici, le champ **[!UICONTROL Date de l&#39;événement]** est directement proposé dans la table **[!UICONTROL Logs de diffusion des destinataires]** car un lien s&#39;opère vers cette table.

     ![Champ à sélectionner pour la fenêtre répertoriant les champs des logs de diffusion des destinataires, avec la date de l’événement (@eventDate) mise en surbrillance](assets/query_editor_nveau_36.png)

     Sélectionnez **[!UICONTROL Date de l&#39;événement]** avec l&#39;opérateur **[!UICONTROL supérieur ou égal à]**. Sélectionnez la valeur **[!UICONTROL DaysAgo (7)]**. Pour cela, cliquez sur **[!UICONTROL Editer l&#39;expression]** dans le champ **[!UICONTROL Valeur]**. Dans la fenêtre **[!UICONTROL Type de formule]**, sélectionnez **[!UICONTROL Traitement sur les dates]** puis **[!UICONTROL Date courante moins n jours]** et saisissez la valeur &quot;7&quot;.

     ![Fenêtre de type formule avec Traitement aux dates et Date actuelle moins n jours définie sur 7](assets/query_editor_nveau_37.png)

     La condition de filtrage est paramétrée.

     ![Fenêtre de l’élément cible avec le filtre : les logs de diffusion n’existent pas, par exemple la date de l’événement est le ou après 7 jours avant](assets/query_editor_nveau_38.png)

1. Dans la fenêtre **[!UICONTROL Formatage des données]**, modifiez la casse des noms : ils doivent s&#39;afficher en majuscules. Cliquez sur la ligne du **[!UICONTROL Nom]** dans la colonne **[!UICONTROL Transformation]** et choisissez **[!UICONTROL Passer en majuscules]** dans le menu déroulant.

   ![Fenêtre Formatage des données avec la liste Transformation pour le nom, Passer à l&#39;option en majuscules mise en surbrillance](assets/query_editor_nveau_39.png)

1. Utilisez la fonction **[!UICONTROL Ajouter un champ calculé]** pour insérer une colonne dans la fenêtre de prévisualisation des données.

   Dans cet exemple, ajoutez un champ calculé qui regroupe le prénom et le nom des destinataires dans une seule colonne. Cliquez sur **[!UICONTROL Ajouter un champ calculé]**. Dans la fenêtre **[!UICONTROL Définition d&#39;un champ calculé d&#39;export]**, saisissez un libellé et un nom interne puis choisissez le type **[!UICONTROL Expression JavaScript]**. Entrez l&#39;expression ci-dessous :

   ```
   var rep = source._firstName+" - "+source._lastName
   return rep
   ```

   ![Éditeur d&#39;expression JavaScript pour la colonne Prénom - Nom avec le script qui concatène les deux champs](assets/query_editor_nveau_40.png)

   Cliquez sur **[!UICONTROL OK]**. La fenêtre **[!UICONTROL Formatage des données]** est paramétrée.

   Pour plus d&#39;informations sur l&#39;ajout de champs calculés, consultez cette section.

1. Le résultat s’affiche dans la fenêtre **[!UICONTROL Aperçu des données]**. Les personnes destinataires qui n’ont pas été contactées au cours des 7 derniers jours sont affichées par ordre alphabétique. Les noms sont affichés en majuscules et la colonne contenant les noms et prénoms a été créée.

   ![Fenêtre de prévisualisation des données répertoriant les destinataires avec la colonne Prénom - Nom ajoutée](assets/query_editor_nveau_41.png)
