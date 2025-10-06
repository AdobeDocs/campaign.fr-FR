---
product: campaign
title: Requête
description: En savoir plus sur l’activité de workflow de requête
feature: Workflows, Targeting Activity, Query Editor
role: User, Data Engineer
exl-id: 717e4f7c-3a8e-4930-9a06-b7412d6e1675
version: Campaign v8, Campaign Classic v7
source-git-commit: 95c944963feee746a2bb83a85f075134c91059d1
workflow-type: tm+mt
source-wordcount: '1663'
ht-degree: 94%

---

# Requête{#query}



## Création dʼune requête {#creating-a-query}

Une requête permet de sélectionner une cible selon des critères. Vous pouvez associer un code segment au résultat de la requête et y insérer des données additionnelles.
Découvrez comment créer des requêtes par le biais de cas d’utilisation dans [cette section](querying-recipient-table.md). Consultez également la section à propos du [Query editor](../../v8/start/query-editor.md).

![](assets/query-activity.png){width="70%" align="center" zoomable="yes"}

>[!NOTE]
>
>L’interface utilisateur web d’Adobe Campaign dispose d’un puissant outil de modélisation des requêtes qui simplifie le processus de filtrage des bases de données afin de sélectionner des cibles spécifiques en fonction de divers critères, ce qui vous permet de créer et de gérer plus facilement vos requêtes. Pour en savoir plus sur le concepteur de requête de l’interface d’utilisation web, reportez-vous à la [documentation de l’interface d’utilisation d’Adobe Campaign Web](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/query-database/query-modeler-overview){target=_blank}.

Le lien **[!UICONTROL Editer la requête...]** permet de définir le type de ciblage, les restrictions et les critères de sélection de la population de la manière suivante :

