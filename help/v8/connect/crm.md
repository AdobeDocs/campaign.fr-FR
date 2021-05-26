---
solution: Campaign v8
product: Adobe Campaign
title: Utilisation de Campaign et de votre CRM
description: 'Découvrez comment utiliser Campaign et votre CRM '
feature: Vue d'ensemble
role: Data Engineer
level: Beginner
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 25%

---

# Connecter votre CRM à Campaign {#gs-crm}

Adobe Campaign propose différents connecteurs CRM pour relier votre plateforme Adobe Campaign à vos systèmes tiers. Ces connecteurs CRM permettent par exemple de synchroniser les contacts, les comptes, les commandes, les achats, etc. Ils simplifient l&#39;intégration de votre application avec vos différentes applications tierces et métiers.

Ces connecteurs permettent une intégration rapide et facile des données : Adobe Campaign fournit un assistant dédié à la collecte et la sélection des tables disponibles dans le CRM. Cela garantit une synchronisation bidirectionnelle pour s’assurer que les données sont à jour en tout temps sur l’ensemble des systèmes.

>[!NOTE]
>
>Cette fonctionnalité est disponible dans Adobe Campaign via le package **Connecteurs CRM** dédié.

## Systèmes compatibles {#compatible-crm-systems-and-limitations}

Les CRM et versions pris en charge sont présentés dans la [matrice de compatibilité](../start/compatibility-matrix.md) de Campaign.

:speak_ballon: Les connecteurs CRM fonctionnent uniquement avec une URL sécurisée (https).

## Étapes de mise en œuvre {#crm-implementation-steps}

:[!DNL :arrow_upper_right:] : Découvrez la procédure détaillée pour connecter Campaign et Microsoft Dynamics dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=en#microsoft-dynamics-implementation-steps)

:[!DNL :arrow_upper_right:] : Découvrez la procédure détaillée pour connecter Campaign et Salesforce dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-sfdc.html?lang=en#getting-started)


La synchronisation des données entre Adobe Campaign et le CRM s&#39;effectue via une activité de workflow dédiée. Créez vos workflows pour automatiser la synchronisation entre Campaign et votre CRM. Vous pouvez créer un workflow qui importe les contacts depuis Microsoft Dynamics, les synchronise avec les données Adobe Campaign existantes, supprime les contacts en double, puis met à jour la base de données Adobe Campaign.

:[!DNL :arrow_upper_right:] : En savoir plus dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-data-sync.html?lang=en#getting-started)

