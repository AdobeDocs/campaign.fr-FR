---
title: Comprendre les processus et composants de Campaign
description: Comprendre les processus et composants de Campaign
feature: Overview, Architecture, Configuration
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
exl-id: 7db32bd8-a088-405f-9633-2968c28b13b0
source-git-commit: e0ec2940db3120dc8fbfd17dd2f5083bbf31232c
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 100%

---

# Comprendre les processus et composants de Campaign {#components-and-processes}

Adobe Campaign est une solution de marketing cross-canal qui automatise les campagnes par e-mail, mobiles, sociales et hors ligne. Adobe Campaign fournit un emplacement central pour accéder aux données et aux profils de vos clients. Utilisez Adobe Campaign pour orchestrer des expériences cohérentes avec vos clients, concevoir, exécuter et personnaliser votre marketing sur l&#39;ensemble des canaux, tout en améliorant l&#39;expérience client sur chaque appareil et point de contact. Avec Adobe Campaign, vous pouvez gérer plusieurs sources de données, définir vos segments d&#39;audience et planifier et exécuter des campagnes cross-canal à plusieurs étapes par le biais d&#39;une interface de workflow visuelle qui fonctionne par glisser-déposer.

Pour en savoir plus sur les fonctionnalités principales de Campaign, reportez-vous à [cette page](../start/get-started.md).

## Composants de Campaign {#ac-components}

Les composants et l&#39;architecture globale d&#39;Adobe Campaign sont décrits ci-dessous.

![](assets/ac-components.png)

### Couche de présentation{#presentation-layer}

Vous pouvez accéder à Adobe Campaign via un client riche, un client léger ou une intégration d&#39;API.

* Client riche

  Le client riche de Campaign est une application native qui communique avec le serveur applicatif d&#39;Adobe Campaign par le biais de protocoles internet standard, tels que SOAP et HTTP. [En savoir plus sur la console cliente Campaign](../start/connect.md).

* Client léger

  Les fonctionnalités d&#39;accès web d&#39;Adobe Campaign vous permettent d&#39;accéder à un sous-ensemble de fonctionnalités de Campaign avec un navigateur web, à l&#39;aide d&#39;une interface utilisateur HTML. Utilisez cette interface web pour consulter des rapports, contrôler et valider les messages, accéder aux tableaux de bord de surveillance, et plus encore.  [En savoir plus sur l&#39;accès web de Campaign](../start/connect.md).

* Applications externes avec API

  Dans certains cas, le système est appelé par des applications externes qui utilisent les API Web Services exposées par le biais du protocole SOAP. [En savoir plus sur les API Campaign](../dev/api.md).

### Couche de persistance{#persistance-layer}

Les bases de données de Campaign sont utilisées comme couches persistantes et contiennent presque toutes les informations et données gérées par Adobe Campaign. Ces données incluent : les données fonctionnelles, telles que les profils, les abonnements, le contenu ; les données techniques, telles que les traitements de diffusion et les logs, les logs de tracking ; et les données de travail (achats, pistes).

La fiabilité de la base de données est primordiale puisque la plupart des composants d&#39;Adobe Campaign doivent avoir accès à cette base afin d&#39;accomplir leurs tâches (hormis le module de redirection).

### Couche de logique applicative{#logical-app-layer}

La couche de logique applicative de Campaign est facilement configurable pour répondre à des besoins métier complexes. Vous pouvez utiliser Campaign comme une plateforme unique avec différentes applications qui se combinent pour créer une architecture ouverte et évolutive. Chaque instance de Campaign est un ensemble de processus de la couche applicative, dont certains sont partagés et d&#39;autres dédiés.

## Campaign Managed Cloud Services{#ac-managed-services}

Adobe Campaign v8 est déployé &#39;as a Managed Service&#39; : tous les composants d&#39;Adobe Campaign, y compris l&#39;interface utilisateur, le moteur de gestion de l&#39;exécution et la base de données Campaign, sont entièrement hébergés par Adobe. Cela inclut également l&#39;exécution des e-mails, les pages miroir, le serveur de tracking et les composants web externes, tels que la page de désabonnement/le centre de préférences et les landing pages.

## Processus Campaign

Le serveur Web Campaign contrôle l&#39;accès aux processus Web Campaign. JavaScript est la langue côté serveur utilisée pour les fonctionnalités et la personnalisation de base du produit. Tomcat est le moteur back-end et est incorporé à Campaign dans le cadre du processus web. Javascript est utilisé, par exemple, dans les pages JSP ou JSSP pour le rendu du contenu dynamique.

![](assets/ac-processes.png)

La console cliente Campaign se connecte au serveur Web à l’aide de SOAP XML via HTTP. Le serveur Web fournit la couche de sécurité, transmet les requêtes à la couche Application à l&#39;aide de Javascript et l&#39;accès des processus internes de Campaign à la base de données à l&#39;aide de SQL.

La communication globale entre les processus de Campaign est décrite dans le diagramme de déploiement autonome suivant : tous les composants de Campaign sont installés sur le même ordinateur.

![](assets/ac-standalone.png)

L&#39;utilisateur se connecte au serveur applicatif Campaign à l&#39;aide du protocole HTTP. Toutes les données et informations sont gérées dans la base de données Campaign. Si un développeur Campaign effectue des modifications de configuration, celles-ci sont capturées dans la base de données. Si un spécialiste marketing crée une nouvelle campagne, toutes les informations et données relatives à cette nouvelle campagne sont également gérées dans la base de données. Lorsqu&#39;un spécialiste marketing exécute une campagne, les diffusions par e-mail sont envoyées aux profils à partir du serveur Campaign via le serveur SMTP. Lorsque les profils interagissent avec des diffusions par e-mail, telles que l&#39;ouverture de l&#39;e-mail, ces données de tracking sont renvoyées au serveur de tracking.

![](../assets/do-not-localize/glass.png) [En savoir plus sur les processus de Campaign](../architecture/general-architecture.md#dev-env).
