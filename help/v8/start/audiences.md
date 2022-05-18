---
title: Utiliser des audiences dans Campaign
description: Utiliser des audiences dans Campaign
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 100%

---

# Utiliser des audiences dans Campaign{#gs-ac-audiences}

Les profils sont des contacts stockés dans la base de données Campaign.

Dans Adobe Campaign, les **destinataires** sont les profils par défaut ciblés pour l&#39;envoi de diffusions (e-mails, SMS, etc.). Les données de destinataire stockées dans la base de données permettent de filtrer la cible qui recevra une diffusion donnée et d&#39;ajouter des données de personnalisation dans le contenu de votre diffusion. D&#39;autres types de profils existent dans la base de données. Ils sont conçus pour différents usages. Par exemple, les profils de contrôle servent à tester vos diffusions avant leur envoi vers la cible finale.

Découvrez comment importer, mettre à jour et gérer des profils et des audiences [dans cette section](../audiences/gs-audiences.md).

## Créer des listes{#create-lists}

Une liste est un ensemble statique de contacts qui peut être ciblé dans des actions de diffusion ou mis à jour pendant une importation ou lors d&#39;une autre action de workflow. Par exemple, une population extraite de la base de données via une requête peut être stockée en tant que liste.

![](../assets/do-not-localize/glass.png) Découvrez comment créer et gérer des listes dans [cette page](../audiences/create-audiences.md).

## Filtrer la base de données{#filter-the-database}

La configuration des filtres permet de sélectionner des données dans une liste **[!UICONTROL de manière dynamique]** : lorsque les données sont modifiées, les données filtrées sont mises à jour. Vous pouvez créer vos propres filtres ou utiliser les filtres intégrés pour définir une audience cible.

![](../assets/do-not-localize/glass.png) Découvrez comment créer et gérer des filtres dans [cette page](../audiences/create-filters.md).

## Créer une audience dans un workflow

Le ciblage peut être créé au moyen d&#39;une combinaison de requêtes dans une séquence graphique de workflow. Vous pouvez créer des audiences qui seront ciblées en fonction de vos besoins. Pour afficher l&#39;éditeur de workflows, cliquez sur l&#39;onglet **[!UICONTROL Ciblage et workflows]** dans le tableau de bord des campagnes.

![](../assets/do-not-localize/book.png) Découvrez comment créer une audience dans un workflow de campagne dans la [documentation d&#39;Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=fr#building-the-main-target-in-a-workflow).{target=&quot;_blank&quot;}.


## Profils actifs{#active-profiles}

Conformément à votre contrat, chacune de vos instances Campaign est configurée avec un nombre spécifique de profils actifs comptabilisés à des fins de facturation. Consultez votre dernier contrat pour connaître le nombre de profils actifs achetés.

Un **profil** désigne un enregistrement d&#39;informations (par exemple un enregistrement dans la [Table de destinataires](../dev/datamodel.md) ou dans une table externe contenant un identifiant de cookie, un identifiant client, un identifiant mobile ou d&#39;autres informations relatives à un canal particulier) représentant un client final, un prospect ou un lead. Les profils sont considérés comme actifs s&#39;ils ont été ciblés ou ont fait l&#39;objet d&#39;une communication via un canal au cours des 12 derniers mois.

<!--
You can monitor the number of active profiles used on your instances directly from Campaign Control Panel. 

![](../assets/do-not-localize/book.png) For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
-->

## Confidentialité et consentement{#privacy-and-consent}

Adobe Campaign est un puissant outil servant à collecter et à traiter de très grands volumes de données, notamment des informations personnelles et des données sensibles. Adobe Campaign vous permet de collecter des données, y compris des informations personnelles et sensibles. Il est donc essentiel de recevoir et surveiller le consentement de vos destinataires.

![](../assets/do-not-localize/book.png) Découvrez comment gérer la confidentialité et le consentement dans la [documentation d&#39;Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=fr){target=&quot;_blank&quot;}.

**Rubriques connexes** dans la documentation de Campaign Classic v7 :

* [Conception et exécution d&#39;un workflow spécifique à une campagne](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html?lang=fr){target=&quot;_blank&quot;}

* [Découvrez comment sélectionner l&#39;audience d&#39;une campagne](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=fr){target=&quot;_blank&quot;}

* [Prise en main des workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=fr){target=&quot;_blank&quot;}
