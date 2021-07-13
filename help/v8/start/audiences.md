---
product: Adobe Campaign
title: Prise en main des audiences
description: Prise en main des audiences
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 97%

---

# Prise en main des audiences{#gs-ac-audiences}

## Utilisation de profils{#gs-ac-profiles}

Les profils sont des contacts stockés dans la base de données Campaign, notamment les clients, les abonnés et les prospects. Il existe de nombreux mécanismes permettant d&#39;acquérir des profils et de créer cette base de données : collecte en ligne par le biais de formulaires web, importation manuelle ou automatique de fichiers texte, réplication avec des bases de données d&#39;entreprises ou d&#39;autres systèmes d&#39;information. Adobe Campaign vous permet d&#39;intégrer des données d&#39;historique marketing, des informations d&#39;achat, des données de préférences, des données CRM et des données d&#39;informations personnelles pertinentes dans une vue consolidée afin d&#39;effectuer une analyse et de prendre des mesures. Les profils contiennent toutes les informations requises pour le ciblage, la qualification et le suivi des individus.

Un profil est un enregistrement dans la table **nmsRecipient** ou une table externe qui stocke tous les attributs de profil, tels que le prénom, le nom, l&#39;adresse e-mail, un identifiant de cookie, l&#39;identifiant client, l&#39;identifiant mobile ou d&#39;autres informations relatives à un canal particulier. D&#39;autres tables liées à la table des destinataires contiennent des données relatives aux profils, par exemple la table des logs de diffusion qui contient les enregistrements de toutes les diffusions envoyées aux destinataires. En savoir plus sur les profils intégrés et les tables de destinataires dans [cette section](../dev/datamodel.md#ootb-profiles).

Dans Adobe Campaign, les **destinataires** sont les profils par défaut ciblés pour l&#39;envoi de diffusions (e-mails, SMS, etc.). Les données de destinataire stockées dans la base de données permettent de filtrer la cible qui recevra une diffusion donnée et d&#39;ajouter des données de personnalisation dans le contenu de votre diffusion. D&#39;autres types de profils existent dans la base de données. Ils sont conçus pour différents usages. Par exemple, les profils de contrôle servent à tester vos diffusions avant leur envoi vers la cible finale.

Les profils peuvent être regroupés dans des listes ou collectés en interrogeant la base de données.


Pour renseigner des données de profil dans Campaign, vous pouvez :

* [importer des fichiers de données](import.md) provenant d&#39;une source de données externe telle qu&#39;un système CRM ;
* [créer des formulaires web](../dev/webapps.md) pour permettre aux clients de saisir leurs propres informations et de créer leur propre profil ;
* [mapper à une base de données externe](../connect/fda.md) dans laquelle les profils sont stockés ;
* saisir les profils manuellement à l&#39;aide de la console cliente, comme ci-dessous :

![](assets/create-profile.png)


↗️ Découvrez comment gérer les profils dans la [documentation d&#39;Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/about-profiles.html?lang=fr){target=&quot;_blank&quot;}.


## Confidentialité et consentement

Adobe Campaign est un outil puissant pour collecter et traiter de très grands volumes de données, notamment des informations personnelles et des données sensibles. Adobe Campaign vous permet de collecter des données, y compris des informations personnelles et sensibles. Il est donc essentiel de recevoir et surveiller le consentement de vos destinataires.

↗️ Découvrez comment gérer la confidentialité et le consentement dans la [documentation d&#39;Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=fr){target=&quot;_blank&quot;}.

## Création de listes

Une liste est un ensemble statique de profils qui peut être ciblé dans les actions de diffusion ou mis à jour lors d&#39;opérations d&#39;import ou lors de l&#39;exécution d&#39;un workflow. Par exemple, une population extraite de la base via une requête peut alimenter une liste.

↗️ Découvrez comment créer et gérer des listes dans la [documentation d&#39;Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/creating-and-managing-lists.html?lang=fr){target=&quot;_blank&quot;}.

## Interrogation de la base de données

Utilisez l&#39;activité **Requête** dans un workflow pour interroger votre base, segmenter les données et créer des audiences complexes.

↗️ Apprenez-en davantage sur les requêtes Campaign en consultant la [documentation d&#39;Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/targeting-data.html?lang=fr){target=&quot;_blank&quot;}.

↗️ Toutes les activités de ciblage sont répertoriées dans la [documentation d&#39;Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html?lang=fr){target=&quot;_blank&quot;}.

## Création d&#39;une audience dans un workflow

Le ciblage peut être créé au moyen d&#39;une combinaison de requêtes dans une séquence graphique de workflow. Vous pouvez créer des audiences qui seront ciblées en fonction de vos besoins. Pour afficher l&#39;éditeur de workflows, cliquez sur l&#39;onglet **[!UICONTROL Ciblage et workflows]** dans le tableau de bord des campagnes.

↗️ Découvrez comment créer une audience dans un workflow de campagne dans la [documentation de Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=fr#building-the-main-target-in-a-workflow){target=&quot;_blank&quot;}.


## Profils actifs{#active-profiles}

Conformément à votre contrat, chacune de vos instances Campaign est configurée avec un nombre spécifique de profils actifs comptabilisés à des fins de facturation. Consultez votre dernier contrat pour connaître le nombre de profils actifs achetés.

Un **profil** désigne un enregistrement d&#39;informations (par exemple un enregistrement dans la [Table de destinataires](../dev/datamodel.md) ou dans une table externe contenant un identifiant de cookie, un identifiant client, un identifiant mobile ou d&#39;autres informations relatives à un canal particulier) représentant un client final, un prospect ou un lead. Les profils sont considérés comme actifs s&#39;ils ont été ciblés ou ont fait l&#39;objet d&#39;une communication via un canal au cours des 12 derniers mois.

<!--
You can monitor the number of active profiles used on your instances directly from Campaign Control Panel. 

↗️ For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
-->

**Rubriques connexes**  dans la documentation Adobe Campaign Classic v7 :

↗️ [Conception et exécution d&#39;un workflow spécifique à une campagne](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html?lang=fr){target=&quot;_blank&quot;}

↗️ [Découvrez comment sélectionner l&#39;audience d&#39;une campagne](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=fr){target=&quot;_blank&quot;}

↗️ [Prise en main des workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=fr){target=&quot;_blank&quot;}
