---
solution: Campaign Classic
product: campaign
title: Travailler avec Campaign et votre CRM
description: 'Découvrez comment travailler avec Campaign et votre CRM '
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 8c9f59067cd0e5a39e84315e5836a32bdf7a0864
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 25%

---

# Connectez votre CRM à Campaign {#gs-crm}

Adobe Campaign propose différents connecteurs CRM pour relier votre plateforme Adobe Campaign à vos systèmes tiers. Ces connecteurs CRM permettent par exemple de synchroniser les contacts, les comptes, les commandes, les achats, etc. Ils simplifient l&#39;intégration de votre application avec vos différentes applications tierces et métiers.

Ces connecteurs permettent une intégration rapide et facile des données : Adobe Campaign fournit un assistant dédié à la collecte et à la sélection des tables disponibles dans le CRM. Ceci garantit une synchronisation bidirectionnelle pour s&#39;assurer que les données sont à jour en tout temps sur l&#39;ensemble des systèmes.

>[!NOTE]
>
>Cette fonctionnalité est disponible dans Adobe Campaign via le package **Connecteurs CRM** dédié.

## Systèmes compatibles {#compatible-crm-systems-and-limitations}

Les CRM et versions pris en charge sont présentés dans la [matrice de compatibilité](../start/compatibility-matrix.md) de Campaign.

**REMARQUE**  - Les connecteurs CRM fonctionnent uniquement avec une URL sécurisée (https).

## Étapes de mise en œuvre {#crm-implementation-steps}

:flèche_supérieur_droite : Découvrez la procédure pas à pas pour connecter Campaign et Microsoft Dynamics dans [la documentation du Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=en#microsoft-dynamics-implementation-steps).

:flèche_supérieur_droite : Découvrez la procédure pas à pas pour connecter Campaign et Salesforce dans [la documentation du Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-sfdc.html?lang=en#getting-started)


La synchronisation des données entre Adobe Campaign et la gestion de la relation client est effectuée via une activité de processus dédiée. Créez vos workflows pour automatiser la synchronisation entre Campaign et votre gestion de la relation client. Vous pouvez créer un processus qui importe les contacts via Microsoft Dynamics, les synchronise avec les données Adobe Campaign existantes, supprime les contacts de duplicata, puis met à jour la base de données Adobe Campaign.

:flèche_supérieur_droite : Pour en savoir plus, consultez la [documentation Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-data-sync.html?lang=en#getting-started)

