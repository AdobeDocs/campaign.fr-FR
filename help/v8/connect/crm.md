---
title: Utilisation de Campaign et de votre CRM
description: Découvrez comment utiliser Campaign et votre CRM
feature: Overview
role: Data Engineer
level: Beginner
exl-id: c2d34ee9-4427-48e7-a8cf-0ae02a801d50
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 100%

---

# Connexion de votre CRM à Campaign {#gs-crm}

Adobe Campaign propose différents connecteurs CRM pour relier votre plateforme Adobe Campaign à vos systèmes tiers. Ces connecteurs CRM permettent par exemple de synchroniser les contacts, les comptes, les commandes, les achats, etc. Ils facilitent l&#39;intégration de votre application à vos différentes applications tierces et métiers.

Ces connecteurs permettent une intégration rapide et facile des données : Adobe Campaign fournit un assistant dédié à la collecte et à la sélection des tableaux disponibles dans le CRM. Cela garantit une synchronisation bidirectionnelle et permet de s&#39;assurer que les données sont à jour en tout temps, et ce, sur l&#39;ensemble des systèmes.

>[!NOTE]
>
>Cette fonctionnalité est disponible dans Adobe Campaign via le package **Connecteurs CRM** dédié.

## Systèmes compatibles {#compatible-crm-systems-and-limitations}

Les CRM et versions pris en charge sont présentés dans la [matrice de compatibilité](../start/compatibility-matrix.md) de Campaign.

?? Les connecteurs CRM fonctionnent seulement avec une URL sécurisée (https).

## Étapes d&#39;implémentation {#crm-implementation-steps}

↗️ Découvrez la procédure pas à pas pour connecter Campaign et Microsoft Dynamics dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=fr#microsoft-dynamics-implementation-steps).

↗️ Découvrez la procédure pas à pas pour connecter Campaign et Salesforce dans la [documentation Campaign Classic V7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-sfdc.html?lang=fr#getting-started).


La synchronisation des données entre Adobe Campaign et le CRM est réalisée à travers une activité de workflow dédiée. Créez vos workflows pour automatiser la synchronisation entre Campaign et votre CRM. Vous pouvez créer un workflow qui importe les contacts depuis Microsoft Dynamics, les synchronise avec les données Adobe Campaign existantes, déduplique les contacts et met à jour la base de données Adobe Campaign.

↗️ Apprenez-en davantage en consultant la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-data-sync.html?lang=fr#getting-started)
