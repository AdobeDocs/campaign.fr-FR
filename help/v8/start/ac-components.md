---
title: Présentation des processus et composants de Campaign
description: Présentation des processus et composants de Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 7db32bd8-a088-405f-9633-2968c28b13b0
source-git-commit: b54a39ee6d106d68446878815c068571e310aaa3
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 3%

---

# Présentation des processus et composants de Campaign {#components-and-processes}

Adobe Campaign est une solution de marketing cross-canal qui automatise les campagnes par e-mail, mobile, sociale et hors ligne. Adobe Campaign fournit un emplacement central pour accéder aux données et aux profils de vos clients. Utilisez Adobe Campaign pour orchestrer des expériences cohérentes avec vos clients, concevoir, exécuter et personnaliser votre marketing sur l’ensemble des canaux, tout en améliorant l’expérience client sur chaque périphérique et point de contact. Avec Adobe Campaign, vous pouvez gérer plusieurs sources de données, définir vos segments d’audience et planifier et exécuter des campagnes cross-canal à plusieurs étapes par le biais d’une interface de workflow visuel par glisser-déposer.

En savoir plus sur les fonctionnalités clés de Campaign dans [cette page](../start/get-started.md).

## Composants de Campaign {#ac-components}

Les composants Adobe Campaign et l’architecture globale sont décrits ci-dessous.

![](assets/ac-components.png)

### Couche de présentation{#presentation-layer}

Vous pouvez accéder à Adobe Campaign via un client riche, un client léger ou une intégration API.

* Client riche

   Le client riche de Campaign est une application native qui communique avec le serveur applicatif Adobe Campaign par le biais de protocoles Internet standard, tels que SOAP et HTTP.

   La console cliente Campaign centralise toutes les fonctionnalités et tous les paramètres et requiert une bande passante minimale car elle repose sur un cache local. Conçue pour un déploiement facile, la console cliente Campaign peut être déployée à partir d’un navigateur Internet, mise à jour automatiquement. Elle ne nécessite aucune configuration réseau spécifique, car elle ne génère que du trafic HTTP(S).

   ![](../assets/do-not-localize/glass.png) [En savoir plus sur la console cliente Campaign](../start/connect.md).

* Client léger

   Les fonctionnalités d’accès web d’Adobe Campaign vous permettent d’accéder à un sous-ensemble de fonctionnalités de Campaign avec un navigateur web, à l’aide d’une interface utilisateur de HTML. Utilisez cette interface web pour accéder aux rapports, contrôler et valider les messages, accéder aux tableaux de bord de surveillance, etc.

   ![](../assets/do-not-localize/glass.png) [En savoir plus sur l&#39;accès web de Campaign](../start/connect.md).

* Applications externes avec API

   Dans certains cas, le système peut être appelé à partir d&#39;applications externes à l&#39;aide des API de services web exposées via le protocole SOAP.

   ![](../assets/do-not-localize/glass.png) [En savoir plus sur les API Campaign](../dev/api.md).

### Couche de persistance{#persistance-layer}

Les bases de données de Campaign sont utilisées comme couches persistantes et contiennent presque toutes les informations et données gérées par Adobe Campaign. Cela inclut : les données fonctionnelles, telles que les profils, les abonnements, le contenu ; les données techniques, telles que les traitements de diffusion et les logs, les logs de tracking ; et les données de travail (achats, pistes).

La fiabilité de la base de données est primordiale car la plupart des composants d&#39;Adobe Campaign nécessitent un accès à la base de données pour accomplir leurs tâches (à l&#39;exception du module de redirection).

### Couche de logique applicative{#logical-app-layer}

La couche d’application logique de Campaign est facilement configurable pour répondre à des besoins métier complexes. Vous pouvez utiliser Campaign comme une plateforme unique avec différentes applications qui se combinent pour créer une architecture ouverte et évolutive. Chaque instance de Campaign est un ensemble de processus de la couche applicative, dont certains sont partagés et d&#39;autres dédiés.

## Campaign Managed Services{#ac-managed-services}

Adobe Campaign v8 est déployé as a Managed Service : tous les composants d’Adobe Campaign, y compris l’interface utilisateur, le moteur de gestion d’exécution et les bases de données Campaign, sont entièrement hébergés par Adobe, notamment l’exécution des emails, les pages miroir, le serveur de suivi et les composants web externes tels que le désabonnement de la page/du centre de préférences et les landing pages.

## Processus de campagne

Le serveur Web Campaign contrôle l&#39;accès aux processus Web Campaign. JavaScript est le langage côté serveur utilisé pour les fonctionnalités et la personnalisation de base du produit. Tomcat est le moteur principal et est incorporé dans le produit Campaign dans le cadre du processus web. Javascript est utilisé, par exemple, dans les pages JSP ou JSSP pour le rendu du contenu dynamique.

![](assets/ac-processes.png)

La console cliente Campaign se connecte au serveur Web à l&#39;aide de SOAP XML via HTTP. Le serveur Web fournit la couche de sécurité, transmet les requêtes à la couche Application à l&#39;aide de Javascript et l&#39;accès aux processus internes de Campaign à la base de données à l&#39;aide de SQL.

La communication globale entre les processus de Campaign est décrite dans le diagramme de déploiement autonome suivant : tous les composants de Campaign sont installés sur le même ordinateur.

![](assets/ac-standalone.png)

L’utilisateur se connecte au serveur applicatif Campaign à l’aide du protocole HTTP. Toutes les données et informations sont gérées dans la base de données Campaign. Si un développeur Campaign effectue des modifications de configuration, celles-ci sont capturées dans la base de données. Si un marketeur crée une nouvelle campagne, toutes les informations et données relatives à cette nouvelle campagne sont également gérées dans la base de données. Lorsqu’un marketeur exécute une campagne, les diffusions email sont envoyées aux profils à partir du serveur Campaign via le serveur SMTP. Lorsque les profils interagissent avec des diffusions email, telles que l’ouverture de l’email, ces données de tracking sont renvoyées au serveur de tracking.

![](../assets/do-not-localize/glass.png) [En savoir plus sur les processus de Campaign](../dev/general-architecture.md#dev-env).
