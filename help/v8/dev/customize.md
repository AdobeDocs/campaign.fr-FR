---
title: Personnaliser votre instance
description: Découvrez comment personnaliser votre instance
feature: Application Settings
role: Data Engineer
level: Beginner
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
source-git-commit: c44fb2de4ed0e1661801313ae0430ba9d19542f0
workflow-type: ht
source-wordcount: '559'
ht-degree: 100%

---

# Personnaliser votre instance{#gs-ac-custom}

Découvrez comment **personnaliser votre instance Campaign**.

>[!CAUTION]
>
>La personnalisation d’Adobe Campaign est réservée aux utilisateurs experts.

## Création de schémas et champs de données

Dans Adobe Campaign, les schémas de données permettent de :

* définir la façon dont les objets de l&#39;application sont liés à des tables de la base de données ;
* définir des liens entre les différents objets de données de l&#39;application Campaign ;
* définir et décrire les champs individuels inclus dans chaque objet.

Par exemple, pour ajouter un champ à une table existante, comme la table de destinataires (nms:destinataire), vous devez étendre ce schéma.

Deux modes d&#39;extension de table sont disponibles :

* Dans l&#39;interface, par le biais de l&#39;assistant **Nouveau champ**

   ![](../assets/do-not-localize/book.png) Découvrez comment ajouter rapidement un nouveau champ dans Campaign dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html?lang=fr#configuring-campaign-classic).{target=&quot;_blank&quot;}

* Par programme, en étendant le schéma

   ![](../assets/do-not-localize/glass.png) Découvrez comment étendre un schéma existant dans [cette section](../dev/extend-schema.md).


Vous pouvez également créer des tables dans la base de données Campaign et étendre le modèle de données natif.

Pour ajouter un nouveau type de données qui n’existe pas par défaut dans Adobe Campaign (une table des contrats par exemple), vous pouvez directement créer un schéma personnalisé. Pour plus d&#39;informations à ce propos, consultez [cet exemple](../dev/create-schema.md#example--creating-a-contract-table).

**Rubriques connexes**

![](../assets/do-not-localize/book.png) Exemple d&#39;édition de schéma dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=fr#configuring-campaign-classic).{target=&quot;_blank&quot;}

![](../assets/do-not-localize/book.png)Cas d’utilisation : liaison d’un champ à une table de référence existante dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=fr#uc-link){target=&quot;_blank&quot;}.


## Modification des formulaires de saisie

Les formulaires de saisie Campaign peuvent être adaptés à votre implémentation. Vous pouvez ajouter ou supprimer des champs de formulaire en modifiant le contenu XML.

![](../assets/do-not-localize/glass.png) Découvrez comment modifier un formulaire de saisie existant ou en créer un dans [cette section](../dev/forms.md).

## Personnalisation des tableaux de bord{#gs-custom-dashboards}

L’interface d’Adobe Campaign utilise de nombreuses applications web afin d’accéder aux destinataires, aux diffusions, aux campagnes, aux stocks, etc., puis de gérer et d’agir sur ceux-ci. Elles se présentent dans l&#39;interface sous la forme de tableaux de bord et ne sont composées que d&#39;une seule page.

Les applications web d&#39;usine sont stockées sous le nœud Administration > Paramétrage > Applications web.

![](../assets/do-not-localize/book.png) Découvrez comment créer une page d&#39;aperçu dans Campaign dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html?lang=fr#creating-a-single-page-web-application).{target=&quot;_blank&quot;}


## Personnalisation de listes et création de filtres {#gs-lists-and-filters}

### Accès aux données à partir des tableaux de bord

Les listes Campaign s’accompagnent de filtres prédéfinis pour faciliter la navigation et la visualisation des données.

![](../assets/do-not-localize/book.png) En savoir plus sur les options de filtrage dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/filtering-options.html?lang=fr#about-filtering){target=&quot;_blank&quot;}.


### Accès aux données à partir de l&#39;Explorateur

Lorsque vous naviguez dans l’arborescence de l’Explorateur Adobe Campaign, les données contenues dans la base s’affichent dans des listes. Vous pouvez filtrer ces listes, lancer des recherches, ajouter des informations, filtrer et trier les données.

![](../assets/do-not-localize/book.png) Découvrez comment configurer des listes et enregistrer une configuration de liste dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=fr#getting-started).{target=&quot;_blank&quot;}


Vous pouvez appliquer un filtre sur ces listes afin d&#39;afficher uniquement les données nécessaires à l&#39;opérateur. Ensuite, les actions peuvent être exécutées sur les données filtrées. La configuration des filtres vous permet de sélectionner dynamiquement des données d&#39;une liste. Si les données sont modifiées, les données filtrées sont mises à jour.

![](../assets/do-not-localize/book.png) En savoir plus sur comment filtrer des données dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/creating-filters.html?lang=fr#typology-of-available-filters){target=&quot;_blank&quot;}.
