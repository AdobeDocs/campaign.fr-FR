---
title: Utiliser des audiences dans Campaign
description: Utiliser des audiences dans Campaign
feature: Audiences
role: User
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 85%

---

# Utiliser des audiences dans Campaign{#gs-ac-audiences}

Les profils sont des contacts stockés dans la base de données Campaign.

Dans Adobe Campaign, les **destinataires** sont les profils par défaut ciblés pour l&#39;envoi de diffusions (e-mails, SMS, etc.). Les données de destinataire stockées dans la base de données permettent de filtrer la cible qui recevra une diffusion donnée et d&#39;ajouter des données de personnalisation dans le contenu de votre diffusion. D&#39;autres types de profils existent dans la base de données. Ils sont conçus pour différents usages. Par exemple, les profils de contrôle servent à tester vos diffusions avant leur envoi vers la cible finale.

Découvrez comment importer, mettre à jour et gérer des profils et des audiences [dans cette section](../audiences/gs-audiences.md).

## Créer des listes{#create-lists}

Une liste est un ensemble statique de contacts qui peut être ciblé dans des actions de diffusion ou mis à jour pendant une importation ou lors d&#39;une autre action de workflow. Par exemple, une population extraite de la base de données via une requête peut être stockée en tant que liste.

Découvrez comment créer et gérer des listes dans [cette page](../audiences/create-audiences.md).

## Filtrer la base de données{#filter-the-database}

La configuration des filtres permet de sélectionner des données dans une liste **[!UICONTROL de manière dynamique]** : lorsque les données sont modifiées, les données filtrées sont mises à jour. Vous pouvez créer vos propres filtres ou utiliser les filtres intégrés pour définir une audience cible.

Découvrez comment créer et gérer des filtres dans [cette page](../audiences/create-filters.md).

## Créer une audience dans un workflow

Le ciblage peut être créé au moyen d&#39;une combinaison de requêtes dans une séquence graphique de workflow. Vous pouvez créer des audiences qui seront ciblées en fonction de vos besoins. Pour afficher l&#39;éditeur de workflows, cliquez sur l&#39;onglet **[!UICONTROL Ciblage et workflows]** dans le tableau de bord des campagnes.

Découvrez comment créer une audience dans un workflow de campagne dans [cette page](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=fr){target="_blank"}.


## Profils actifs {#active-profiles}

Un profil actif est un profil avec lequel le client ou la cliente a tenté de communiquer au cours des 12 derniers mois via n’importe quel canal. Les mesures de licence sont basées sur des profils actifs. En savoir plus dans la [description du produit Adobe Campaign](https://helpx.adobe.com/fr/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

Vous pouvez surveiller le nombre de profils actifs utilisés sur votre instance directement à partir du panneau de contrôle de Campaign. Pour plus d’informations à ce sujet, consultez la [documentation du Panneau de contrôle Campaign](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=fr){target="_blank"}.

>[!CAUTION]
>
>* Un profil qui a été ciblé par plusieurs diffusions n’est comptabilisé qu’une seule fois.
>
>* Les profils ciblés dans le cadre du marketing social sur X (anciennement Twitter) ne sont pas pris en compte comme profils actifs.

## Confidentialité et consentement{#privacy-and-consent}

Adobe Campaign est un puissant outil servant à collecter et à traiter de très grands volumes de données, notamment des informations personnelles et des données sensibles. Adobe Campaign vous permet de collecter des données, y compris des informations personnelles et sensibles. Il est donc essentiel de recevoir et surveiller le consentement de vos destinataires.

Découvrez comment gérer la confidentialité et le consentement dans [Documentation de Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=fr){target="_blank"}.

**Rubriques connexes** 

* [Concevoir et exécuter un workflow spécifique à une campagne](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/campaign-workflows.html?lang=fr){target="_blank"}

* [Découvrez comment sélectionner l’audience d’une campagne](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=fr){target="_blank"}

* [Prise en main des workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=fr){target="_blank"}
