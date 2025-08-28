---
title: Utiliser des audiences dans Campaign
description: Utiliser des audiences dans Campaign
feature: Audiences
role: User
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
version: Campaign v8, Campaign Classic v7
source-git-commit: b24e05f152bc299ea7953856bfa71950b5cc9837
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 77%

---


# Utiliser des audiences dans Campaign{#gs-ac-audiences}

Les profils représentent les contacts stockés dans votre base de données Adobe Campaign. Par défaut, les **destinataires** sont les profils principaux utilisés lors de l’envoi de diffusions telles que les e-mails, les SMS ou le publipostage direct. Les données de destinataires stockées dans la base de données vous permettent de définir et de filtrer les audiences cibles et de personnaliser le contenu des diffusions. Outre les destinataires, d’autres types de profils existent à des fins spécifiques. Par exemple, les profils de contrôle vous permettent de tester les diffusions avant leur envoi à votre audience réelle.

Découvrez comment importer, mettre à jour et gérer des profils et des audiences [dans cette section](../audiences/gs-audiences.md).

## Créer des listes{#create-lists}

Une liste est un ensemble statique de contacts qui peut être ciblé dans des actions de diffusion ou mis à jour pendant une importation ou lors d&#39;une autre action de workflow. Par exemple, une population extraite de la base de données via une requête peut être stockée en tant que liste.

Découvrez comment créer et gérer des listes sur [cette page](../audiences/create-audiences.md).

## Filtrer la base de données{#filter-the-database}

La configuration des filtres permet de sélectionner des données dans une liste **[!UICONTROL de manière dynamique]** : lorsque les données sont modifiées, les données filtrées sont mises à jour. Vous pouvez créer vos propres filtres ou utiliser les filtres intégrés pour définir une audience cible.

Découvrez comment créer et gérer les filtres sur [cette page](../audiences/create-filters.md).

## Créer une audience dans un workflow

Le ciblage peut être créé au moyen d&#39;une combinaison de requêtes dans une séquence graphique de workflow. Vous pouvez créer des audiences qui seront ciblées en fonction de vos besoins. Pour afficher l&#39;éditeur de workflows, cliquez sur l&#39;onglet **[!UICONTROL Ciblage et workflows]** dans le tableau de bord des campagnes.

Découvrez comment créer une audience dans un workflow de campagne sur [cette page](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=fr){target="_blank"}.


## Profils actifs {#active-profiles}

Un profil actif est un profil avec lequel le client ou la cliente a tenté de communiquer au cours des 12 derniers mois via n’importe quel canal.

Conformément à votre contrat, chacune de vos instances Campaign est configurée avec un nombre spécifique de profils actifs comptabilisés à des fins de facturation. Consultez votre dernier contrat pour connaître le nombre de profils actifs achetés. En savoir plus dans la description du produit [Adobe Campaign](https://helpx.adobe.com/fr/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

Vous pouvez surveiller le nombre de profils actifs utilisés sur votre instance directement à partir du panneau de contrôle de Campaign. Pour plus d&#39;informations, consultez la [documentation du Panneau de contrôle](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=fr){target="_blank"}.


Les limitations et mécanismes de sécurisation suivants s’appliquent :

* Un profil qui a été ciblé par plusieurs diffusions n’est comptabilisé qu’une seule fois.
* Les profils ciblés dans le cadre du marketing social sur X (anciennement Twitter) ne sont pas pris en compte comme profils actifs.
* Le comptage est basé sur la clé primaire de la personne destinataire. Par conséquent, si un profil est présent dans deux tableaux de personnes destinataires différents, il peut être compté deux fois comme profil actif.

## Confidentialité et consentement{#privacy-and-consent}

Adobe Campaign est un puissant outil servant à collecter et à traiter de très grands volumes de données, notamment des informations personnelles et des données sensibles. Adobe Campaign vous permet de collecter des données, y compris des informations personnelles et sensibles. Il est donc essentiel de recevoir et surveiller le consentement de vos destinataires.

Découvrez comment gérer la confidentialité et le consentement dans la documentation de [Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=fr){target="_blank"}.

