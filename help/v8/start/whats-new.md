---
title: Nouveautés de Campaign v8
description: Découvrez les fonctionnalités clés d’Adobe Campaign v8, les nouveautés et ce que vous pouvez attendre de la dernière version.
feature: Overview, Release Notes
role: User
level: Beginner
exl-id: 7771a02c-ebd4-48b6-b25e-6b6e420ad493
source-git-commit: f577ee6d303bab9bb07350b60cf0fa6fc9d3a163
workflow-type: ht
source-wordcount: '923'
ht-degree: 100%

---

# Nouveautés d’Adobe Campaign v8 {#ac-gs-what-is-new}

Adobe Campaign v8 est conçu pour les spécialistes marketing cross-canal qui ont besoin de la solution cloud la plus performante pour la gestion de campagnes cross-canal à l’échelle de l’entreprise. Il offre des fonctionnalités ETL et de gestion des données performantes pour concevoir et organiser une campagne parfaite. Son moteur d’orchestration fournit des programmes marketing multi-touch riches qui mettent l’accent sur les parcours pilotés par lots. Il est également associé à un serveur de messagerie en temps réel évolutif qui permet aux équipes marketing d’envoyer des messages prédéfinis sur la base d’une payload globale à partir de n’importe quel système informatique, pour des tâches telles que la réinitialisation du mot de passe, la confirmation de commande, la facturation en ligne, etc.

Adobe Campaign v8 a fortement amélioré son infrastructure, sa sécurité, sa délivrabilité et sa surveillance.

![](assets/home-page.png)

## Fonctionnalités principales{#key-capabilities}

Les fonctionnalités principales sont répertoriées ci-dessous.

### Gestion de workflows centrale{#central-wf-mgt}

Améliorez la vitesse et l’échelle relatives à chaque aspect de vos campagnes marketing, de la création de segments à la préparation des messages, en passant par leur diffusion.

Adobe Campaign vous permet de synchroniser facilement vos canaux à l’aide d’une seule interface conviviale pour l’orchestration des campagnes. Ainsi, vos canaux en ligne — tels que les e-mails, le web, les appareils mobiles et les réseaux sociaux — correspondent à vos canaux hors ligne, notamment le courrier, le centre d’appels, le magasin, etc. Il vous permet d’offrir à vos clients une expérience cohérente et contextuelle au niveau des canaux numériques et traditionnels. Adobe Campaign facilite la diffusion de contenu vers tous les chemins que vos clients peuvent emprunter, sur n’importe quel canal.

![](../assets/do-not-localize/glass.png) [En savoir plus sur les workflows de Campaign](../config/workflows.md)

### Marketing par e-mail personnalisé {#perso-email-mkt}

Créez des e-mails personnalisés et pertinents qui sont également conformes au reste de l&#39;expérience client.

Avec Adobe Campaign, vous pouvez améliorer vos e-mails, les personnaliser et les rentabiliser. Les e-mails sont faciles à créer et à diffuser. Campaign v8 vous offre la possibilité de concevoir, de personnaliser, de tester, d’affiner et d’améliorer chaque message que vous envoyez.

![](../assets/do-not-localize/glass.png) [En savoir plus sur les fonctionnalités de personnalisation](create-message.md)

### Gestion des données client {#customer-data-mgt}

Affichez l’ensemble de vos clients afin de pouvoir créer rapidement des campagnes personnalisées à l’échelle de l’entreprise.

Adobe Campaign vous aide à créer des profils client à partir des données collectées sur tous vos canaux. Avec ce profil, vous pouvez orchestrer des campagnes sur plusieurs canaux. En connectant tous vos canaux marketing, vous pouvez personnaliser les différents parcours que chaque client suivra de la manière qui lui sera logique.

![](../assets/do-not-localize/glass.png) [En savoir plus sur la gestion des données client](audiences.md)

### Gestion de campagnes la plus performante {#best-in-campaign-mgt}

Adobe Campaign v8 offre aux spécialistes marketing des fonctionnalités riches pour planifier, lancer et mesurer des campagnes sur plusieurs canaux.

Les fonctionnalités incluent un profil intégré qui fournit une vue unique du client. Gestion des données et segmentation pour la création d’audiences de campagne à grande échelle. Gestion des workflows cross-canal pour automatiser les campagnes multicanal et de plusieurs vagues. Messagerie intégrée, ce qui réduit la dépendance à l’égard des FAI coûteux. Rapports et analyses pour comprendre le comportement des clients et les performances des campagnes.

