---
title: Utilisation de Campaign et de votre CRM
description: Découvrez comment utiliser Campaign et votre CRM
feature: Salesforce Integration, Microsoft CRM Integration
role: Admin, User
level: Beginner
exl-id: c2d34ee9-4427-48e7-a8cf-0ae02a801d50
version: Campaign v8, Campaign Classic v7
TQID: 'https://experienceleague.adobe.com/gYGdySWZC1j2VkvAkL9rVBes7iQvRkRjNjm-dvFsHBM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: f09afca2-2160-4624-bedb-639c4f4c236f
    internal-label: Salesforce integration
  - id: dd99420f-367d-4a14-bbc4-5140615992c2
    internal-label: Microsoft CRM integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: beb7a3c1-66ab-4786-b879-7621375b3c40
    internal-label: Email marketing
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
    internal-label: Data integration
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 100%
---
# Connexion de votre CRM à Campaign {#gs-crm}

Adobe Campaign propose différents connecteurs CRM pour lier votre plateforme Adobe Campaign à vos systèmes tiers. Ces connecteurs CRM permettent par exemple de synchroniser les contacts, les comptes, les commandes, les achats, etc. Ils facilitent l’intégration de votre application à vos différentes applications tierces et métiers.

Ces connecteurs permettent une intégration rapide et facile des données : Adobe Campaign fournit un assistant dédié à la collecte et à la sélection des tableaux disponibles dans le CRM. Cela garantit une synchronisation bidirectionnelle et permet de s&#39;assurer que les données sont à jour en tout temps, et ce, sur l&#39;ensemble des systèmes.

Les principaux avantages sont les suivants :

* Messages cohérents entre les ventes et le marketing : l’intégration d&#39;Adobe Campaign avec votre CRM donne aux deux systèmes un accès aux informations du client et à l&#39;historique du marketing e-mail, ce qui permet à toutes les communications adressées au client de partager le même message cohérent.

* Vue holistique de toutes les données de prospect et de client : en intégrant Adobe Campaign avec votre CRM, il est possible de partager et d&#39;accéder à l&#39;historique du marketing e-mail de chaque contact depuis le système CRM.

* Activation des données de votre CRM sur n&#39;importe quel canal : les données de contact étant synchronisées avec Adobe Campaign, les communications peuvent être envoyées sur n’importe quel canal en ligne ou hors ligne avec Campaign, y compris des notifications push mobiles, In-App, des e-mails ou du courrier.


>[!NOTE]
>
>Cette fonctionnalité est disponible dans Adobe Campaign via le package **Connecteurs CRM** dédié.

## Systèmes compatibles {#compatible-crm-systems-and-limitations}

Les CRM et versions pris en charge sont présentés dans la [matrice de compatibilité](../start/compatibility-matrix.md) de Campaign.

>[!CAUTION]
>
> Les connecteurs CRM Campaign fonctionnent seulement avec une URL sécurisée (https).

## Étapes dʼimplémentation {#crm-implementation-steps}

Découvrez la procédure détaillée pour connecter Campaign et Microsoft Dynamics dans [cette page](ac-ms-dyn.md).

Découvrez la procédure détaillée pour connecter Campaign et Salesforce.com dans [cette page](ac-sfdc.md).

La synchronisation des données entre Adobe Campaign et le CRM est réalisée à travers une activité de workflow dédiée. Créez vos workflows pour automatiser la synchronisation entre Campaign et votre CRM. Vous pouvez créer un workflow qui importe les contacts depuis Microsoft Dynamics, les synchronise avec les données Adobe Campaign existantes, déduplique les contacts et met à jour la base de données Adobe Campaign. En savoir plus à ce propos sur [cette page](crm-data-sync.md).
