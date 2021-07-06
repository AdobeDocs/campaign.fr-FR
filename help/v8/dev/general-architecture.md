---
product: Adobe Campaign
title: Architecture générale
description: En savoir plus sur l’architecture et les composants de Campaign
exl-id: 1d9ff6c5-974d-4a8a-a0d7-641685bbe26e
source-git-commit: 8b31e24e0b6cfb699179e62366bc6706e9019382
workflow-type: tm+mt
source-wordcount: '1217'
ht-degree: 100%

---

# Architecture générale{#general-architecture}

Un déploiement classique de la solution Adobe Campaign comprend les composants suivants :

* **Environnement client personnalisé**

   Interface graphique intuitive dans laquelle les utilisateurs peuvent communiquer et suivre les offres marketing, créer des campagnes, passer en revue et gérer toutes les activités, programmes et plans marketing, notamment les e-mails, les workflows et les landing pages, créer et gérer les profils des clients et créer les audiences.

* **Environnement de développement**

   Logiciel côté serveur qui exécute les campagnes marketing par le biais des canaux de communication sélectionnés, notamment e-mail, SMS, notification push, courrier, web ou social, en fonction des règles et des workflows définis dans l&#39;interface utilisateur.

* **Conteneurs de base de données**

   Reposant sur la technologie de base de données relationnelle, la base de données cloud d&#39;Adobe Campaign stocke toutes les informations sur les clients, les composants de campagne, les offres et les workflows, ainsi que les résultats de campagne dans des conteneurs de base de données client.

## Environnement client personnalisé {#client-env}

L&#39;application est accessible de différentes manières : client riche, client léger ou intégration via une API.

* **Console cliente** : la principale interface utilisateur de l&#39;application est une application native (sur Windows) qui communique avec le serveur applicatif Adobe Campaign via les protocoles Internet standard (SOAP, HTTP, etc.). La console cliente Adobe Campaign est très conviviale, permet d&#39;être productif, utilise très peu de bande passante (grâce à l&#39;utilisation d&#39;un cache local) et est conçue pour offrir un déploiement facile. Cette console peut être déployée à partir d&#39;un navigateur Internet et mise à jour automatiquement. En outre, elle ne nécessite aucune configuration réseau spécifique, car elle génère uniquement du trafic HTTP(S).

   [!DNL :bulb:] [En savoir plus sur la console cliente Campaign](../start/connect.md).

