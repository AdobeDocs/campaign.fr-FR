---
title: Paramètres de l’interface Campaign
description: Découvrez comment personnaliser les paramètres de l’interface Campaign.
feature: Application Settings
role: Admin, Developer
level: Beginner
exl-id: 9fa6fc42-45be-41db-9b4a-19b3b0c40dcd
source-git-commit: fbde111671fb972f6c96ba45eba4c8a88dbcac64
workflow-type: tm+mt
source-wordcount: '1083'
ht-degree: 97%

---

# Paramètres de l’interface utilisateur de Campaign {#ui-settings}

## Unités par défaut {#default-units}

Dans Adobe Campaign, pour les champs qui expriment une durée (par exemple la période de validité des ressources, la date limite de validation d’une tâche, etc.), les valeurs peuvent être exprimées dans les **unités** suivantes :

* **[!UICONTROL s]** pour les secondes
* **[!UICONTROL mn]** pour les minutes
* **[!UICONTROL h]** pour les heures
* **[!UICONTROL j]** pour les jours

## Personnaliser l&#39;explorateur Campaign{#customize-explorer}

Vous pouvez ajouter des dossiers à l&#39;explorateur Campaign, créer des vues et attribuer des autorisations.

Découvrez comment gérer les dossiers et les vues dans [cette page](../audiences/folders-and-views.md)

## Gérer et personnaliser des listes {#customize-lists}

Dans la console cliente Campaign, les données sont affichées sous forme de listes. Vous pouvez adapter ces listes à vos besoins. Vous pouvez par exemple ajouter des colonnes, filtrer les données, comptabiliser les enregistrements, enregistrer et partager vos paramètres.

En outre, vous pouvez créer et enregistrer des filtres.  Pour en savoir plus sur les filtres, consultez [cette page](../audiences/create-filters.md).

### Nombre d’enregistrements {#number-of-records}

Par défaut, Adobe Campaign charge en mémoire les 200 premiers enregistrements d&#39;une liste. Par conséquent, l&#39;affichage ne propose pas nécessairement l&#39;intégralité des enregistrements de la table dont vous affichez le contenu. Vous pouvez lancer un décompte du nombre d&#39;enregistrements de la liste et déclencher le chargement en mémoire d&#39;enregistrements supplémentaires.

En bas à droite de l&#39;écran de liste, un **compteur** indique le nombre d&#39;enregistrements chargés en mémoire par rapport au nombre total d&#39;enregistrements dans la base (après application de tous les filtres éventuels) :

![Afficher le nombre total d’enregistrements dans une liste](assets/number-of-records.png)

Si un point d’interrogation apparaît à la place du nombre de droite, par exemple `240/?`, cliquez sur le compteur pour lancer le calcul.

Pour charger et afficher des enregistrements supplémentaires, cliquez sur **[!UICONTROL Continuer le chargement]**. Par défaut, 200 enregistrements sont chargés. Pour modifier le nombre d’enregistrements chargés par défaut, cliquez sur l’icône **[!UICONTROL Configurer la liste]**, en bas à droite de la liste. Dans la fenêtre de configuration de la liste, cliquez sur **[!UICONTROL Paramètres avancés]** (en bas à gauche) et modifiez le nombre de lignes à récupérer.

Si vous souhaitez charger l’intégralité des enregistrements, cliquez dans la liste avec le bouton droit et sélectionnez **[!UICONTROL Tout charger]**.

>[!CAUTION]
>
>Lorsqu’une liste contient un grand nombre d’enregistrements, le chargement complet peut prendre un certain temps.
>

### Ajouter et supprimer des colonnes {#add-columns}

Pour chaque liste, la configuration des colonnes intégrée peut être adaptée pour afficher davantage d’informations ou masquer les colonnes inutilisées.

Lorsque des données sont visibles dans le détail d’un enregistrement, cliquez avec le bouton droit sur le champ et sélectionnez **[!UICONTROL Ajouter dans la liste]**.

![Ajouter un champ dans la liste](assets/add-in-the-list.png)

La colonne est ajoutée à droite des colonnes déjà affichées.

![Ajouter une colonne de champ](assets/add-a-column.png)

Vous pouvez également utiliser l’écran de configuration de la liste pour ajouter et supprimer des colonnes :

1. Dans une liste d’enregistrements, cliquez sur l’icône **[!UICONTROL Configurer la liste]** dans la section inférieure droite.
1. Faites un double clic sur les champs à ajouter dans la liste **[!UICONTROL Champs disponibles]** : ils sont ajoutés à la liste **[!UICONTROL Colonnes de sortie]**.

   ![Écran de configuration de la liste](assets/list-config-screen.png)


   >[!NOTE]
   >
   >Par défaut, les champs avancés ne sont pas affichés. Pour les afficher, cliquez sur l’icône **Afficher les champs avancés**, dans la section inférieure droite de la liste des champs disponibles.
   >
   >Les champs sont identifiés par des icônes spécifiques : champs SQL, tables liées, champs calculés, etc. Pour chaque champ sélectionné, la description est affichée sous la liste des champs disponibles.
   >

1. Utilisez les flèches haut/bas pour modifier l’**ordre d’affichage**.

