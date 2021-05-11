---
solution: Campaign
product: Adobe Campaign
title: Commencer avec les audiences
description: Commencer avec les audiences
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
translation-type: tm+mt
source-git-commit: eb47761f20c02474bb971ab992cf1ea5098bb350
workflow-type: tm+mt
source-wordcount: '707'
ht-degree: 38%

---

# Commencer avec les audiences{#gs-ac-audiences}

Les profils peuvent être regroupés en listes ou collectés en interrogeant la base de données.

## Utilisation de profils{#gs-ac-profiles}

Les profils sont centralisés dans la base de données cloud. Il existe de nombreux mécanismes permettant d’acquérir des profils et créer cette base de données : collecte en ligne par le biais de formulaires Web, importation manuelle ou automatique de fichiers texte, réplication avec des bases de données d’entreprises ou d’autres systèmes d’information. Adobe Campaign vous permet d’intégrer des données d’historique marketing, des informations d’achat, des préférences, des données CRM et des données d’informations personnelles pertinentes dans une vue consolidée afin d’effectuer une analyse et de prendre des mesures.

&quot;**Profil**&quot; désigne un enregistrement d&#39;informations représentant un client, une prospect, un abonné à un bulletin d&#39;information, etc.
Un enregistrement de la table **nmsRecipient** ou d&#39;une table externe contient un identifiant de cookie, un identifiant de client, un identifiant de mobile ou d&#39;autres informations pertinentes pour un canal particulier. Pour en savoir plus sur les profils intégrés et les tableaux de destinataires, consultez [cette section](../dev/datamodel.md#ootb-profiles).

Dans Adobe Campaign, les destinataires sont les profils par défaut ciblés pour l’envoi de diffusions (emails, SMS, etc.). Les données de destinataire stockées dans la base de données permettent de filtrer la cible qui recevra une diffusion donnée et d’ajouter des données de personnalisation dans le contenu de votre diffusion. D’autres types de profils existent dans la base de données. Ils sont conçus pour différents usages. Par exemple, les profils de contrôle servent à tester vos diffusions avant leur envoi vers la cible finale.

:flèche_avant : [Comprendre ce qu’est un profil dans video](https://video.tv.adobe.com/v/35611?quality=12)

:flèche_supérieur_droite : Découvrez comment gérer les profils dans [ce guide](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/about-profiles.html{{){:cible=&quot;_blank&quot;}.

## Confidentialité et consentement

Adobe Campaign est un outil puissant pour collecter et traiter de très grands volumes de données, notamment des informations personnelles et des données sensibles. Adobe Campaign vous permet de collecter des données, y compris des informations personnelles et sensibles. Il est donc essentiel de recevoir et surveiller le consentement de vos destinataires.

:flèche_supérieur_droite : Découvrez comment gérer la confidentialité et le consentement dans [ce guide](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html).


## Créer des listes

Une liste est un ensemble statique de profils qui peut être ciblé dans les actions de diffusion ou mis à jour lors d’opérations d’import ou lors de l’exécution d’un workflow. Par exemple, une population extraite de la base via une requête peut alimenter une liste.

:flèche_supérieur_droite : Découvrez comment créer et gérer des listes dans [cette section](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/creating-and-managing-lists.html).

## Requête de la base de données

Utilisez l&#39;activité **Requête** dans un processus pour requête de votre base de données, segmenter les données et créer des audiences complexes.

:flèche_supérieur_droite : Pour en savoir plus sur les requêtes Campaign, consultez [ce guide](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/targeting-data.html).

:flèche_supérieur_droite : Toutes les activités de ciblage sont répertoriées dans [cette page](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html).

## Création d’une audience dans un processus

Le ciblage peut être créé au moyen d’une combinaison de requêtes dans une séquence graphique d’un flux de travail. Vous pouvez créer des audiences qui seront ciblées en fonction de vos besoins. Pour afficher l’éditeur de flux de travaux, cliquez sur l’onglet **[!UICONTROL Ciblage et workflows]** dans le tableau de bord de la campagne.

:flèche_supérieur_droite : Découvrez comment créer une audience dans un processus de campagne dans [cette page]https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow)


## Profils actifs{#active-profiles}

Conformément à votre contrat, chacune de vos instances Campaign est configurée avec un nombre spécifique de profils actifs comptabilisés à des fins de facturation. Consultez votre dernier contrat pour connaître le nombre de profils actifs achetés.

&quot;Profil&quot; : un enregistrement d&#39;information (p. ex. : un enregistrement dans la table [Destinataire](../dev/datamodel.md) ou une table externe contenant un ID de cookie, un ID de client, un identifiant de mobile ou d&#39;autres informations pertinentes pour un canal particulier) représentant un client final, une prospect ou une piste. Les profils sont considérés comme principaux s&#39;ils ont été ciblés ou communiqués au cours des 12 derniers mois par l&#39;intermédiaire d&#39;un canal quelconque.

Vous pouvez contrôler le nombre de profils principaux utilisés sur vos instances directement à partir du Panneau de Contrôle Campaign.

:flèche_supérieur_droite : Pour plus d&#39;informations à ce sujet, consultez la [documentation du Panneau de Contrôle](https://docs.adobe.com/content/help/fr-FR/control-panel/using/performance-monitoring/active-profiles-monitoring.html).


**Rubriques connexes :**

:flèche_supérieur_droite : [Concevoir et exécuter un workflow spécifique à une campagne](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html)

:flèche_supérieur_droite : [Découvrez comment sélectionner l’audience d’une campagne](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html)

:flèche_supérieur_droite : [Commencer avec workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html)
