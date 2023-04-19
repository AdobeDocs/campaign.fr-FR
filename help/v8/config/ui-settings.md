---
title: Paramètres de l’interface de Campaign
description: Découvrez comment personnaliser les paramètres de l’interface de Campaign
version: v8
feature: Application Settings
role: Admin, Developer
level: Beginner, Intermediate, Experienced
source-git-commit: 1c879c7803c346d4b602089a22c2639eb83e82be
workflow-type: tm+mt
source-wordcount: '909'
ht-degree: 29%

---

# Paramètres de l’interface utilisateur de Campaign {#ui-settings}

## Énumérations {#enumerations}

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


>[!CAUTION]
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
