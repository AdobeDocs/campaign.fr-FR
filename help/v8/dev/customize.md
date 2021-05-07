---
solution: Campaign
product: Adobe Campaign
title: Personnaliser votre instance
description: Découvrez comment personnaliser votre instance
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 19%

---

# Personnaliser votre instance{#gs-ac-custom}

Découvrez comment **personnaliser votre instance Campaign**

>[!CAUTION]
>
>La personnalisation Adobe Campaign est réservée aux utilisateurs experts uniquement.

## Créer de nouveaux champs et schémas de données

Dans Adobe Campaign, les schémas de données permettent de :

* Définir comment les objets de données de l&#39;application sont liés aux tables de base de données sous-jacentes
* Définir des liens entre les différents objets de données dans l&#39;application Campaign
* définir et décrire les champs individuels inclus dans chaque objet

Vous pouvez ajouter un champ à un tableau existant, tel que le tableau destinataire (nms:destinataire), vous devez étendre ce schéma.

Deux modes d’extension de table sont disponibles :

* Dans l&#39;interface, en utilisant l&#39;assistant **Nouveau champ**

   :flèche_supérieur_droite : Découvrez comment ajouter rapidement un nouveau champ dans Campaign dans [la documentation Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html?lang=en#configuring-campaign-classic)

* Programmatiquement, en étendant le schéma

   : bulb: Découvrez comment étendre un schéma existant dans [cette section](../dev/extend-schema.md).


Vous pouvez créer de nouvelles tables dans la base de données Campaign et étendre le modèle de données intégré.

Pour ajouter un nouveau type de données qui n&#39;existe pas par défaut dans Adobe Campaign (une table des contrats par exemple), vous pouvez directement créer un schéma personnalisé. Pour plus d&#39;informations à ce sujet, reportez-vous à [cet exemple](../dev/create-schema.md#example--creating-a-contract-table).

**Rubriques connexes :**

:flèche_supérieur_droite : Exemple d’édition schéma dans [la documentation Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#configuring-campaign-classic)

:flèche_supérieur_droite : Cas d’utilisation : lier un champ à une table de référence existante dans la [documentation du Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#uc-link)


## Modification des formulaires d’entrée

Les formulaires d’entrée Campaign peuvent être adaptés à votre mise en oeuvre. Vous pouvez ajouter ou supprimer des champs en modifiant le contenu XML.

: bulb: Découvrez comment modifier un formulaire de saisie existant ou créer un nouveau formulaire dans [cette section](../dev/forms.md).

## Personnaliser les tableaux de bord{#gs-custom-dashboards}

L&#39;interface d&#39;Adobe Campaign utilise de nombreuses applications web afin d&#39;accéder, gérer et agir sur les destinataires, les diffusions, les opérations, les stocks, etc. Elles se présentent dans l&#39;interface sous la forme de tableaux de bord et elles ne sont composées que d&#39;une seule page.

Les applications web d&#39;usine sont stockées sous le nœud Administration > Paramétrage > Applications web.

:flèche_supérieur_droite : Découvrez comment créer une page d’aperçu dans Campaign dans [la documentation Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html?lang=en#creating-a-single-page-web-application)


## Personnaliser les listes et créer des filtres {#gs-lists-and-filters}

### Accès aux données à partir de tableaux de bord

Les listes Campaign sont fournies avec des filtres prédéfinis pour faciliter la navigation et la visualisation des données.

:flèche_supérieur_droite : En savoir plus sur les options de filtrage dans la [documentation Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/filtering-options.html?lang=en#about-filtering)


### Accès aux données à partir de l&#39;Explorateur

Lorsque vous naviguez dans l’arborescence de l’Explorateur Adobe Campaign, les données contenues dans la base de données s’affichent dans des listes. Vous pouvez filtrer ces listes, lancer des recherches, ajouter des informations, filtrer et trier les données.

:flèche_supérieur_droite : Découvrez comment configurer des listes et enregistrer une configuration de liste dans [la documentation du Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=en#getting-started)


Vous pouvez appliquer un filtre sur ces listes pour n’afficher que les données dont l’opérateur a besoin. Ensuite, les actions peuvent être exécutées sur les données filtrées. La configuration de filtre vous permet de sélectionner dynamiquement des données d’une liste. Si les données sont modifiées, les données filtrées sont mises à jour.

:flèche_supérieur_droite : Découvrez comment filtrer les données dans la [documentation du Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/creating-filters.html?lang=en#typology-of-available-filters)
