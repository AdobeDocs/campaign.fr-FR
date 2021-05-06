---
solution: Campaign Classic
product: campaign
title: Architecture générale
description: Architecture générale de Campaign v8
exl-id: 1d9ff6c5-974d-4a8a-a0d7-641685bbe26e
translation-type: tm+mt
source-git-commit: 0e0cd6eb9fcf656c9ba6c72cd1a782098f9399fe
workflow-type: tm+mt
source-wordcount: '1162'
ht-degree: 55%

---

# Architecture générale{#general-architecture}

Un déploiement classique de la solution Adobe Campaign comprend les composants suivants :

* **Environnement client personnalisé**

   Interface graphique intuitive dans laquelle les utilisateurs peuvent communiquer et suivre les offres marketing, créer des campagnes, examiner et gérer toutes les activités, programmes et plans marketing (y compris les courriels, workflows et landings page), créer et gérer des profils clients et créer des audiences.

* **Environnement de développement**

   Logiciel côté serveur qui exécute les campagnes marketing par le biais des canaux de communication sélectionnés, notamment email, SMS, notification push, courrier, web ou social, en fonction des règles et des workflows définis dans l&#39;interface utilisateur.

* **Conteneurs de base de données**

   Basée sur la technologie de base de données relationnelle, la base de données Adobe Campaign stocke toutes les informations sur les clients, les composants de campagne, les offres et les workflows, ainsi que les résultats de campagne dans les conteneurs de base de données des clients.

## Environnement client personnalisé {#client-env}

L’application est accessible de différentes manières : Intégration d’un client riche, d’un client léger ou d’une API.

* **Console** client : La principale interface utilisateur de l&#39;application est un client riche, en d&#39;autres termes, une application native (Windows) qui communique avec le serveur d&#39;applications Adobe Campaign uniquement avec les protocoles Internet standard (SOAP, HTTP, etc.). La console client Adobe Campaign offre une grande convivialité pour la productivité, utilise très peu de bande passante (grâce à l&#39;utilisation d&#39;un cache local) et est conçue pour un déploiement facile. Cette console peut être déployée à partir d&#39;un navigateur Internet, peut être mise à jour automatiquement et ne nécessite aucune configuration réseau spécifique car elle ne génère que du trafic HTTP(S).

   : bulb: [En savoir plus sur Campaign Client Console](../start/connect.md).

* **Accès** Web : Certaines parties de l&#39;application sont accessibles via un simple navigateur Web à l&#39;aide d&#39;une interface utilisateur HTML, y compris le module de rapports, les étapes d&#39;approbation de diffusion, la surveillance d&#39;instance, etc.

   : bulb: [En savoir plus sur Campaign Web Access](../start/connect.md).

* **API** Campaign : Dans certains cas, le système peut être appelé à partir d&#39;une application externe à l&#39;aide des API de services Web exposées via le protocole SOAP.

   : bulb: [En savoir plus sur les API Campaign](../dev/api.md).

## Environnement de développement {#dev-env}

Adobe Campaign est une plate-forme unique avec différentes applications qui se combinent pour créer une architecture ouverte et évolutive. La plate-forme Adobe Campaign est écrite sur une couche d&#39;application flexible et est facilement configurable pour répondre aux besoins de votre entreprise. L&#39;architecture distribuée assure une évolutivité linéaire du système, passant de milliers de messages à des millions de messages.

Certains modules Campaign fonctionnent en permanence, tandis que d&#39;autres sont lancés à l&#39;occasion pour effectuer des tâches administratives (par exemple pour configurer la connexion à la base de données) ou pour exécuter une tâche récurrente (par exemple pour consolider les informations de suivi).

On distingue trois types de modules Adobe Campaign :

* Modules multi-instances : un seul processus est exécuté pour toutes les instances. Ceci s’applique aux modules suivants : web, syslogd, trackinglogd et watchdog.
* Modules mono-instances : un processus est exécuté par instance. Ceci s’applique aux modules suivants : mta, wfserver, inMail, sms et stat.
* Les modules utilitaires : il s&#39;agit de modules démarrés occasionnellement pour réaliser des opérations ponctuelles ou récurrentes (cleanup, config, remontée des logs de tracking, etc.).

Les principaux processus sont les suivants :

**Serveur applicatif** (nlserver web)

Ce processus expose toute la gamme des fonctionnalités Adobe Campaign via les API de services Web (SOAP - HTTP + XML). En outre, il peut générer de manière dynamique les pages Web utilisées pour l&#39;accès HTML (rapports, Formulaires web, etc.). Pour ce faire, ce processus comprend un serveur JSP Apache Tomcat. Il s&#39;agit du processus auquel la console se connecte.

**Moteur de workflow** (nlserver wfserver)

Il assure l&#39;exécution des processus de workflow définis dans l&#39;application.

Il prend également en charge les workflows techniques qui s&#39;exécutent périodiquement, et notamment les suivants :