1. Sélectionnez la dimension de ciblage et de filtrage. Par défaut, la cible est sélectionnée parmi les destinataires. La liste des filtres de restriction est la même que celle utilisée lors du ciblage d&#39;une diffusion.

   La dimension de ciblage correspond au type d&#39;élément sur lequel on va travailler, par exemple la population ciblée par l&#39;opération.

   La dimension de filtrage permet d&#39;aller chercher ces éléments, par exemple les informations liées à la personne ciblée (les contrats, les soldes de comptes, etc.).

   Voir à ce sujet la section [Dimension de ciblage et dimension de filtrage](targeting-workflows.md#targeting-and-filtering-dimensions).

   ![](assets/targeting-filtering-dimensions.png){width="70%" align="center" zoomable="yes"}

   Une requête peut être basée sur les données de la transition entrante, le cas échéant, en sélectionnant **[!UICONTROL Schéma temporaire]** lors du choix des dimensions de ciblage et de filtrage.

   ![](assets/query_temporary_table.png){width="70%" align="center" zoomable="yes"}

1. Définissez les populations à l’aide de l’assistant. Les champs à renseigner peuvent différer en fonction du type de cible. Vous pouvez prévisualiser la population ciblée avec vos critères actuels à l’aide de l’onglet **[!UICONTROL Aperçu]**.

   ![](assets/query-sample.png){width="70%" align="center" zoomable="yes"}

1. Vous devrez ajouter des critères de filtrage manuellement si vous avez sélectionné **[!UICONTROL Critères de filtrage]** à l’étape 1 ou via l’option **[!UICONTROL Filtres]** > **[!UICONTROL Filtre avancé...]**.

   Vous pouvez également ajouter des conditions de regroupement de données en cochant la case correspondante. Pour cela, la dimension de filtrage doit impérativement être différente de la dimension de ciblage de la requête. Pour plus d’informations sur les regroupements, consultez cette [section](query-grouping-management.md).

   Vous pouvez également ajouter des critères supplémentaires en vous aidant du Créateur d’expressions et les combiner grâce aux options logiques ET, OU et SAUF.

   Enregistrez votre filtre si vous souhaitez le réutiliser ultérieurement.

## Ajout de données {#adding-data}

Les colonnes additionnelles permettent de collecter des informations supplémentaires sur la population ciblée, par exemple ses numéros de contrats, ses abonnements à des newsletters ou son origine. Ces données peuvent être stockées dans la base de données Adobe Campaign ou dans une base externe.

Le lien **[!UICONTROL Ajouter des données...]** permet de sélectionner les données additionnelles à collecter.

![](assets/wf_add_data_link.png){width="70%" align="center" zoomable="yes"}

Sélectionnez d&#39;abord le type de données à ajouter :

![](assets/wf_add_data_1st_option.png){width="70%" align="center" zoomable="yes"}

* Sélectionnez **[!UICONTROL Données liées à la dimension de ciblage]** pour sélectionner des données de la base Adobe Campaign.
* Sélectionnez **[!UICONTROL Données externes]** pour ajouter des données provenant d’une base externe. Cette option n’est disponible que si vous avez acquis l’option **Federated Data Access**. Pour plus dʼinformations, consultez la section [Accès à une base de données externe (FDA)](accessing-an-external-database-fda.md).
* Sélectionnez l’option **[!UICONTROL Une proposition d’offre]** pour ajouter un ensemble de colonnes permettant de stocker la meilleure proposition générée par le moteur d’offres. Cette option n’est disponible que si vous avez acquis le module **Interaction**.

Si aucun module optionnel n&#39;est installé sur la plateforme, cette étape n&#39;est pas affichée. Vous accédez directement à l&#39;étape suivante.

Pour ajouter des données de la base Adobe Campaign :

1. Sélectionnez le type de données que vous souhaitez ajouter. Il peut s&#39;agir de données appartenant à la dimension de filtrage ou de données stockées dans des tables liées.

   ![](assets/query_add_columns.png){width="70%" align="center" zoomable="yes"}

1. Lorsque les données appartiennent à la dimension de filtrage de la requête, il suffit de les sélectionner dans la liste des champs disponibles afin de les faire apparaître parmi les colonnes de sortie.

   ![](assets/wf_add_data_field_selection.png){width="70%" align="center" zoomable="yes"}

   Vous pouvez ajouter :

   * Un champ calculé à partir de données issues de la population ciblée ou un agrégat (nombre d’achats en attente au cours du dernier mois, montant moyen d’un ticket de caisse, etc.). Un exemple est proposé dans la section [Sélection des données](targeting-workflows.md#selecting-data).
   * Un nouveau champ, créé à partir du bouton **[!UICONTROL Ajouter]** situé à droite de la liste des colonnes de sortie.

     Vous pouvez également ajouter une collection d’informations, par exemple une liste de contrats, les 5 dernières diffusions, etc. Les collections correspondent à des champs dont les valeurs peuvent être multiples pour un même profil (relation 1-N). Pour plus dʼinformations, consultez la section [Modification des données additionnelles](targeting-workflows.md#editing-additional-data).

Pour ajouter une collection d’informations liées à une population ciblée, procédez comme suit :

1. Sélectionnez l&#39;option **[!UICONTROL Données liées à la dimension de filtrage]** à la première étape de l&#39;assistant :
1. Sélectionnez la table contenant les informations à collecter et cliquez sur le bouton **[!UICONTROL Suivant.]**

   ![](assets/wf_add_data_linked_table.png){width="70%" align="center" zoomable="yes"}

1. Au besoin, indiquez le nombre d&#39;éléments de la collection que vous souhaitez conserver en sélectionnant une des valeurs du champ **[!UICONTROL Données collectées]**. Par défaut, toutes les lignes de la collection sont récupérées, puis filtrées selon les conditions définies à l&#39;étape suivante.

   * Si un seul élément de la collection correspond aux conditions de filtrage définies à l&#39;étape suivante, sélectionnez **[!UICONTROL Ligne unique]** dans le champ **[!UICONTROL Données collectées]**.

     >[!IMPORTANT]
     >
     >Ce mode optimise la requête SQL générée grâce à une jointure directe sur les éléments de la collection.
     >
     >Si la condition initiale n&#39;est pas respectée, le résultat peut être erroné (lignes manquantes ou doublons).

   * Si vous choisissez de récupérer plusieurs lignes (**[!UICONTROL Limiter le nombre de lignes]**), vous pouvez indiquer le nombre de lignes à collecter.
   * Si les colonnes collectées contiennent des agrégats, par exemple le nombre de sinistres déclarés, la moyenne des dépenses sur un site, etc., vous pouvez utiliser la valeur **[!UICONTROL Agrégats]**.

   ![](assets/query_add_collection_param.png){width="70%" align="center" zoomable="yes"}

1. Spécifiez la sous-sélection de la collection.

   ![](assets/query_add_columns_collection_filter.png){width="70%" align="center" zoomable="yes"}

1. Si vous avez sélectionné l&#39;option **[!UICONTROL Limiter le nombre de lignes]**, définissez l&#39;ordre de tri des données collectées. Lorsque le nombre de lignes collectées est supérieur au nombre de lignes à conserver que vous avez indiqué, l&#39;ordre de tri permet de définir quelles sont les lignes à conserver.

## Exemple : ciblage sur des attributs destinataires simples {#example--targeting-on-simple-recipient-attributes}

Dans l&#39;exemple suivant, la requête cherchera à identifier les hommes de 18 à 30 ans et vivant en France. Cette requête pourra par exemple être utilisée dans un workflow visant à leur faire parvenir une offre qui leur est spécialement réservée.

>[!NOTE]
>
>D&#39;autres exemples de requête sont présentés dans [cette section](querying-recipient-table.md).

1. Nommez votre requête puis sélectionnez le lien **[!UICONTROL Editer la requête...]**.
1. Sélectionnez **[!UICONTROL Critères de filtrage]** dans la liste des types de filtres disponibles.
1. Renseignez les différents critères correspondant à la cible souhaitée. Ici, les critères sont combinés à l’aide de l’opérateur ET. Pour faire partie de la sélection, ils devront donc réunir les quatre conditions suivantes :

   * Les destinataires dont la civilité est &quot;M.&quot; (également possible en utilisant le champ **Genre** et la valeur **Masculin**).
   * Les destinataires ayant moins de 30 ans.
   * Les destinataires ayant plus de 18 ans.
   * Les destinataires dont le pays de résidence est la France.

   ![](assets/query_example.png){width="70%" align="center" zoomable="yes"}

   Vous pouvez visualiser le code SQL correspondant à votre combinaison de critères :

   ![](assets/query_example_sql.png){width="70%" align="center" zoomable="yes"}

1. Affichez un aperçu des destinataires correspondant à votre requête via l&#39;onglet correspondant afin de vérifier que vos critères sont correctement renseignés :

   ![](assets/query_example_preview.png){width="70%" align="center" zoomable="yes"}

1. Sauvegardez éventuellement vos filtres pour pouvoir les réutiliser ultérieurement puis cliquez sur **[!UICONTROL Terminer]** > **[!UICONTROL Ok]**.
1. Poursuivez l’édition de votre workflow en y ajoutant d’autres activités. Après le lancement et une fois l’étape de requête précédente terminée, le nombre de personnes destinataires trouvées s’affiche. Vous pouvez afficher d’autres détails à l’aide du menu contextuel de la souris (cliquez avec le bouton droit de la souris sur la transition > **[!UICONTROL Afficher la cible...]**).

   ![](assets/query_example_result.png){width="70%" align="center" zoomable="yes"}

## Paramètres de sortie {#output-parameters}

* tableName
* schéma
* recCount

Ce jeu de trois valeurs identifie la population ciblée par la requête. **[!UICONTROL tableName]** est le nom de la table qui enregistre les identifiants de la cible, **[!UICONTROL schema]** est le schéma de la population (généralement nms:recipient) et **[!UICONTROL recCount]** est le nombre d&#39;éléments dans la table.

Cette valeur correspond au schéma de la table de travail. Ce paramètre est valide pour toutes les transitions avec **[!UICONTROL tableName]** et **[!UICONTROL schema]**.

## Optimisation des requêtes {#optimizing-queries}

La section ci-dessous présente les bonnes pratiques pour optimiser les requêtes exécutées dans Adobe Campaign, ce qui permet de limiter la charge de travail sur la base de données et d’améliorer l’expérience utilisateur.

### Jointures et index {#joins-and-indexes}

* Les requêtes efficaces reposent sur des index.
* Utilisez un index pour toutes les jointures.
* La définition de liens sur le schéma détermine les conditions de jointure. La table liée doit avoir un index unique sur la clé primaire et la jointure doit se trouver sur ce champ.
* Effectuez des jointures en définissant des clés sur des champs numériques au lieu de champs de chaîne.
* Évitez d’effectuer des jointures externes. Dans la mesure du possible, utilisez l’enregistrement Zero ID pour obtenir la fonctionnalité de jointure externe.
* Utilisez le type de données approprié pour les jointures.

  Assurez-vous que la clause `where` est du même type que le champ.

  Il existe une erreur courante : `iBlacklist='3'` où `iBlacklist` est un champ numérique et `3` correspond à une valeur de texte.

  Assurez-vous de connaître le plan d’exécution de votre requête. Évitez les analyses de table complètes, en particulier pour les requêtes en temps réel ou quasi temps réel qui s’exécutent toutes les minutes.

### Fonctions {#functions}

* Attention aux fonctions comme `Lower(...)`. Si vous avez recours à la fonction Lower, l’index n’est pas utilisé.
* Vérifiez soigneusement les requêtes contenant les instructions « like », « upper » ou « lower ». Appliquez « upper » à la saisie utilisateur et non au champ de base de données.

### Dimensions de filtrage {#filtering-dimensions}

Utilisez la dimension de filtrage de la requête au lieu de l’opérateur « exists such as ».

![](assets/optimize-queries-filtering.png){width="70%" align="center" zoomable="yes"}

Dans les requêtes, les conditions « exists such as » des filtres ne sont pas efficaces. Elles constituent l’équivalent d’une sous-requête dans SQL :

`select iRecipientId from nmsRecipient where iRecipientId IN (select iRecipientId from nmsBroadLog where (...))`

Il est recommandé d’utiliser plutôt la dimension de filtrage de la requête :

![](assets/optimize-queries-filtering2.png){width="70%" align="center" zoomable="yes"}

L’équivalent de la dimension de filtrage dans SQL est la jointure interne :

`select iRecipientId from nmsRecipient INNER JOIN nmsBroadLog ON (...)`

Pour plus d’informations sur les dimensions de filtrage, consultez [cette section](build-a-workflow.md#targeting-and-filtering-dimensions).

### Architecture {#architecture}

* Créez une plateforme de développement avec des volumes, des paramètres et une architecture similaires à ceux de la plateforme de production.
* Utilisez les mêmes valeurs pour les environnements de développement et de production. Dans la mesure du possible, les éléments suivants doivent être identiques :

   * Système d&#39;exploitation,
   * Version,
   * Données,
   * Application,
   * Volumes.

  >[!NOTE]
  >
  >Une fonctionnalité opérationnelle dans un environnement de développement peut ne pas l’être dans un environnement de production. Les données peuvent en effet être différentes de l’un à l’autre. Essayez d’identifier les principales différences pour anticiper les risques et préparer des solutions.

* Effectuez des configurations qui correspondent aux volumes cible. Les gros volumes nécessitent des configurations spécifiques. Une configuration adaptée pour 100 000 destinataires peut ne pas fonctionner pour 10 000 000.

  Pensez à la façon dont le système va évoluer une fois mis en service. Si un élément fonctionne à petite échelle, il ne sera pas nécessairement adapté à de plus grands volumes. Les tests doivent être effectués avec des volumes similaires à ceux de la production. Vous devez également évaluer l’incidence des évolutions de volumes (nombre d’appels, taille de la base de données) aux heures et aux jours de pointe, et pendant toute la durée du projet.
