---
product: campaign
title: Effectuer un calcul d'agrégats
description: Découvrez comment effectuer des calculs d'agrégats dans des requêtes
feature: Workflows
role: User, Developer
version: Campaign v8, Campaign Classic v7
exl-id: 00e564b5-3c8e-45d4-b240-c872a8b8ccb6
TQID: 'https://experienceleague.adobe.com/ubtfw1irqKiD8mrRqD2L3UI-kGwhdBiSmBTjIfp-4NE'
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
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 100%
---
# Effectuer un calcul d&#39;agrégats {#performing-aggregate-computing}

Dans cet exemple, vous allez comptabiliser le nombre de destinataires domiciliés à Paris, en fonction de leur genre.

* Quelle table doit-on sélectionner ?

  Table des personnes destinataires (**nms:recipient**)

* Quels sont les champs à sélectionner en colonne de sortie ?

  Clé primaire (avec comptage) et Genre.

* En fonction de quels critères seront filtrées les informations ?

  En fonction des destinataires domiciliés à Paris.

Pour réaliser cet exemple, les étapes sont les suivantes :

1. Dans **[!UICONTROL Données à extraire]**, définissez un comptage de la clé primaire (comme dans l&#39;exemple précédent). Ajoutez le champ **[!UICONTROL Genre]** en colonne de sortie. Cochez l&#39;option **[!UICONTROL Grouper]** de la colonne **[!UICONTROL Genre]**. Ainsi, les destinataires seront regroupés par genre.

   ![](assets/query_editor_nveau_27.png)

1. Dans la fenêtre **[!UICONTROL Tri]**, cliquez sur **[!UICONTROL Suivant]** : aucun tri n&#39;est nécessaire dans cet exemple.
1. Paramétrez le filtrage des données. Ici, vous allez restreindre la sélection aux personnes contacts domiciliées à Paris.

   ![](assets/query_editor_22.png)

   >[!NOTE]
   >
   >Les valeurs sont sensibles à la casse. Si la valeur « paris » est saisie dans la condition sans majuscule et si la liste des personnes destinataires comporte le terme « Paris » avec une majuscule, la requête échoue.

1. Dans la fenêtre **[!UICONTROL Formatage des données]**, cliquez sur **[!UICONTROL Suivant]** : aucun formatage n&#39;est nécessaire dans cet exemple.
1. Dans la fenêtre de prévisualisation, cliquez sur **[!UICONTROL Lancer la prévisualisation des données]**.

   Il y a trois valeurs distinctes dans un tri par genre : **2** correspond au genre féminin, **1** au genre masculin et la valeur **0** apparaît lorsque le genre est inconnu. Dans cet exemple, la liste comporte 10 femmes, 16 hommes et 2 personnes dont le genre n’est pas renseigné.

   ![](assets/query_editor_agregat_04.png)
