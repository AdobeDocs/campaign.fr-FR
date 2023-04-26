---
title: Paramètres de l’interface de Campaign
description: Découvrez comment personnaliser les paramètres de l’interface de Campaign
version: v8
feature: Application Settings
role: Admin, Developer
level: Beginner, Intermediate, Experienced
source-git-commit: 5251885f0493eb41f93d07f0e22dcf77926e69dd
workflow-type: tm+mt
source-wordcount: '1945'
ht-degree: 38%

---

# Paramètres de l’interface utilisateur de Campaign {#ui-settings}

## Unités par défaut {#default-units}

Dans Adobe Campaign, pour les champs qui expriment une durée (par exemple la période de validité des ressources, la date limite de validation d&#39;une tâche, etc.), les valeurs peuvent être exprimées dans la syntaxe suivante : **unit**:

* **[!UICONTROL s]** pour les secondes
* **[!UICONTROL mn]** pour les minutes
* **[!UICONTROL h]** pour les heures
* **[!UICONTROL j]** pour les jours

## Personnaliser l&#39;explorateur Campaign{#customize-explorer}

Vous pouvez ajouter des dossiers à l&#39;explorateur Campaign, créer des vues et attribuer des autorisations.

Découvrez comment gérer les dossiers et les vues dans [cette page](../audiences/folders-and-views.md)

## Gestion et personnalisation de listes{#customize-lists}

Dans la console cliente Campaign, les données sont affichées dans des listes. Vous pouvez adapter ces listes à vos besoins. Vous pouvez par exemple ajouter des colonnes, filtrer les données, comptabiliser les enregistrements, enregistrer et partager vos paramètres.

En outre, vous pouvez créer et enregistrer des filtres.  En savoir plus sur les filtres dans [cette page](../audiences/create-filters.md).

### Nombre d&#39;enregistrements {#number-of-records}

Par défaut, Adobe Campaign charge en mémoire les 200 premiers enregistrements d&#39;une liste. Par conséquent, l&#39;affichage ne propose pas nécessairement l&#39;intégralité des enregistrements de la table dont vous affichez le contenu. Vous pouvez lancer un décompte du nombre d&#39;enregistrements de la liste et déclencher le chargement en mémoire d&#39;enregistrements supplémentaires.

En bas à droite de l&#39;écran de liste, un **compteur** indique le nombre d&#39;enregistrements chargés en mémoire par rapport au nombre total d&#39;enregistrements dans la base (après application de tous les filtres éventuels) :

![Afficher le nombre total d&#39;enregistrements dans une liste](assets/number-of-records.png)

Si un point d’interrogation s’affiche à la place du nombre à droite, par exemple `240/?`, cliquez sur le compteur pour lancer le calcul.

Pour charger et afficher des enregistrements supplémentaires, cliquez sur **[!UICONTROL Continuer le chargement]**. Par défaut, 200 enregistrements sont chargés. Pour modifier le nombre d’enregistrements à charger par défaut, utilisez la variable **[!UICONTROL Configurer la liste]** dans le coin inférieur droit de la liste. Dans la fenêtre de configuration de la liste, cliquez sur **[!UICONTROL Paramètres avancés]** (en bas à gauche) et modifiez le nombre de lignes à récupérer.

Si vous souhaitez charger l&#39;intégralité des enregistrements, cliquez dans la liste avec le bouton droit et sélectionnez **[!UICONTROL Tout charger]**.

>[!CAUTION]
>
>Lorsqu&#39;une liste contient un volume élevé d&#39;enregistrements, le chargement complet peut prendre du temps.

### Ajout et suppression de colonnes {#add-columns}

Pour chaque liste, la configuration de colonne intégrée peut être adaptée pour afficher plus d’informations ou masquer les colonnes inutilisées.

Lorsque des données sont visibles dans le détail d&#39;un enregistrement, cliquez avec le bouton droit sur le champ et sélectionnez **[!UICONTROL Ajouter dans la liste]**.

![Ajouter un champ dans la liste](assets/add-in-the-list.png)

La colonne est ajoutée à droite des colonnes déjà affichées.

![Ajouter une colonne de champ](assets/add-a-column.png)

Vous pouvez également utiliser l&#39;écran de configuration de la liste pour ajouter et supprimer des colonnes :

1. Dans une liste d&#39;enregistrements, cliquez sur **[!UICONTROL Configurer la liste]** dans la section inférieure droite.
1. Double-cliquez sur les champs à ajouter dans le **[!UICONTROL Champs disponibles]** list : ils sont ajoutés au **[!UICONTROL Colonnes de sortie]** liste.

   ![Écran de configuration de liste](assets/list-config-screen.png)


   >[!NOTE]
   >
   >Par défaut, les champs avancés ne sont pas affichés. Pour les afficher, cliquez sur le bouton **Afficher les champs avancés** , dans la section inférieure droite de la liste des champs disponibles.
   >
   >Les champs sont identifiés par des icônes spécifiques : champs SQL, tables liées, champs calculés, etc. Pour chaque champ sélectionné, la description est affichée sous la liste des champs disponibles.

1. Utilisez les flèches haut/bas pour modifier la variable **ordre d’affichage**.

1. Cliquez sur **[!UICONTROL OK]** pour valider la configuration et visualiser le résultat.

Si vous devez supprimer une colonne, sélectionnez-la et cliquez sur l’icône **Corbeille** icône .

Vous pouvez utiliser la variable **[!UICONTROL Répartition des valeurs]** pour visualiser la répartition des valeurs du champ sélectionné dans le dossier courant.

![](assets/value-distribution.png)


### Créer une nouvelle colonne {#create-a-new-column}

Vous pouvez créer de nouvelles colonnes pour afficher des champs supplémentaires dans la liste.

Pour créer une colonne, procédez comme suit :

1. Dans une liste d&#39;enregistrements, cliquez sur **[!UICONTROL Configurer la liste]** dans la section inférieure droite.
1. Cliquez sur le bouton **[!UICONTROL Ajouter]** pour afficher un nouveau champ dans la liste.
1. Configurez le champ à ajouter à la colonne.


### Affichage des données dans des sous-dossiers {#display-sub-folders-records}

Les listes peuvent afficher :

* Tous les enregistrements contenus dans le dossier sélectionné (par défaut)
* Tous les enregistrements contenus dans le dossier sélectionné et ses sous-dossiers

Pour passer d’un mode d’affichage à l’autre, cliquez sur **[!UICONTROL Afficher les sous-niveaux]** dans la barre d’outils de Campaign.

### Enregistrement d’une configuration de liste {#saving-a-list-configuration}

Les configurations de liste sont définies localement pour chaque utilisateur. Lorsque le cache local est effacé, les configurations locales sont désactivées.

Par défaut, les paramètres de paramétrage s&#39;appliquent à toutes les listes avec le type de dossier correspondant. Lorsque vous modifiez l&#39;affichage de la liste de destinataires à partir d&#39;un dossier, ce paramétrage est appliqué à tous les autres dossiers de destinataires.

Vous pouvez enregistrer plusieurs configurations à appliquer à différents dossiers du même type. La configuration est enregistrée avec les propriétés du dossier contenant les données et peut être réappliquée.

Pour enregistrer une configuration de liste afin de pouvoir la réutiliser, procédez comme suit :

1. Dans l&#39;Explorateur, cliquez avec le bouton droit sur le dossier contenant les données affichées.
1. Sélectionnez **[!UICONTROL Propriétés]**.
1. Cliquez sur **[!UICONTROL Paramètres avancés]** et indiquez un nom dans le champ **[!UICONTROL Configuration]**.
1. Cliquez sur **[!UICONTROL OK]**, puis sur **[!UICONTROL Enregistrer]**.

Vous pouvez ensuite appliquer cette configuration à tout autre dossier du même type. En savoir plus sur les dossiers dans [cette page](../audiences/folders-and-views.md).

### Export d’une liste {#exporting-a-list}

Pour exporter les données d&#39;une liste, vous devez utiliser l&#39;assistant d&#39;export. Pour y accéder, sélectionnez les éléments de la liste à exporter, cliquez avec le bouton droit de la souris et choisissez **[!UICONTROL Exporter...]**.

<!--The use of the import and export functions is explained in [Generic imports and exports](../../platform/using/about-generic-imports-exports.md).-->

>[!CAUTION]
>
>Les éléments d&#39;une liste ne doivent pas être exportés via la fonction Copier/Coller.

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




## Utilisation des énumérations {#enumerations}

Une énumération (également appelée &quot;énumération&quot;) est une liste de valeurs proposées par le système pour renseigner les champs. Utilisez des énumérations pour normaliser les valeurs de ces champs, faciliter la saisie de données ou les utiliser dans des requêtes.

La liste des valeurs s&#39;affiche sous forme d&#39;une liste déroulante dans laquelle vous pouvez sélectionner la valeur à renseigner dans le champ. La liste déroulante permet également une entrée prédictive : saisissez les premières lettres et la demande remplit le reste.

La définition des valeurs des champs de ce type et l&#39;administration globale de ces champs (ajout/suppression d&#39;une valeur) s&#39;effectue depuis le nœud **[!UICONTROL Administration > Plateforme > Enumérations]** de l&#39;arborescence.

![Accès aux énumérations](assets/enumerations-menu.png)

### Types d&#39;énumération {#types-of-enum}

Les énumérations sont stockées dans la variable **[!UICONTROL Administration > Plateforme > Enumérations]** dossier de l’explorateur.

Ils peuvent être : Ouverture, système, émoticône ou fermeture.

* Un **Ouvrir** enumeration permet aux utilisateurs d’ajouter de nouvelles valeurs directement dans les champs à partir de cette énumération.
* A **Fermé** l&#39;énumération a une liste fixe de valeurs qui ne peut être modifiée qu&#39;à partir du **[!UICONTROL Administration > Plateforme > Enumérations]** dossier de l’explorateur.
* Un **Émoticône** enumeration est utilisée pour mettre à jour la liste des émoticônes. En savoir plus
* A **Système** enumeration est associée aux champs système et est fournie avec un nom interne.

Pour **Ouvrir** et **Fermé** énumérations, des options spécifiques sont disponibles :

* **Enumération simple** est le type standard par défaut.
* **Gestion des alias** enumeration est utilisée pour harmoniser les valeurs d’énumération stockées dans la base de données. [En savoir plus](#alias-cleansing)
* **Réservé à la mise en classe** est une option permettant de lier des valeurs cubiques à cette énumération. [En savoir plus](../reporting/gs-cubes.md)


### Gestion des alias {#alias-cleansing}

Dans les champs de l&#39;énumération, vous pouvez sélectionner une valeur ou saisir une valeur personnalisée qui n&#39;est pas disponible dans la liste déroulante. Les valeurs personnalisées peuvent être ajoutées aux valeurs d’énumération existantes, en tant que nouvelles. Dans ce cas, la variable **[!UICONTROL Ouvrir]** doit être sélectionnée. Ces valeurs personnalisées peuvent être nettoyées à l’aide des fonctionnalités de nettoyage des alias. Par exemple, si un utilisateur accède à `Adob` au lieu de `Adobe`, le processus de nettoyage des alias peut le remplacer automatiquement par le terme correct.

>[!CAUTION]
>
>La normalisation des données est un processus critique qui affecte les données de la base. En effet, Adobe Campaign procède à la mise à jour en masse de données, ce qui peut impliquer la suppression de certaines valeurs. Cette opération est donc réservée à des utilisateurs avertis.

Activez la variable **[!UICONTROL Gestion des alias]** pour utiliser les fonctionnalités de normalisation des données pour une énumération. Lorsque cette option est sélectionnée, la variable **[!UICONTROL Alias]** s’affiche au bas de la fenêtre.

Lorsqu’un utilisateur saisit une valeur qui n’existe pas dans une énumération Gestion des alias , elle est ajoutée à la variable **Valeurs** liste. Vous pouvez [créer des alias à partir de ces valeurs ;](#convert-to-alias)ou [créer de nouveaux alias à partir de zéro](#create-alias).

#### Créer un alias{#create-alias}

Pour créer un alias, procédez comme suit :

1. Cliquez sur **[!UICONTROL Ajouter]** du bouton **[!UICONTROL Alias]** .
1. Saisissez l&#39;alias à convertir et sélectionnez la valeur à appliquer dans la liste déroulante.

   ![Créer un alias](assets/new-alias.png)

1. Cliquez sur **[!UICONTROL Ok]** et confirmez.

1. Enregistrez vos modifications. Le remplacement des valeurs est effectué par la fonction **Gestion des alias** workflow exécuté toutes les nuits. Pour plus d&#39;informations, consultez la section [Exécution du cleansing des données](#running-data-cleansing).

Pour tous les champs basés sur cette énumération, lorsqu’un utilisateur saisit la valeur **Adobe** dans un champ &quot;société&quot; (dans la console Adobe Campaign, dans un formulaire web), il sera automatiquement remplacé par la valeur **Adobe**.

#### Convertir une valeur incorrecte en alias{#convert-to-alias}

Vous pouvez également convertir une valeur d&#39;énumération existante en alias. Procédez comme suit :

1. Dans la liste des valeurs d&#39;une énumération, cliquez avec le bouton droit de la souris et accédez à **[!UICONTROL Actions... > Convertir les valeurs en alias...]**.

   ![Convertir une valeur en alias](assets/convert-into-aliases.png)

1. Sélectionnez les valeurs à convertir en alias et cliquez sur **[!UICONTROL Suivant]**.
1. Cliquez sur **[!UICONTROL Démarrer]** pour lancer la conversion.

   Une fois l’exécution terminée, des alias sont ajoutés à la liste, dans la variable **Alias** . Vous pouvez associer une valeur correcte pour remplacer les entrées incorrectes. Procédez comme suit :

1. Sélectionnez une valeur à nettoyer.
1. Cliquez sur le bouton **Détail...** bouton .
1. Sélectionnez la nouvelle valeur dans la liste déroulante.

   ![Créer un alias](assets/define-new-alias.png)


>[!NOTE]
>
>Vous pouvez effectuer le suivi des occurrences d’un alias dans la variable **[!UICONTROL Accès]** dans la colonne **[!UICONTROL Alias]** sous-onglet. Il peut afficher le nombre de fois où cette valeur a été saisie.  [En savoir plus](#calculate-entry-occurrences).

#### Exécuter le cleansing des données {#running-data-cleansing}

La normalisation des données est effectuée par la fonction **[!UICONTROL Gestion des alias]** workflow technique. Par défaut, il est exécuté quotidiennement.

La normalisation peut également être déclenchée via le **[!UICONTROL Nettoyer les valeurs...]** lien.

Le lien **[!UICONTROL Paramètres avancés...]** permet de définir la date de prise en compte des valeurs collectées.

Cliquez sur le bouton **[!UICONTROL Démarrer]** pour lancer l&#39;uniformisation des données.

##### Surveiller les occurrences {#calculate-entry-occurrences}

Le sous-onglet **[!UICONTROL Alias]** d&#39;une énumération peut afficher le nombre d&#39;apparitions d&#39;un alias parmi toutes les valeurs saisies. Cette information est une estimation. Elle sera affichée dans la colonne **[!UICONTROL Hits]**.

>[!CAUTION]
>
>Le calcul des occurrences de saisie d&#39;un alias peut prendre beaucoup de temps.

Vous pouvez exécuter manuellement le calcul des accès à l’aide de l’option **[!UICONTROL Nettoyer les valeurs...]** lien. Pour ce faire, cliquez sur le bouton **[!UICONTROL Paramètres avancés...]** lier et sélectionner une ou plusieurs options.

* **[!UICONTROL Actualiser le nombre d&#39;apparitions des alias]** : permet de mettre à jour les occurrences déjà calculées, à partir de la date de prise en compte renseignée.
* **[!UICONTROL Recalculer depuis le début le nombre d&#39;apparitions des alias]** : permet de réinitialiser tout le calcul sur l&#39;ensemble de la plateforme Adobe Campaign.

Vous pouvez également créer un workflow dédié afin que ce calcul s&#39;exécute automatiquement pour une période donnée, par exemple toutes les semaines.

Pour cela, créez une copie du workflow **[!UICONTROL Gestion des alias]**, modifiez le planificateur et utilisez les paramètres suivants dans l&#39;activité **[!UICONTROL Uniformisation des valeurs des énumérations]** :

* **updateHits** pour actualiser le nombre d’apparitions des alias,
* **-updateHits:full** pour recalculer toutes les apparitions des alias.