![](../assets/do-not-localize/glass.png) [En savoir plus sur la gestion de campagnes](campaigns.md)


### Connexions à Adobe Experience Platform {#connection-to-aep}

Adobe Campaign v8 prend en charge les connecteurs de données avec Real-Time CDP et Adobe Experience Platform, de sorte que les entreprises puissent exploiter le profil client unifié en temps réel.

En outre, Adobe Campaign v8 est nativement intégré aux fonctionnalités d’orchestration des parcours en temps réel afin que les spécialistes marketing puissent réutiliser les mêmes modèles et fonctionnalités de diffusion dans Adobe Campaign pour interagir avec les clients en temps réel. Ces investissements vont permettre d’optimiser l’expérience client dans Adobe Campaign. Ils débloqueront notamment de nouveaux cas d’utilisation, tels que la possibilité d’ajouter des parcours clients en temps réel personnalisés aux campagnes.

Vous pouvez également configurer l&#39;optimisation de l&#39;heure d&#39;envoi prédictive ainsi que le score d&#39;engagement prédictif grâce à l&#39;IA dédiée au parcours. Cela permet d&#39;augmenter les taux d&#39;ouverture, les clics et les revenus.

[ ![](../assets/do-not-localize/glass.png)En savoir plus sur les intégrations de Campaign](../connect/integration.md).


### Managed Cloud Services {#acms-desc}

Adobe Campaign v8 est disponible en tant que service Managed Cloud Services, offrant une supervision proactive, des alertes rapides et une gouvernance des services.

Adobe Managed Cloud Service offre aux spécialistes marketing une solution de gestion de campagnes cross-canal plus agile, sécurisée et évolutive, avec un coût total de possession faible. La nouvelle offre associe des services à une supervision proactive et à des alertes opportunes.

>[!NOTE]
>
>La nouvelle architecture cloud permet à Campaign de rationaliser les processus, de réduire les coûts, de gérer les risques et d’améliorer la sécurité des données. Votre environnement Campaign v8 est fourni avec un cloud privé virtuel (VPC) dédié et préconfiguré pour vous.

### Vitesse et échelle {#speed-scale}

Adobe Campaign peut désormais tirer parti des technologies de base de données à l’échelle du cloud pour améliorer considérablement son échelle et sa vitesse.

[Campaign v8 Enterprise](../architecture/enterprise-deployment.md) présente le concept de **Full Federated Data Access** (FFDA) : toutes les données sont désormais distantes sur la base de données cloud. Avec cette nouvelle offre, Campaign v8 simplifie la gestion des données : aucun index n&#39;est requis sur la base de données cloud. Il vous suffit de créer les tables et de copier les données pour démarrer. [!DNL Snowflake] est la base de données cloud de Campaign. Grâce à sa vitesse et son endurance, vous ne constaterez aucun pic de surcharge d&#39;activité du système. La technologie de base de données cloud ne nécessite pas de maintenance spécifique pour garantir le niveau de performances attendu.

![](../assets/do-not-localize/glass.png) [En savoir plus sur le déploiement d’Enterprise (FFDA)](../architecture/enterprise-deployment.md)

>[!CAUTION]
>
>* Campaign v8 est **uniquement** disponible en tant que Managed Cloud Service et ne peut pas être déployé dans des environnements on-premise ou hybrides.
>
>* La migration automatisée depuis un environnement Campaign Classic v7 existant n’est pas encore disponible.


## Interface d&#39;administrateur en libre-service{#self-service-admin}

En tant qu&#39;administrateur de produit, vous pouvez gérer les paramètres et suivre l&#39;utilisation de chacune de vos instances Campaign v8 avec le **Panneau de contrôle Campaign**.

Grâce à une interface utilisateur intuitive, les administrateurs peuvent surveiller l&#39;utilisation des ressources clés, effectuer des tâches avancées telles que les listes autorisées d&#39;adresses IP, la surveillance de l&#39;espace de stockage SFTP, la gestion des clés, etc. Cette interface en libre-service vous apporte davantage de flexibilité et vous permet d&#39;effectuer les opérations suivantes :

* Modifiez rapidement par vous-même les paramètres sans contacter le support Adobe
* Configurez les paramètres en fonction de vos besoins métier à différents instants
* Renforcez la sécurité en contrôlant les paramètres d&#39;accès au cas par cas

![](assets/subdomain1.png)

![](../assets/do-not-localize/glass.png) [Apprenez-en davantage sur le panneau de contrôle Campaign](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/key-features.html?lang=fr){target="_blank"}