* Tracking : récupération et consolidation des logs de tracking. Il permet d&#39;obtenir les logs du serveur de redirection et créer les indicateurs agrégés utilisés par le module de reporting.
* Cleanup : nettoyage de la base de données. Il permet de purger les anciens enregistrements et éviter une croissance exponentielle de la base.
* Billing : envoi automatique d&#39;un rapport d&#39;activité de la plateforme (taille de base, nombre d&#39;actions marketing, etc.).

**Serveur de diffusion** (nlserver mta)

Adobe Campaign permet d&#39;exécuter nativement les diffusions de type email. Ce processus agit alors comme un agent de transfert de mails (MTA) natif pour la diffusion par le protocole SMTP. Il prend en charge la personnalisation &quot;one-to-one&quot; des messages et leur diffusion physique. Il repose sur la notion de traitements de diffusions et gère les reprises automatiques. De plus, lorsque le tracking est activé, il remplace automatiquement toutes les URL présentes dans un message afin de les faire pointer vers le serveur de redirection.

Ce processus peut assurer la personnalisation et l&#39;envoi automatique vers un prestataire externe pour les diffusions de type SMS, Fax ou Courrier papier.

**Serveur de redirection** (nlserver webmdl)

Dans le cas des diffusions par email, Adobe Campaign assure automatiquement le suivi des ouvertures et clics dans les messages (et éventuellement le suivi des transactions générées sur le site Web). Pour cela, les URL présentes dans les emails sont réécrites afin de pointer vers ce module, qui assure l&#39;enregistrement de passage de l&#39;internaute avant de le rediriger vers la véritable URL.

Afin d&#39;en garantir la disponibilité maximale, ce processus est totalement indépendant de la base de données : les autres processus serveur dialoguent avec lui en utilisant uniquement des appels SOAP (donc HTTP, HTTPS et XML). Techniquement, cette fonctionnalité est implémentée dans un module d&#39;extension d&#39;un serveur HTTP (extension ISAPI sous IIS, module DSO sous Apache) et n&#39;est accessible que sous Windows.

D&#39;autres processus plus techniques sont également disponibles :

**Gestion des mails rebonds** (nlserver inMail)

Ce processus permet de relever automatiquement les boîtes mail configurées pour recevoir les mails rebonds retournés en cas d&#39;échec de livraison d&#39;emails. Ces mails sont ensuite passés au travers d&#39;un moteur de règles utilisé pour déterminer les causes exactes de non-livraison (destinataire inconnu, boîte aux lettres pleine, etc.) et mettre à jour l&#39;état de diffusion dans la base de données.

Toutes ces opérations sont entièrement automatiques et préconfigurées.

**Etat de diffusion des SMS** (nlserver sms)

Ce processus interroge à intervalles réguliers le routeur des messages SMS afin de collecter les états d&#39;avancement des diffusions et de mettre à jour la base de données.

**Ecriture des messages de logs** (nlserver syslogd)

Ce processus technique capture les messages de log et traces générés par tous les autres processus, et assure leur écriture sur disque. Il permet de collecter le maximum d&#39;informations utiles au diagnostic en cas de problème.

**Ecriture des logs de tracking** (nlserver trackinglogd)

Ce processus assure l&#39;enregistrement sur disque des logs de tracking générés par le processus de redirection.

**Ecriture des événements entrants** (nlserver interactiond)

Ce processus assure l&#39;enregistrement sur disque des événements entrants, dans le cadre de l&#39;application Interaction.

**Surveillance des modules** (nlserver watchdog)

Ce processus technique joue le rôle d’un processus principal qui entraîne les autres. Il les surveille également et les relance automatiquement en cas d’incident, ce qui permet de maintenir un temps d’activité du système.

**Serveur de statistiques** (nlserver stat)

Ce processus maintient les statistiques du nombre de connexions, de messages envoyés pour chaque serveur de messagerie vers lequel les messages sont envoyés, ainsi que leurs limitations (nombre maximum de connexions simultanées, de messages par heure et/ou connexion). Il permet également de fédérer plusieurs instances ou plusieurs machines entre elles si elles partagent les mêmes adresses IP publiques.

## Conteneurs de base de données {#db-containers}

La base de données Adobe Campaign Cloud repose sur [!DNL Snowflake] qui contient les données fonctionnelles (profils, abonnements, contenu, etc.), les données techniques (travaux de diffusion et journaux, logs de tracking, etc.). et les données de travail (achats, pistes) pour la solution, et tous les composants Adobe Campaign communiquent avec la base de données afin d&#39;exécuter leurs tâches spécifiques.

Les clients peuvent déployer Adobe Campaign à l’aide de la banque de données et des schémas prédéfinis et peuvent également l’étendre. Toutes les données du magasin de données sont accessibles par Adobe Campaign via des appels SQL. Adobe Campaign fournit également un ensemble complet d&#39;outils Extract Transform and Load (ETL) pour importer et exporter des données dans le système et en dehors.

![](assets/data-flow-diagram.png)
