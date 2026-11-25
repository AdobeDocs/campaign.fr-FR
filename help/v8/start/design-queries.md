---
title: Interrogation de la base de données Campaign
description: Découvrez comment créer des requêtes dans la console cliente Campaign
feature: Query Editor, Data Management
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: d34b6073-a7e7-443a-a6d8-e74ef10a67e8
TQID: 'https://experienceleague.adobe.com/-HhNQgwweCPn3ts3AAm6SjdFTxg-2zexCALMqS1Yjgc'
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
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: 8ab3ced33b95f977032d9f0ffccd1dc50c7a59e8
workflow-type: tm+mt
source-wordcount: '1180'
ht-degree: 16%
---
# Base de données Query Campaign

Les requêtes sont réalisées soit avec les champs disponibles de la table sélectionnée, soit à l&#39;aide d&#39;une formule.

Les étapes de construction d&#39;une requête dans Adobe Campaign sont les suivantes :

1. [Sélectionnez la table de travail](#step-1---choose-a-table).
1. [Sélectionnez les données à extraire](#step-2---choose-data-to-extract).
1. [Définissez le mode de tri des données](#step-3---sort-data).
1. [Définissez les options de filtrage des données](#step-4---filter-data).
1. [Configurer la mise en forme des données](#step-5---format-data).
1. [Prévisualiser les résultats de la requête](#step-6---preview-data).

Toutes ces étapes sont disponibles dans le [requêteur générique](query-editor.md). Lorsqu’une requête est créée dans un autre contexte, certaines étapes peuvent être manquantes. Pour en savoir plus sur les requêtes, consultez également la [documentation sur l&#39;activité de requête du workflow](../../automation/workflow/query.md).


## Etape 1 - Sélection de la table {#step-1---choose-a-table}

Pour interroger la base de données Campaign, ouvrez le **[Requêteur générique](query-editor.md)**, puis sélectionnez la table contenant les données à interroger dans la fenêtre **[!UICONTROL Type de document]**.

![Menu Outils avec Requêteur générique ouvrant la fenêtre Type de document , avec le schéma Destinataires dans la liste.](assets/query_editor_nveau_21.png)

Si nécessaire, filtrez les données à l’aide du champ de filtrage ou du bouton **[!UICONTROL Filtres]**.

## Etape 2 - Sélection des données à extraire {#step-2---choose-data-to-extract}

Dans l&#39;écran **[!UICONTROL Données à extraire]**, choisissez les champs que vous souhaitez inclure dans la sortie. Ces champs définissent les colonnes affichées dans les résultats.

Par exemple, vous pouvez sélectionner **[!UICONTROL Âge]**, **[!UICONTROL Clé de Principal]**, **[!UICONTROL Domaine d’e-mail]** et **[!UICONTROL Ville]**. La sortie sera structurée en fonction de cette sélection. Pour ajuster l’ordre des colonnes, utilisez les flèches bleues sur le côté droit de la fenêtre.

![Données à extraire de l’étape avec l’âge, la clé de Principal, le domaine d’e-mail et la ville ajoutés à la liste Colonnes de sortie.](assets/query_editor_nveau_01.png)

Vous pouvez modifier une expression en ajoutant une formule ou en appliquant un processus à une fonction d&#39;agrégat. Pour modifier une expression, cliquez sur le champ de colonne **[!UICONTROL Expression]**, puis sélectionnez **[!UICONTROL Modifier l’expression]**.

![Champ de colonne d&#39;expression dans les colonnes de sortie avec le bouton Modifier l&#39;expression en surbrillance.](assets/query_editor_nveau_97.png)

Vous pouvez regrouper les données affichées dans les colonnes de sortie. Pour ce faire, sélectionnez **[!UICONTROL Oui]** dans la colonne **[!UICONTROL Groupe]** de la fenêtre **[!UICONTROL Données à extraire]**. Les résultats seront ensuite agrégés en fonction de l’axe de regroupement sélectionné. Pour un exemple de requête utilisant le regroupement, consultez [Interrogation des informations de diffusion](../../automation/workflow/query-delivery-info.md).

![Données à extraire à l’étape avec la colonne Groupe mise en surbrillance, définir sur Non pour chaque colonne de sortie.](assets/query_editor_nveau_56.png)

* L&#39;option **[!UICONTROL Gérer les regroupements (GROUP BY + HAVING)]** vous permet de regrouper les résultats et d&#39;appliquer des conditions à ces groupes. Elle s’applique à tous les champs des colonnes de sortie. Par exemple, vous pouvez l’utiliser pour regrouper les valeurs d’une colonne de sortie, puis filtrer les résultats afin de récupérer uniquement des informations spécifiques, telles que les destinataires âgés de 35 à 50 ans.

  Pour plus d&#39;informations, consultez la section [Requête avec gestion des regroupements](../../automation/workflow/query-grouping-management.md).

L&#39;option **[!UICONTROL Supprimer les lignes en double (DISTINCT)]** élimine les lignes identiques de la sortie (dédupliquer). Par exemple, si vous sélectionnez **Nom**, **Prénom** et **E-mail** comme colonnes de sortie, tous les enregistrements ayant les mêmes valeurs dans les trois champs seront considérés comme des doublons. Une seule instance sera conservée dans les résultats, chaque contact n’apparaissant ainsi qu’une seule fois.

## Etape 3 - Tri des données {#step-3---sort-data}

La fenêtre **[!UICONTROL Tri]** vous permet de trier le contenu des colonnes. Utilisez les flèches pour modifier l’ordre des colonnes :

* Avec **[!UICONTROL Tri]**, le contenu de chaque colonne est ordonné de A à Z. Le contenu est ordonné par ordre croissant s&#39;il est chiffré.
* Le tri **[!UICONTROL décroissant]** organise le contenu de Z à A et dans l&#39;ordre décroissant. Cela s’avère utile pour consulter les ventes d’enregistrements, par exemple : les chiffres les plus élevés sont affichés en haut de la liste.

Dans cet exemple, les données seront triées en fonction de l&#39;âge des destinataires, du plus jeune au plus âgé.

![Étape de tri répertoriant l&#39;âge, la clé de Principal, le domaine de l&#39;e-mail et la ville, avec les colonnes de tri Tri et Descendant définies sur Non.](assets/query_editor_nveau_57.png)

## Etape 4 - Filtrage des données {#step-4---filter-data}

Le requêteur permet de filtrer les données pour affiner les résultats. Les filtres disponibles dépendent du tableau que vous interrogez.

![Étape de filtrage des données avec des conditions de filtrage sélectionnées dans la liste des filtres de restriction et les filtres utilisateur ci-dessous.](assets/query_editor_nveau_09.png)

Après avoir sélectionné **[!UICONTROL Conditions de filtrage]**, la section **[!UICONTROL Éléments de Target]** s’ouvre. Vous pouvez définir ici les règles de filtrage des données à collecter.

* Pour créer un nouveau filtre, choisissez les champs, les opérateurs et les valeurs nécessaires à la création de la condition. Vous pouvez également combiner plusieurs conditions, comme expliqué [sur cette page](filter-conditions.md).

* Pour réutiliser un filtre existant, cliquez sur le bouton **[!UICONTROL Ajouter]**, sélectionnez **[!UICONTROL Filtre prédéfini]** et choisissez le filtre de votre choix.

  ![Ajoutez un menu à l’étape Élément cible avec le filtre Prédéfini ouvert, répertoriant l’adresse e-mail Placée sur la liste bloquée et d’autres filtres.](assets/query_editor_15.png)

Les filtres créés dans le **[!UICONTROL Requêteur générique]** peuvent être réutilisés dans d&#39;autres applications de requête, et l&#39;inverse est également vrai. Pour enregistrer un filtre pour une utilisation ultérieure, cliquez sur l&#39;icône **[!UICONTROL Enregistrer]**.

>[!NOTE]
>
>La création et l&#39;utilisation des filtres sont présentées dans la section [Options de filtrage](filter-conditions.md).

Dans l&#39;exemple ci-dessous, pour ne récupérer que les destinataires de langue française, choisissez : &quot;langue des destinataires **égal à** FR&quot;.

![Conditions de filtrage sélectionnées, puis un élément Target avec la condition Langue égale à EN.](assets/query_editor_nveau_89.png)

>[!NOTE]
>
>Vous pouvez directement accéder à une option en saisissant la formule suivante dans le champ **Valeur** : **$(options:OPTION_NAME)**.

Cliquez sur l&#39;onglet **[!UICONTROL Aperçu]** pour afficher le résultat de la condition de filtrage. Dans ce cas, tous les destinataires anglophones sont affichés avec leur nom, prénom et adresse e-mail.

![Onglet Aperçu de l’étape Élément cible répertoriant les destinataires qui correspondent au filtre.](assets/query_editor_nveau_98.png)

Les utilisateurs maîtrisant le langage SQL peuvent cliquer sur **[!UICONTROL Requête SQL correspondante]** pour visualiser la requête en SQL.

![Lien de requête SQL générée ouvrant la requête SQL native générée à partir du filtre pour une langue égale à EN.](assets/query_editor_nveau_99.png)

## Etape 5 - Formatage des données {#step-5---format-data}

Après avoir configuré les filtres de restriction, la fenêtre **[!UICONTROL Formatage des données]** s&#39;ouvre. Dans cette fenêtre, vous pouvez réorganiser les colonnes de sortie, transformer les données et ajuster la casse des libellés des colonnes. Vous pouvez également appliquer des formules au résultat final en créant un champ calculé.

>[!NOTE]
>
>Pour plus d&#39;informations sur les types de champs calculés, consultez la section [Créer des champs calculés](filter-conditions.md#creating-calculated-fields).

Les colonnes non cochées sont masquées dans la fenêtre de prévisualisation des données.

![Étape de formatage des données répertoriant l&#39;âge, la clé de Principal, le domaine et la ville de l&#39;e-mail, avec la colonne Domaine de l&#39;e-mail décochée.](assets/query_editor_nveau_10.png)

La colonne **[!UICONTROL Transformation]** permet de modifier la casse du libellé d&#39;une colonne. Sélectionnez une colonne puis cliquez dans la colonne **[!UICONTROL Transformation]**. Les modifications possibles sont :

* **[!UICONTROL Passer en minuscules]**,
* **[!UICONTROL Passer en majuscules]**,
* **[!UICONTROL Première lettre en majuscule]**.

![Liste déroulante Transformation avec Aucun, Passer en minuscules, Passer en majuscules et Première lettre en majuscule.](assets/query_editor_nveau_42.png)

## Etape 6 - Prévisualisation des données {#step-6---preview-data}

La fenêtre **[!UICONTROL Aperçu des données]** marque la dernière étape du processus de requête. Cliquez sur **[!UICONTROL Démarrer l&#39;aperçu des données]** pour consulter vos résultats, qui peuvent être affichés en colonnes ou au format XML. Pour examiner la requête SQL sous-jacente, ouvrez l&#39;onglet **[!UICONTROL Requêtes SQL générées]**. Cette étape vous permet de vérifier que votre requête se comporte comme prévu avant de l’utiliser davantage.

Dans cet exemple, les données sont triées selon l&#39;âge des destinataires ciblés et dans un ordre croissant.

![Étape de prévisualisation des données : commencez la prévisualisation des données pour remplir un tableau des valeurs Âge, Clé de Principal et Ville.](assets/query_editor_nveau_11.png)

>[!NOTE]
>
>Comme pour toutes les listes disponibles dans la console, seules les 200 premières lignes sont affichées par défaut dans la fenêtre **[!UICONTROL Aperçu des données]**. Pour modifier ce paramètre, saisissez un nombre dans la zone **[!UICONTROL Lignes à afficher]** et cliquez sur **[!UICONTROL Démarrer l&#39;aperçu des données]**. [En savoir plus](../config/ui-settings.md#customize-lists)



**Rubriques connexes :**

* [Activité de requête de workflow](../../automation/workflow/query.md)
* [Effectuer une requête sur la table des destinataires](../../automation/workflow/querying-recipient-table.md)
* [Critères de filtrage](filter-conditions.md)
