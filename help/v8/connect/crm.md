---
title: Utilisation de Campaign et de votre CRM
description: Découvrez comment utiliser Campaign et votre CRM
feature: Overview
role: Data Engineer
level: Beginner
exl-id: c2d34ee9-4427-48e7-a8cf-0ae02a801d50
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 63%

---

# Connexion de votre CRM à Campaign {#gs-crm}

Adobe Campaign propose différents connecteurs CRM pour relier votre plateforme Adobe Campaign à vos systèmes tiers. Ces connecteurs CRM permettent par exemple de synchroniser les contacts, les comptes, les commandes, les achats, etc. Ils facilitent l’intégration de votre application à vos différentes applications tierces et métiers.

Ces connecteurs permettent une intégration rapide et facile des données : Adobe Campaign fournit un assistant dédié à la collecte et à la sélection des tableaux disponibles dans le CRM. Cela garantit une synchronisation bidirectionnelle et permet de s&#39;assurer que les données sont à jour en tout temps, et ce, sur l&#39;ensemble des systèmes.

Les principaux avantages sont les suivants :

* Messagerie cohérente entre les ventes et le marketing : l’intégration d’Adobe Campaign à votre CRM permet aux deux systèmes d’accéder à l’insight du client et à l’historique marketing email, ce qui permet à tous les messages adressés au client de partager les mêmes messages cohérents.

* Vue holistique de toutes les données client et prospect : grâce à l&#39;intégration d&#39;Adobe Campaign à votre CRM, il est possible de partager et d&#39;accéder à l&#39;historique marketing email de chaque contact depuis le système CRM.

* Activez vos données CRM sur n’importe quel canal : avec les données de contact synchronisées avec Adobe Campaign, les communications peuvent être envoyées sur n’importe quel canal en ligne ou hors ligne avec Campaign, y compris les notifications push mobiles, les messages In-App, les courriers électroniques ou les courriers.


>[!NOTE]
>
>Cette fonctionnalité est disponible dans Adobe Campaign via le package **Connecteurs CRM** dédié.

## Systèmes compatibles {#compatible-crm-systems-and-limitations}

Les CRM et versions pris en charge sont présentés dans la [matrice de compatibilité](../start/compatibility-matrix.md) de Campaign.

![](../assets/do-not-localize/speech.png)  Les connecteurs CRM fonctionnent seulement avec une URL sécurisée (https).

## Étapes dʼimplémentation {#crm-implementation-steps}

Découvrez la procédure détaillée pour connecter Campaign et Microsoft Dynamics dans [cette page](ac-ms-dyn.md).

Découvrez la procédure détaillée pour connecter Campaign et Salesforce.com dans [cette page](ac-sfdc.md).

La synchronisation des données entre Adobe Campaign et le CRM est réalisée à travers une activité de workflow dédiée. Créez vos workflows pour automatiser la synchronisation entre Campaign et votre CRM. Vous pouvez créer un workflow qui importe les contacts depuis Microsoft Dynamics, les synchronise avec les données Adobe Campaign existantes, déduplique les contacts et met à jour la base de données Adobe Campaign.

![](../assets/do-not-localize/book.png) Apprenez-en davantage en consultant la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-data-sync.html?lang=fr#getting-started).
