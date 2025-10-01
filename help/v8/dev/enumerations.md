---
title: Gérer les énumérations
description: Découvrir comment utiliser les énumérations
feature: Configuration, Application Settings
role: Developer
version: Campaign v8, Campaign Classic v7
level: Intermediate, Experienced
source-git-commit: 428de72e0459b95a6db0b06ec8541d0475b72fdd
workflow-type: tm+mt
source-wordcount: '858'
ht-degree: 57%

---

# Gérer les énumérations {#manage-enumerations}

Une énumération (également appelée liste détaillée) est une liste prédéfinie de valeurs que vous pouvez utiliser pour renseigner certains champs. Les énumérations permettent de normaliser les valeurs de champ, de rendre la saisie de données plus cohérente et de simplifier les requêtes.

Lorsqu’elles sont disponibles, les valeurs s’affichent dans une liste déroulante. Vous pouvez sélectionner une valeur directement ou commencer à saisir : l’entrée prédictive suggère des valeurs correspondantes et les complète automatiquement.

![](assets/enum_values.png)

Certains champs de console sont configurés avec des énumérations. Si une énumération est **ouverte**, vous pouvez également ajouter de nouvelles valeurs directement dans le champ.

## Accéder aux énumérations

Les valeurs utilisées dans ces champs sont gérées de manière centralisée. Vous pouvez les ajouter, les modifier, les mettre à jour ou les supprimer dans l’arborescence de l’explorateur, sous **Administration** `>` **Plateforme** `>` **Énumérations**.

* La section supérieure propose la liste des champs pour lesquels une énumération a été définie.
* La section inférieure répertorie les valeurs disponibles.

Lorsqu’une énumération est **[!UICONTROL ouverte]**, les utilisateurs peuvent saisir une nouvelle valeur directement dans le champ correspondant de l’interface utilisateur.

Lorsqu’une énumération est **[!UICONTROL Fermée]**, les nouvelles valeurs ne peuvent être ajoutées qu’à partir du menu **Énumération**.

## Ajouter une nouvelle valeur

Pour créer une nouvelle valeur d&#39;énumération, cliquez sur le bouton **[!UICONTROL Ajouter]**.

![](assets/enumeration_screen.png)

Saisissez le libellé de la valeur.


## Cleansing des alias {#alias-cleansing}

Dans les champs d’énumération, vous pouvez saisir des valeurs autres que des valeurs d’énumération. Ces valeurs peuvent être stockées telles quelles ou faire l&#39;objet d&#39;une normalisation.

>[!CAUTION]
>
>La normalisation des données est un processus critique qui affecte les données de la base. En effet, Adobe Campaign procède à la mise à jour en masse de données, ce qui peut impliquer la suppression de certaines valeurs. Cette opération est donc réservée à des utilisateurs avertis.

En effet, la valeur saisie peut être :

* ajoutée aux valeurs de l&#39;énumération : l&#39;option **[!UICONTROL Ouverte]** doit être cochée,
* soit remplacé automatiquement par son alias correspondant : dans ce cas, ce cas doit alors être défini dans l&#39;onglet **[!UICONTROL Alias]** de l&#39;énumération,
* stockée dans la liste des alias : un alias pourra lui être attribué ultérieurement.

### Créer un alias {#creating-an-alias}

L&#39;option **[!UICONTROL Support des alias]** permet de gérer les alias pour l&#39;énumération sélectionnée. Lorsque cette option est sélectionnée, l’onglet **[!UICONTROL Alias]** s’affiche au bas de la fenêtre.

Pour créer un alias, procédez comme suit :

1. Accédez à l’énumération pour mettre à jour tout clic **[!UICONTROL Ajouter]**.

   ![](assets/enumeration_alias_create.png)

1. Saisissez l&#39;alias à transformer et la valeur qui sera appliquée et cliquez sur **[!UICONTROL Ok]**.

1. Vérifiez les paramètres avant de valider cette opération.

>[!CAUTION]
>
>Une fois cette étape confirmée, les valeurs précédentes peuvent ne pas être récupérées : elles sont remplacées.

Ainsi, lorsqu&#39;un utilisateur renseigne la valeur **NEILSEN** dans un champ « société » (dans la console Adobe Campaign ou dans un formulaire), elle est remplacée automatiquement par la valeur **NEILSEN Ltd**. Le remplacement des valeurs est effectué par le workflow **Cleansing des alias**. Pour plus d’informations, consultez la section [Exécuter le cleansing des données](#running-data-cleansing).

