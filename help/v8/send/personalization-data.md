---
title: Sources de données de personnalisation
description: Découvrez les sources pouvant être utilisées pour la personnalisation
feature: Personalization
role: User
level: Beginner
source-git-commit: 50688c051b9d8de2b642384963ac1c685c0c33ee
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 39%

---


# Sources de données de personnalisation{#personalization-data}

Les données de personnalisation peuvent être récupérées à partir de différents types de sources : Source de données de la base de données Campaign, Source de données de fichier externe ou Source de données de base de données externe.

## Source de données de la base de données Campaign

Dans le cas le plus courant, les données de personnalisation sont stockées dans la base de données. Par exemple, les &quot;champs de personnalisation des destinataires&quot; sont tous les champs définis dans la table des destinataires, les champs standard (généralement : nom, prénom, adresse, ville, date de naissance, etc.) ou des champs personnalisés.

![Champs de personnalisation de campagne dans un email](assets/perso-campaign-datasource.png)


## Source de données de fichier externe

Vous pouvez utiliser un fichier externe contenant tous les champs définis en colonnes. Ce fichier est utilisé comme entrée lors de la définition d’une diffusion de message. Vous pouvez choisir d&#39;insérer ou non ces profils dans la base de données.

Pour sélectionner le fichier à utiliser comme source de données, accédez au lien Pour de la fenêtre de création du message et sélectionnez le **Défini dans un fichier externe** . Une fois le fichier chargé, accédez aux données du destinataire dans les options de personnalisation, à partir du **Champs du fichier** entrée .

![Données de personnalisation d’un fichier](assets/perso-from-file.png)


## Source de données FDA

Les données de personnalisation peuvent être extraites d’une table externe via [Federated Data Access](../connect/fda.md).  Si vous souhaitez effectuer une personnalisation dans vos diffusions à l&#39;aide des données de la base externe, collectez les données à utiliser dans un workflow afin de les rendre disponibles dans une table temporaire.

Pour ce faire, ajoutez une **Requête** dans le workflow de ciblage et utilisez la méthode **Ajouter des données...** pour sélectionner la base externe. Le processus détaillé est disponible dans la section [cette section](../../automation/workflow/query.md#adding-data).

Utilisez ensuite les données de la table temporaire pour personnaliser votre diffusion. Une fois l&#39;activité de requête paramétrée, accédez aux données externes des options de personnalisation depuis la **Extension Target** entrée .

![Données de personnalisation d’une base de données externe](assets/perso-external-db.png)

Lors de l&#39;utilisation de données externes accessibles dans FDA, il est recommandé de pré-traiter la personnalisation des messages dans un workflow dédié à l&#39;aide de la fonction **Préparer les données de personnalisation avec un workflow** comme décrit ci-dessous.

### Optimiser la personnalisation {#optimize-personalization}

Vous pouvez optimiser la personnalisation à l&#39;aide d&#39;une option dédiée : **[!UICONTROL Préparer les données de personnalisation avec un workflow]**, disponible dans l&#39;onglet **[!UICONTROL Analyse]** des propriétés d&#39;une diffusion.

Cette option permet, lors de l&#39;analyse de la diffusion, de créer automatiquement et d&#39;exécuter un workflow qui stocke dans une table temporaire toutes les données liées à la cible, notamment les données issues des tables liées en FDA.

Si vous cochez cette option, les performances de l’analyse des diffusions peuvent être améliorées lorsque de nombreuses données sont en cours de traitement, en particulier si les données de personnalisation proviennent d’une table externe par le biais de FDA. [En savoir plus](../connect/fda.md).

Pour utiliser cette option, procédez comme suit :

1. Créez une campagne.
1. Dans le **[!UICONTROL Ciblage et workflows]** de votre campagne, ajoutez un **Requête** à votre workflow.
1. Ajoutez un **[!UICONTROL Diffusion Email]** dans le workflow et ouvrez-le.
1. Accédez à l&#39;onglet **[!UICONTROL Analyse]** des **[!UICONTROL Propriétés de la diffusion]** et sélectionnez l&#39;option **[!UICONTROL Préparer les données de personnalisation avec un workflow]**.
1. Configurez la diffusion et démarrez le workflow afin de lancer l&#39;analyse.

Une fois l&#39;analyse terminée, les données de personnalisation sont stockées dans une table temporaire via un workflow technique temporaire créé à la volée lors de l&#39;analyse.

Ce workflow n&#39;est pas visible dans l&#39;interface d&#39;Adobe Campaign. Il s&#39;agit uniquement d&#39;un moyen technique permettant de stocker et de traiter rapidement les données de personnalisation.

Une fois l&#39;analyse terminée, accédez aux **[!UICONTROL Propriétés]** du workflow et sélectionnez l&#39;onglet **[!UICONTROL Variables]**. Celui-ci contient le nom de la table temporaire que vous pouvez utiliser pour effectuer un appel SQL afin d&#39;afficher les identifiants qu&#39;elle contient.

## Données de personnalisation dans un workflow

Lorsqu&#39;une diffusion est créée dans le cadre d&#39;un workflow, vous pouvez utiliser les données de la table de workflow temporaire. Les données stockées dans la table de travail temporaire du workflow sont disponibles pour les tâches de personnalisation. Vous pouvez utiliser les données dans les champs de personnalisation.

Ces données sont regroupées dans la variable **[!UICONTROL Extension Target]** . Pour plus d’informations, consultez [cette section](../../automation/workflow/use-workflow-data.md#target-data).




