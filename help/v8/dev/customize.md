---
solution: Campaign v8
product: Adobe Campaign
title: Personnalisation de votre instance
description: Découvrez comment personnaliser votre instance
feature: Vue d'ensemble
role: Data Engineer
level: Beginner
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 17%

---

# Personnaliser votre instance{#gs-ac-custom}

Découvrez comment **personnaliser votre instance Campaign**

>[!CAUTION]
>
>La personnalisation d’Adobe Campaign est réservée à des utilisateurs experts uniquement.

## Création de champs de données et de schémas

Adobe Campaign utilise les schémas de données pour :

* Définir la manière dont les objets de données de l’application sont liés aux tables de base de données sous-jacentes
* Définir des liens entre les différents objets de données dans l&#39;application Campaign
* définir et décrire les champs individuels inclus dans chaque objet

Par exemple, pour ajouter un champ à une table existante, comme la table des destinataires (nms:recipient), vous devez étendre ce schéma.

Deux modes d’extension de table sont disponibles :

* Grâce à l’interface, en utilisant l’assistant **Nouveau champ**

   :flèche_upper_right : Découvrez comment ajouter rapidement un nouveau champ dans Campaign dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html?lang=en#configuring-campaign-classic)

* Par programmation, en étendant le schéma

   :bulb: Découvrez comment étendre un schéma existant dans [cette section](../dev/extend-schema.md).


Vous pouvez également créer de nouvelles tables dans la base de données Campaign et étendre le modèle de données intégré.

Pour ajouter un nouveau type de données qui n&#39;existe pas par défaut dans Adobe Campaign (une table des contrats par exemple), vous pouvez directement créer un schéma personnalisé. Voir à ce propos [cet exemple](../dev/create-schema.md#example--creating-a-contract-table).

**Rubriques connexes :**

:flèche_upper_right : Exemple d’édition de schéma dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#configuring-campaign-classic)

:flèche_upper_right : Cas pratique : lier un champ à une table de référence existante dans la [documentation Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#uc-link)


## Modifier les formulaires de saisie

Les formulaires de saisie Campaign peuvent être adaptés pour s&#39;adapter à votre implémentation. Vous pouvez ajouter ou supprimer des champs de formulaire en modifiant le contenu XML.

:bulb: Découvrez comment modifier un formulaire de saisie existant ou créer un nouveau formulaire dans [cette section](../dev/forms.md).

## Personnalisation des tableaux de bord{#gs-custom-dashboards}

L&#39;interface d&#39;Adobe Campaign utilise de nombreuses applications web afin d&#39;accéder, gérer et agir sur les destinataires, les diffusions, les opérations, les stocks, etc. Elles se présentent dans l&#39;interface sous la forme de tableaux de bord et elles ne sont composées que d&#39;une seule page.

Les applications web d&#39;usine sont stockées sous le nœud Administration > Paramétrage > Applications web.

:flèche_upper_right : Découvrez comment créer une page d’aperçu dans Campaign dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html?lang=en#creating-a-single-page-web-application)


## Personnalisation des listes et création de filtres {#gs-lists-and-filters}

### Accès aux données depuis les tableaux de bord

Les listes de campagnes sont dotées de filtres prédéfinis pour faciliter la navigation et la visualisation des données.

:flèche_upper_right : En savoir plus sur les options de filtrage dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/filtering-options.html?lang=en#about-filtering)


### Accès aux données à partir de l’Explorateur

Lorsque vous naviguez dans l&#39;arborescence de l&#39;Explorateur Adobe Campaign, les données contenues dans la base de données sont affichées dans des listes. Vous pouvez filtrer ces listes, lancer des recherches, ajouter des informations, filtrer et trier les données.

:flèche_upper_right : Découvrez comment configurer des listes et enregistrer une configuration de liste dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=en#getting-started)


Vous pouvez appliquer un filtre sur ces listes afin de n&#39;afficher que les données nécessaires à l&#39;opérateur. Ensuite, les actions peuvent être exécutées sur les données filtrées. La configuration des filtres permet de sélectionner dynamiquement les données d&#39;une liste. Si les données sont modifiées, les données filtrées sont mises à jour.

:flèche_upper_right : Découvrez comment filtrer les données dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/creating-filters.html?lang=en#typology-of-available-filters)