![](assets/enumeration_alias_use.png)

### Convertir les valeurs en alias {#values-into-aliases}

Vous pouvez convertir des valeurs existantes en alias. Pour ce faire, procédez comme suit :

1. Faites un clic droit dans la liste des valeurs et choisissez **[!UICONTROL Convertir les valeurs en alias...]**.

1. Sélectionnez les valeurs à convertir et cliquez sur **[!UICONTROL Suivant]**.

1. Cliquez sur **[!UICONTROL Démarrer]** pour lancer la conversion.

Une fois l&#39;exécution terminée, l&#39;alias est ajouté dans la liste des alias.

### Récupérer les hits d’alias {#alias-hits}

Lorsque les utilisateurs saisissent des valeurs qui ne sont pas incluses dans l’énumération, elles sont stockées dans l’onglet **[!UICONTROL Alias]**.

Le workflow technique **Cleansing des alias** récupère ces valeurs toutes les nuits pour mettre à jour l’énumération. Pour plus d&#39;informations, consultez la section [Exécution du cleansing des données](#running-data-cleansing)

Si nécessaire, la colonne **[!UICONTROL Accès]** peut afficher le nombre de fois où cette valeur a été saisie. Cependant, le calcul de cette valeur peut prendre du temps et de la mémoire. Voir à ce sujet la section [Calcul des occurrences de saisie](#calculating-entry-occurrences).

### Exécuter le cleansing des données {#run-data-cleansing}

Le cleansing des données est effectué par le workflow technique **[!UICONTROL Cleansing des alias]**. Les paramétrages définis pour les énumérations sont appliqués lors de son exécution. Voir [Workflow de cleansing des alias](#alias-cleansing-workflow).

Vous pouvez déclencher la normalisation via le lien **[!UICONTROL Uniformiser les valeurs...]**.

Le lien **[!UICONTROL Paramètres avancés...]** permet de définir la date de prise en compte des valeurs collectées.

Cliquez sur le bouton **[!UICONTROL Démarrer]** pour lancer l&#39;uniformisation des données.

### Calculer les occurrences de saisie {#entry-occurrences}

Le sous-onglet **[!UICONTROL Alias]** d&#39;une énumération peut afficher le nombre d&#39;occurrences d&#39;un alias parmi toutes les valeurs saisies. Ces informations sont une estimation qui sera affichée dans la colonne **[!UICONTROL Accès]**.

>[!CAUTION]
>
>Le calcul des occurrences de saisie d&#39;un alias peut être long. Cette fonctionnalité doit par conséquent être utilisée avec précaution.

Vous pouvez lancer manuellement le calcul des occurrences via le lien **[!UICONTROL Nettoyer les valeurs...]**. Pour cela, cliquez sur le lien **[!UICONTROL Paramètres avancés]**, puis sélectionnez la ou les options souhaitées.

* **[!UICONTROL Actualiser le nombre d&#39;apparitions des alias]** : permet de mettre à jour les occurrences déjà calculées, à partir de la date de prise en compte renseignée.
* **[!UICONTROL Recalculer depuis le début le nombre d&#39;apparitions des alias]** : permet de réinitialiser tout le calcul sur l&#39;ensemble de la plateforme Adobe Campaign.

Vous pouvez également créer un workflow dédié afin que ce calcul s&#39;exécute automatiquement pour une période donnée, par exemple toutes les semaines.

Pour cela, créez une copie du workflow **[!UICONTROL Gestion des alias]**, modifiez le planificateur et utilisez les paramètres suivants dans l&#39;activité **[!UICONTROL Uniformisation des valeurs des énumérations]** :

* **updateHits** pour actualiser le nombre d’apparitions des alias,
* **-updateHits:full** pour recalculer tous les accès aux alias.

### Workflow de gestion des alias {#alias-cleansing-workflow}

Le workflow **Gestion des alias** exécute la normalisation des valeurs d&#39;énumération. Par défaut, sa fréquence d&#39;exécution est quotidienne.

Il est accessible à partir du noeud **[!UICONTROL Administration > Exploitation > Workflows techniques]**.


