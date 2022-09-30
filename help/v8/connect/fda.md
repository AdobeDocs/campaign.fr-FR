---
title: Utilisation de Campaign et de bases de données externes (FDA)
description: Découvrez comment utiliser Campaign et des bases de données externes
feature: Federated Data Access
role: Admin
level: Beginner, Intermediate
exl-id: 0259b3bd-9dc2-44f9-a426-c4af46b00a4e
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 70%

---

# Federated Data Access (FDA){#gs-fda}

Utilisez le connecteur FDA (Federated Data Access) pour connecter Campaign à une ou plusieurs **bases de données externes** et traiter les informations stockées dans celles-ci sans affecter vos données provenant des bases cloud de Campaign. Vous pouvez ensuite accéder à des données externes sans modifier la structure des données Adobe Campaign.

![](../assets/do-not-localize/speech.png)   En tant qu’utilisateur Cloud Services géré, [contact Adobe](../start/campaign-faq.md#support) pour connecter vos bases de données externes à Campaign.


>[!NOTE]
>
>* Les bases de données compatibles avec Federated Data Access sont répertoriées dans la section [Matrice de compatibilité](../start/compatibility-matrix.md).
>
>* Dans le contexte d’un [Déploiement Enterprise (FFDA)](../architecture/enterprise-deployment.md), un compte externe spécifique est disponible pour gérer la communication entre la base de données locale Campaign et la base de données cloud Snowflake. Ce compte externe est configuré pour vous par Adobe et **must not** être modifié.
>



## Bonnes pratiques et limites

L’option FDA est soumise aux limitations du système de base de données tiers que vous utilisez.

Gardez également à l’esprit les limites et bonnes pratiques suivantes :

* L&#39;option FDA est utilisée pour manipuler les données des bases de données externes en mode batch dans les workflows. Pour éviter les problèmes de performance, il n&#39;est pas recommandé d&#39;utiliser le module FDA dans le cadre d&#39;opérations unitaires, par exemple : personnalisation, interaction, messagerie en temps réel, etc.

* Evitez autant que possible les opérations nécessitant d&#39;utiliser à la fois la base Adobe Campaign et la base externe. Pour cela, vous pouvez :

   * exporter les données de la base Adobe Campaign vers la base externe et effectuer les opérations uniquement depuis la base externe avant de réimporter les résultats dans Adobe Campaign.

   * collecter les données de la base externe dans Adobe Campaign et effectuer les opérations localement.
   Si vous souhaitez effectuer de la personnalisation dans vos diffusions à l&#39;aide des données de la base externe, collectez les données à utiliser dans un workflow afin de les rendre disponibles dans une table temporaire. Utilisez alors les données de la table temporaire pour personnaliser votre diffusion. Pour ce faire, pré-traitez la personnalisation des messages dans un workflow dédié à l’aide de la fonction **[!UICONTROL Préparer les données de personnalisation avec un workflow]** , disponible dans la variable **[!UICONTROL Analyse]** de l’onglet des propriétés de la diffusion. Cette option permet, lors de l&#39;analyse de la diffusion, de créer et d&#39;exécuter automatiquement un workflow qui stocke toutes les données liées à la cible dans une table temporaire, notamment les données issues des tables liées dans une base de données externe.

   >[!CAUTION]
   >
   >Cette option améliore considérablement les performances lors de l&#39;exécution de l&#39;étape de personnalisation.


## Utiliser des données externes dans un workflow

Campaign est livré avec plusieurs activités de workflow que vous pouvez utiliser pour interagir avec les données de vos bases de données externes :

* **Filtrer sur les données externes** - Utilisez la variable **[!UICONTROL Requête]** pour ajouter des données externes et les utiliser dans les configurations de filtre définies.

* **Créer des sous-ensembles** - Utilisez la variable **[!UICONTROL Partage]** pour créer des sous-ensembles. Vous pouvez utiliser des données externes pour définir les critères de filtrage à utiliser.

* **Chargement de la base de données externe** - Utilisez les données externes de la variable **[!UICONTROL Chargement (SGBD)]** activité.

* **Ajouter des informations et des liens** - Utilisez la variable **[!UICONTROL Enrichissement]** pour ajouter des données additionnelles à la table de travail du workflow et créer des liens vers une table externe. Dans ce contexte, elle peut utiliser des données provenant d&#39;une base de données externe.

Vous pouvez également définir directement une connexion à une base de données externe à partir de toutes les activités de workflow répertoriées ci-dessus, pour une utilisation temporaire. Dans ce cas, il sera stocké dans une base de données externe locale, à utiliser uniquement dans le workflow en cours.

>[!CAUTION]
>
>Ce type de configuration ne doit être utilisé que temporairement pour collecter des données. La configuration du compte externe doit être préférée pour toute autre utilisation.

Par exemple, dans l&#39;activité **[!UICONTROL Requête]**, vous pouvez définir une connexion temporaire à une base externe comme suit :

1. Ouvrez l&#39;activité et cliquez sur le lien **[!UICONTROL Ajouter des données...]**
1. Sélectionnez les options des **[!UICONTROL Données externes]**.
1. Choisissez l&#39;option **[!UICONTROL En définissant localement la source de données]**.
1. Sélectionnez le moteur de la base de données cible dans la liste déroulante. Saisissez le nom du serveur et renseignez les paramètres d&#39;authentification. Indiquez également le nom de la base de données externe.
1. Sélectionnez la table où sont stockées les données. Vous pouvez saisir le nom de la table directement dans le champ correspondant ou cliquer sur l&#39;icône d&#39;édition pour accéder à la liste des tables de la base de données.
1. Cliquez sur le bouton **[!UICONTROL Ajouter]** pour définir un ou plusieurs champs de réconciliation entre les données de la base externe et celles de la base Adobe Campaign. Les icônes **[!UICONTROL Editer l&#39;expression]** des colonnes **[!UICONTROL Champ distant]** et **[!UICONTROL Champ local]** permettent d&#39;accéder à la liste des champs de chacune des tables.
1. Au besoin, indiquez une condition de filtrage et le mode de tri des données.
1. Sélectionnez les données additionnelles à collecter dans la base externe. Pour cela, double-cliquez sur le ou les champs à ajouter afin de les afficher parmi les **[!UICONTROL Colonnes de sortie]**.
1. Cliquez sur le bouton **[!UICONTROL Terminer]** pour valider ce paramétrage.