1. Cliquez sur **[!UICONTROL OK]** pour valider la configuration et visualiser le résultat.

Si vous devez supprimer une colonne, sélectionnez-la et cliquez sur l’icône **Corbeille**.

Vous pouvez utiliser l’icône **[!UICONTROL Répartition des valeurs]** pour visualiser la répartition des valeurs du champ sélectionné dans le dossier courant.

![](assets/value-distribution.png)


### Créer une nouvelle colonne {#create-a-new-column}

Vous pouvez créer de nouvelles colonnes pour afficher des champs supplémentaires dans la liste.

Pour créer une colonne, procédez comme suit :

1. Dans une liste d’enregistrements, cliquez sur l’icône **[!UICONTROL Configurer la liste]** dans la section inférieure droite.
1. Cliquez sur l’icône **[!UICONTROL Ajouter]** pour afficher un nouveau champ dans la liste.
1. Configurez le champ à ajouter à la colonne.


### Affichage des données dans des sous-dossiers {#display-sub-folders-records}

Les listes peuvent afficher :

* Tous les enregistrements contenus dans le dossier sélectionné (par défaut)
* Tous les enregistrements contenus dans le dossier sélectionné et ses sous-dossiers

Pour basculer d’un mode d’affichage à l’autre, cliquez sur l’icône **[!UICONTROL Afficher les sous-niveaux]** dans la barre d’outils Campaign.

### Enregistrer une configuration de liste {#saving-a-list-configuration}

Les configurations de liste sont définies localement pour chaque utilisateur et utilisatrice. Lorsque le cache local est effacé, les configurations locales sont désactivées.

Par défaut, les paramètres s’appliquent à toutes les listes avec le type de dossier correspondant. Lorsque vous modifiez l’affichage de la liste de destinataires à partir d’un dossier, cette configuration est appliquée à tous les autres dossiers de destinataires.

Vous pouvez enregistrer plusieurs configurations à appliquer à différents dossiers du même type. La configuration est enregistrée avec les propriétés du dossier contenant les données et peut être réappliquée.

Pour enregistrer cette configuration de liste en vue de la réutiliser, procédez comme suit :

1. Dans l’explorateur, faites un clic droit sur le dossier contenant les données affichées.
1. Sélectionnez **[!UICONTROL Propriétés]**.
1. Cliquez sur **[!UICONTROL Paramètres avancés]** et indiquez un nom dans le champ **[!UICONTROL Configuration]**.
1. Cliquez sur **[!UICONTROL OK]**, puis sur **[!UICONTROL Enregistrer]**.

Vous pouvez ensuite appliquer cette configuration à tout autre dossier du même type. Pour en savoir plus sur les dossiers, consultez [cette page](../audiences/folders-and-views.md).

### Exporter une liste {#exporting-a-list}

Pour exporter les données d’une liste, vous devez utiliser un assistant d’export. Pour y accéder, sélectionnez les éléments de la liste à exporter, cliquez avec le bouton droit de la souris et choisissez **[!UICONTROL Exporter...]**.

<!--The use of the import and export functions is explained in [Generic imports and exports](../../platform/using/about-generic-imports-exports.md).-->

>[!CAUTION]
>
>Les éléments d’une liste ne doivent pas être exportés via la fonction Copier/Coller.

### Tri d’une liste {#sorting-a-list}

Les listes peuvent contenir un grand nombre de données. Vous pouvez trier ces données ou appliquer des filtres simples ou avancés. Le tri permet d&#39;afficher les données dans un ordre ascendant ou descendant, tandis que les filtres permettent de définir et de combiner des critères afin de n&#39;afficher qu&#39;une sélection de données.

Cliquez sur l&#39;en-tête de la colonne pour appliquer un tri ascendant, un tri descendant ou annuler le tri des données. Une flèche bleue devant le libellé de la colonne indique qu&#39;un tri est actif et l&#39;ordre du tri. Un tiret rouge devant le libellé de la colonne indique que le tri est appliqué à des données indexées depuis la base de données. Ce mode de tri permet d&#39;optimiser les actions de tri.

Vous pouvez également paramétrer le tri ou combiner les critères de tri. Pour cela, procédez comme suit :

1. Cliquez sur **[!UICONTROL Configurer la liste]** en bas à droite de la liste.
1. Dans la fenêtre de configuration de la liste, cliquez sur l&#39;onglet **[!UICONTROL Tris]**.
1. Sélectionnez les champs à trier et le sens du tri (ascendant/descendant).
1. La priorité du tri est définie par l&#39;ordre des colonnes de tri. Pour changer la priorité, modifiez l&#39;ordre des colonnes à partir des icônes correspondantes.

   La priorité du tri n&#39;a aucune incidence sur l&#39;affichage des colonnes de la liste.

1. Cliquez sur **[!UICONTROL OK]** pour valider ce paramétrage et visualiser le résultat dans la liste.


## Ressources supplémentaires

* **[Commencez par l’interface utilisateur de Campaign](../start/campaign-ui.md)** - Découvrez comment accéder à l’interface d’Adobe Campaign et la parcourir.
* **[Utiliser des énumérations](../dev/enumerations.md)** - Standardisez les valeurs de champ avec des listes déroulantes prédéfinies pour une saisie plus rapide et plus cohérente des données.