* **Accès web** : certaines parties de l&#39;application, dont le module de reporting, les étapes de validation d&#39;une diffusion, la surveillance des instances, etc., sont accessibles via un simple navigateur web à l&#39;aide d&#39;une interface utilisateur HTML.

   [!DNL :bulb:] [En savoir plus sur l&#39;accès web de Campaign](../start/connect.md).

* **API Campaign** : dans certains cas, le système est appelé par des applications externes qui utilisent les API Web Services exposées par le biais du protocole SOAP.

   [!DNL :bulb:] [En savoir plus sur les API Campaign](../dev/api.md).

## Environnement de développement {#dev-env}

Adobe Campaign est une plateforme unique comprenant différentes applications visant à créer une architecture ouverte et évolutive. La plateforme Adobe Campaign est écrite sur une couche d&#39;application flexible. Elle est facilement configurable pour répondre aux besoins de votre entreprise. L&#39;architecture distribuée assure une évolutivité linéaire du système, capable de passer de milliers de messages à des millions.

Certains modules Campaign fonctionnent en continu, tandis que d&#39;autres sont démarrés ponctuellement pour effectuer des actions d&#39;administration (par exemple configurer la connexion à la base de données) ou lancer une tâche récurrente (par exemple consolider les informations de tracking).

On distingue trois types de modules Adobe Campaign :

* **Modules multi-instances** : un seul processus est exécuté pour toutes les instances. Cela s&#39;applique aux modules suivants : web, syslogd, trackinglogd et watchdog.
* **Modules mono-instances** : un processus est exécuté par instance. Cela s&#39;applique aux modules suivants : mta, wfserver, inMail, sms et stat.
* **Modules utilitaires** : il s&#39;agit de modules démarrés occasionnellement pour réaliser des opérations ponctuelles ou récurrentes (nettoyage, configuration, téléchargement de logs de tracking, etc.).

Les principaux processus sont les suivants :

**Serveur applicatif** (nlserver web)

Ce processus expose toutes les fonctionnalités d&#39;Adobe Campaign via des API Web Services (SOAP/HTTP + XML). De plus, il est capable de générer dynamiquement les pages web utilisées par l&#39;accès HTML à l&#39;application (reporting, formulaires web, etc.). Pour cela, ce processus intègre le serveur de JSP Apache Tomcat. C&#39;est à ce processus que se connecte la console.

**Moteur de workflow** (nlserver wfserver)

Il assure l&#39;exécution des processus de workflow définis dans l&#39;application.

Il prend également en charge les workflows techniques qui s&#39;exécutent périodiquement, et notamment les suivants :

* **Tracking** : récupération et consolidation des logs de tracking. Il permet d&#39;obtenir les logs du serveur de redirection et de créer les indicateurs agrégés utilisés par le module de reporting.
* **Nettoyage** : nettoyage de la base de données. Il permet de purger les anciens enregistrements et d&#39;éviter une croissance exponentielle de la base de données.
* **Facturation **: envoi automatique d&#39;un rapport d&#39;activité de la plateforme (taille de la base de données, nombre d&#39;actions marketing, etc.).

**Serveur de diffusion** (nlserver mta)

Adobe Campaign dispose d&#39;une fonctionnalité native de diffusion par e-mail. Ce processus fonctionne comme un agent de transfert d&#39;e-mails SMTP (MTA). Il effectue une personnalisation &quot;un-à-un&quot; des messages et gère leur diffusion physique. Il s&#39;exécute à l&#39;aide de traitements de diffusion et gère les reprises automatiques. De plus, lorsque le tracking est activé, il remplace automatiquement les URL afin qu&#39;elles pointent vers le serveur de redirection.

Ce processus peut assurer la personnalisation et l&#39;envoi automatique vers un prestataire externe pour les diffusions de type SMS, Fax ou Courrier papier.

**Serveur de redirection** (nlserver webmdl)

Dans le cas des diffusions par e-mail, Adobe Campaign assure automatiquement le suivi des ouvertures et clics dans les messages (et éventuellement le suivi des transactions générées sur le site Web). Pour cela, les URL présentes dans les e-mails sont réécrites afin de pointer vers ce module, qui assure l&#39;enregistrement de passage de l&#39;internaute avant de le rediriger vers la véritable URL.

Afin d&#39;en garantir la disponibilité maximale, ce processus est totalement indépendant de la base de données : les autres processus serveur dialoguent avec lui en utilisant uniquement des appels SOAP (donc HTTP, HTTPS et XML). Techniquement, cette fonctionnalité est implémentée dans un module d&#39;extension d&#39;un serveur HTTP (extension ISAPI sous IIS, module DSO sous Apache) et n&#39;est accessible que sous Windows.

D&#39;autres processus plus techniques sont également disponibles :

**Gestion des mails rebonds** (nlserver inMail)

Ce processus permet de relever automatiquement les boîtes mail configurées pour recevoir les mails rebonds retournés en cas d&#39;échec de livraison d&#39;e-mails. Ces mails sont ensuite passés au travers d&#39;un moteur de règles utilisé pour déterminer les causes exactes de non-livraison (destinataire inconnu, boîte aux lettres pleine, etc.) et mettre à jour l&#39;état de diffusion dans la base de données.

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

Ce processus technique joue le rôle d&#39;un processus principal qui entraîne les autres. Il les surveille également et les relance automatiquement en cas d&#39;incident, ce qui permet de maintenir un temps d&#39;activité du système.

**Serveur de statistiques** (nlserver stat)

Ce processus maintient les statistiques du nombre de connexions, de messages envoyés pour chaque serveur de messagerie vers lequel les messages sont envoyés, ainsi que leurs limitations (nombre maximum de connexions simultanées, de messages par heure et/ou connexion). Il permet également de fédérer plusieurs instances ou plusieurs machines entre elles si elles partagent les mêmes adresses IP publiques.

## Conteneurs de base de données {#db-containers}

La base de données cloud d&#39;Adobe Campaign repose sur [!DNL Snowflake], qui contient les données fonctionnelles (profils, abonnements, contenu, etc.), les données techniques (traitement et journaux de diffusion, logs de tracking, etc.) ainsi que les données de travail (achats, leads) pour la solution. En outre, tous les composants Adobe Campaign communiquent avec la base de données afin d&#39;exécuter leurs tâches spécifiques.

Les clients peuvent déployer Adobe Campaign à l&#39;aide de la base de données et des schémas prédéfinis. Si nécessaire, cet environnement prédéfini peut être étendu. Toutes les données du datamart sont accessibles par Adobe Campaign via des appels SQL. Adobe Campaign fournit également un ensemble complet d&#39;outils Extract Transform and Load (ETL) pour importer et exporter des données dans et en dehors du système.

![](assets/data-flow-diagram.png)


>[!CAUTION]
>
>Avec **Managed Cloud Services de Campaign**, votre environnement et votre configuration initiale ont été définis par Adobe, conformément aux termes de votre contrat de licence. Vous n&#39;êtes pas autorisé à modifier les packages, les schémas ou les rapports natifs installés.
>
>Si vous devez utiliser un module complémentaire Campaign ou une fonctionnalité spécifique qui n&#39;a pas été configurée pour vous, vous devez contacter **l&#39;assistance clientèle Adobe**.