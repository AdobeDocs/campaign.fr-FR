---
solution: Campaign v8
product: Adobe Campaign
title: Utilisation de Campaign et de votre CRM
description: 'Découvrez comment utiliser Campaign et votre CRM '
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
source-git-commit: 4ae0c968bd68d76d7ceffb91023d5426d6a810ea
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 87%

---

# Connexion de votre CRM à Campaign {#gs-crm}

Adobe Campaign propose différents connecteurs CRM pour relier votre plateforme Adobe Campaign à vos systèmes tiers. Ces connecteurs CRM permettent par exemple de synchroniser les contacts, les comptes, les commandes, les achats, etc. Ils facilitent l’intégration de votre application à vos différentes applications tierces et métiers.

Ces connecteurs permettent une intégration rapide et facile des données : Adobe Campaign fournit un assistant dédié à la collecte et à la sélection des tableaux disponibles dans le CRM. Cela garantit une synchronisation bidirectionnelle et permet de s’assurer que les données sont à jour en tout temps, et ce, sur l’ensemble des systèmes.

>[!NOTE]
>
>Cette fonctionnalité est disponible dans Adobe Campaign via le package **Connecteurs CRM** dédié.

## Systèmes compatibles {#compatible-crm-systems-and-limitations}

Les CRM et versions pris en charge sont présentés dans la [matrice de compatibilité](../start/compatibility-matrix.md) de Campaign.

[!DNL :speech_balloon:] Les connecteurs CRM fonctionnent seulement avec une URL sécurisée (https).

## Étapes d’implémentation {#crm-implementation-steps}

[!DNL :arrow_upper_right:] Découvrez la procédure détaillée pour connecter Campaign et Microsoft Dynamics dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=fr#microsoft-dynamics-implementation-steps)

[!DNL :arrow_upper_right:] Découvrez la procédure détaillée pour connecter Campaign et Salesforce dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-sfdc.html?lang=fr#getting-started)


La synchronisation des données entre Adobe Campaign et le CRM est réalisée à travers une activité de workflow dédiée. Créez vos workflows pour automatiser la synchronisation entre Campaign et votre CRM. Vous pouvez créer un workflow qui importe les contacts depuis Microsoft Dynamics, les synchronise avec les données Adobe Campaign existantes, déduplique les contacts et met à jour la base de données Adobe Campaign.

[!DNL :arrow_upper_right:] En savoir plus dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-data-sync.html?lang=fr#getting-started)

