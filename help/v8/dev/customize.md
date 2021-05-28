---
solution: Campaign v8
product: Adobe Campaign
title: Personnalisation de votre instance
description: Découvrez comment personnaliser votre instance
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
source-git-commit: ab7e458db5ad5696d144c17f6e89e4437a476d11
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 83%

---

# Personnalisation de votre instance{#gs-ac-custom}

Découvrez comment **personnaliser votre instance Campaign**

>[!CAUTION]
>
>La personnalisation d’Adobe Campaign est réservée aux utilisateurs experts.

## Création de schémas et champs de données

Dans Adobe Campaign, les schémas de données permettent de :

* définir la façon dont les objets de l’application sont liés à des tables de la base de données ;
* définir des liens entre les différents objets de données de l’application Campaign ;
* définir et décrire les champs individuels inclus dans chaque objet.

Par exemple, pour ajouter un champ à une table existante, comme la table de destinataires (nms:destinataire), vous devez étendre ce schéma.

Deux modes d’extension de table sont disponibles :

* Dans l’interface, par le biais de l’assistant **Nouveau champ**

   [!DNL :arrow_upper_right:] Découvrez comment ajouter rapidement un nouveau champ dans la documentation de Campaign  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html?lang=fr#configuring-campaign-classic)

* Par programme, en étendant le schéma

   [!DNL :bulb:] Découvrez comment étendre un schéma existant dans [cette section](../dev/extend-schema.md).


Vous pouvez également créer des tables dans la base de données Campaign et étendre le modèle de données natif.

Pour ajouter un nouveau type de données qui n’existe pas par défaut dans Adobe Campaign (une table des contrats par exemple), vous pouvez directement créer un schéma personnalisé. Pour plus d’informations à ce propos, consultez [cet exemple](../dev/create-schema.md#example--creating-a-contract-table).

**Rubriques connexes**

[!DNL :arrow_upper_right:] Exemple d’édition de schéma dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=fr#configuring-campaign-classic)

[!DNL :arrow_upper_right:] Cas pratique : lier un champ à une table de référence existante dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=fr#uc-link)


## Modification des formulaires de saisie

Les formulaires de saisie Campaign peuvent être adaptés à votre implémentation. Vous pouvez ajouter ou supprimer des champs de formulaire en modifiant le contenu XML.

[!DNL :bulb:] Découvrez comment modifier un formulaire de saisie existant ou en créer un dans [cette section](../dev/forms.md).

## Personnalisation des tableaux de bord{#gs-custom-dashboards}

L’interface d’Adobe Campaign utilise de nombreuses applications web afin d’accéder aux destinataires, aux diffusions, aux campagnes, aux stocks, etc., puis de gérer et d’agir sur ceux-ci. Elles se présentent dans l’interface sous la forme de tableaux de bord et ne sont composées que d’une seule page.

Les applications web d’usine sont stockées sous le nœud Administration > Paramétrage > Applications web.

[!DNL :arrow_upper_right:] Découvrez comment créer une page d’aperçu dans la documentation de Campaign dans  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html?lang=fr#creating-a-single-page-web-application)


## Personnalisation de listes et création de filtres {#gs-lists-and-filters}

### Accès aux données à partir des tableaux de bord

Les listes Campaign s’accompagnent de filtres prédéfinis pour faciliter la navigation et la visualisation des données.

[!DNL :arrow_upper_right:] En savoir plus sur les options de filtrage dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/filtering-options.html?lang=fr#about-filtering)


### Accès aux données à partir de l’Explorateur

Lorsque vous naviguez dans l’arborescence de l’Explorateur Adobe Campaign, les données contenues dans la base s’affichent dans des listes. Vous pouvez filtrer ces listes, lancer des recherches, ajouter des informations, filtrer et trier les données.

[!DNL :arrow_upper_right:] Découvrez comment configurer des listes et enregistrer une configuration de liste dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=fr#getting-started)


Vous pouvez appliquer un filtre sur ces listes afin d’afficher uniquement les données nécessaires à l’opérateur. Ensuite, les actions peuvent être exécutées sur les données filtrées. La configuration des filtres vous permet de sélectionner dynamiquement des données d’une liste. Si les données sont modifiées, les données filtrées sont mises à jour.

[!DNL :arrow_upper_right:] Découvrez comment filtrer les données dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/creating-filters.html?lang=fr#typology-of-available-filters)
