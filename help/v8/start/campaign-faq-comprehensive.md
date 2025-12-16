---
title: Questions fréquentes sur Campaign v8
description: Obtenez des réponses aux questions courantes d’Adobe Campaign v8 sur l’installation, la configuration, la messagerie, les workflows, etc
feature: Overview
role: User
level: Beginner
keywords: FAQ, Campaign v8, questions, réponses, aide, support, dépannage
version: Campaign v8
source-git-commit: 9c751429ac3da2a583990ba0d891744353bd65c8
workflow-type: tm+mt
source-wordcount: '10219'
ht-degree: 13%

---

# Questions fréquentes {#faq}

Obtenez des réponses rapides aux questions les plus courantes sur Adobe Campaign v8. Que vous débutiez ou que vous recherchiez une aide de configuration avancée, vous trouverez des réponses organisées par sujet ci-dessous.

**Vous découvrez Campaign ?** Commencer par [Prise en main](#getting-started) pour en savoir plus sur l’essentiel.\
**Besoin d’aide sur les versions ?** les informations de version et les processus de mise à niveau[&#x200B; consultez &#x200B;](#upgrades)Mises à niveau.\
**Migrer depuis v7 ou Standard ?** Voir [Campaign v8 et versions précédentes](#v7-differences) pour obtenir des différences et des conseils sur la transition.\
**Besoin d’aide technique ?** vérifier [développeurs](#developers) et [paramètres de Campaign](#settings).\
**Vous ne trouvez pas la réponse ?** Visitez notre [Forums communautaires](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community?profile.language=fr){target="_blank"} ou [contactez l’assistance](#get-help).

**Conseil :** utilisez Ctrl+F (Cmd+F sur Mac) pour rechercher des mots-clés spécifiques sur cette page. Cliquez sur une question pour développer la réponse.


## Prise en main {#getting-started}

Découvrez les éléments essentiels pour commencer à utiliser Adobe Campaign v8, de l’installation et de la connexion à la création de vos premières campagnes.

+++ Qu’est-ce qu’Adobe Campaign v8 ?

Adobe Campaign v8 est une puissante plateforme d’automatisation du marketing cross-canal qui vous permet de créer, de coordonner et de diffuser des campagnes personnalisées sur des canaux e-mail, mobiles, sociaux et hors ligne. Il associe une base de données marketing robuste, un moteur d’orchestration des campagnes et des fonctionnalités d’interaction en temps réel pour impliquer les clients dans l’ensemble de leur parcours.

**Fonctionnalités clés : gestion de campagnes multicanal** segmentation et ciblage d&#39;audience, automatisation des workflows, personnalisation à grande échelle, messagerie en temps réel et par lots, reporting et analyse, intégration à Adobe Experience Cloud.

**&#x200B;**&#x200B;Ce qui rend v8 unique : architecture native au cloud (Managed Cloud Services uniquement), performances à l’échelle de l’entreprise optimisées par la base de données Snowflake, mises à niveau automatiques, sécurité renforcée et intégration bidirectionnelle à Adobe Experience Platform.

**Idéal pour** les équipes marketing d’entreprise qui gèrent des campagnes complexes à volume élevé sur plusieurs canaux et points de contact client.

**Rubriques connexes :**

[&#x200B; Description du produit Campaign v8 &#x200B;](https://helpx.adobe.com/fr/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"} | [Nouveautés de v8](whats-new.md) | [Guide de prise en main](get-started.md)

+++

+++ Comment télécharger Campaign ?

Vous pouvez obtenir le programme d&#39;installation et la console cliente à partir du Centre de téléchargement d&#39;Adobe.

En tant qu’utilisateur administrateur, accédez à Adobe [Distribution logicielle](https://experience.adobe.com/#/downloads/content/software-distribution/fr/campaign.html){target="_blank"} pour télécharger Adobe Campaign.

En savoir plus sur le Centre de distribution [sur cette page](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=fr){target="_blank"}.

+++

+++ Comment se connecter à Campaign v8 ?

Vous devez télécharger et installer la console cliente Campaign pour vous connecter à Adobe Campaign. [En savoir plus](connect.md).

À compter de la version 8.6 de Campaign, vous avez accès à l’**interface utilisateur web de Campaign**, disponible via l’environnement Adobe Experience Cloud central. Experience Cloud est une famille intégrée d’applications, de produits et de services de marketing numérique d’Adobe.

Découvrez comment vous connecter à Adobe Experience Cloud et accéder à l’interface web d’Adobe Campaign [sur cette page](campaign-ui.md#ac-web-ui). Pour en savoir plus, consultez la [documentation sur l’interface d’utilisation d’Adobe Campaign Web](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/campaign-web-home){target="_blank"}.


**Rubriques connexes :**

[Installation de la console cliente](connect.md) | [Interface utilisateur de Campaign](campaign-ui.md) | [Autorisations utilisateur](gs-permissions.md)

+++

+++ Puis-je me connecter à Campaign v8 avec un Adobe ID ?

Oui ! Grâce à l&#39;intégration avec l&#39;IMS (système Adobe Identity Management), les utilisateurs se connectent à la console Adobe Campaign à l&#39;aide de leur Adobe ID. Cette intégration présente les avantages suivants :

* utilisation d&#39;un même identifiant pour toutes les solutions Experience Cloud
* mémorisation de la connexion lors de l&#39;utilisation d&#39;Adobe Campaign avec les différentes intégrations
* politique de gestion de mot de passe plus sécurisée
* utilisation de comptes de type Federated ID (fournisseur d&#39;identité externe)

[En savoir plus](connect.md) sur l’accès à Campaign v8 avec un Adobe ID.

+++

+++ Quelles notions concernant l&#39;interface utilisateur de Campaign faut-il connaître ? 

Reportez-vous à [cette section](campaign-ui.md) pour en savoir plus sur les bases de l’interface utilisateur d’Adobe Campaign.

À compter de la version 8.6 de Campaign, vous avez également accès à la nouvelle **interface utilisateur web de Campaign**, disponible via l’environnement Adobe Experience Cloud central.

[En savoir plus dans la documentation de l’interface utilisateur web d’Adobe Campaign](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/campaign-web-home){target="_blank"}.

+++

+++ Comment configurer les autorisations utilisateur ?

En tant qu&#39;administrateur de Campaign, vous pouvez configurer des autorisations pour les utilisateurs de votre organisation.

Il s&#39;agit d&#39;un ensemble de droits et de restrictions qui autorisent ou refusent :

* Accès à certaines fonctionnalités
* l’accès à certaines données
* Créer, modifier et/ou supprimer des données

**Rubriques connexes :**

[Prise en main des autorisations](gs-permissions.md) | [Gérer les autorisations utilisateur](manage-permissions.md) | [Ajouter des autorisations sur les dossiers](folder-permissions.md)

+++

+++ Comment sélectionner l’audience de mes messages ? 

Campaign propose plusieurs méthodes de ciblage pour sélectionner l&#39;audience appropriée à vos messages :

**Méthodes de ciblage :**

* **Requêteur** - Créez des audiences à l’aide de filtres visuels sur les attributs, les comportements ou les données démographiques des destinataires
* **Listes** - Utilisez des listes de destinataires statiques ou dynamiques prédéfinies
* **Import de fichiers** - Chargez des fichiers de destinataires externes pour des campagnes ponctuelles.
* **Workflows** - Créez une logique de ciblage complexe avec des activités de requête, de partage et d’enrichissement
* **Filtres prédéfinis** - Appliquez des filtres prêts à l’emploi (clients actifs, abonnés, VIP).
* **Segments depuis Adobe Experience Platform** - Tirez parti de profils unifiés et de segments en temps réel

Vous pouvez combiner plusieurs critères (emplacement, historique d’achat, engagement) et utiliser des exclusions, des intersections ou des unions pour affiner votre audience.

**Rubriques connexes :**

[Définition d’audiences dans Campaign v8](../audiences/gs-audiences.md) | [Requêteur](query-editor.md) | [Mappings de ciblage](../audiences/target-mappings.md)

+++

+++ Comment créer et envoyer un premier email ? 

La création de votre premier e-mail dans Campaign v8 est simple. Commencez à partir d’un modèle, sélectionnez votre audience cible, concevez votre contenu avec de la personnalisation, testez-le avec des BAT, puis envoyez-le. Campaign propose deux interfaces pour la création d’e-mails : la console cliente **console cliente** complète destinée aux utilisateurs avancés, et l’interface utilisateur web **IU web de Campaign** moderne, qui permet de créer des e-mails plus rapidement et de manière plus intuitive.

Étapes clés de **5 :**

1. **Créer une diffusion** - Commencez à partir d’un modèle d’e-mail ou créez-en une
2. **Définir l’audience** - Sélectionnez les destinataires à l’aide de requêtes, de listes ou de workflows
3. **Concevoir du contenu** - Utilisez le concepteur d’e-mail pour créer votre message avec des champs de personnalisation
4. **Envoyer des BAT** - Validez le rendu et le contenu sur les appareils et les clients de messagerie
5. **Analyser et envoyer** - Exécutez l’analyse de diffusion pour vérifier les erreurs, puis envoyez votre e-mail

**Rubriques connexes :**

[Conception et validation des e-mails](../send/email.md) | [Créer la première diffusion](create-message.md) | [&#x200B; Modèles de diffusion &#x200B;](../send/create-templates.md) | [Personnaliser le contenu](../send/personalize.md)

+++

+++ Comment traduire un message d’erreur ? 

Un message d&#39;erreur est affiché dans une langue étrangère ? Tous les messages d&#39;erreur et leur traduction sont répertoriés sur [cette page](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=fr){target="_blank"}.

+++

+++ Comment signaler un problème ?

Pour contacter le service clientèle d’Adobe, connectez-vous à [Adobe Admin Console](https://adminconsole.adobe.com/overview){target="_blank"} pour créer un dossier ou démarrer une session de conversation.

Nécessite des comptes individuels avec les autorisations appropriées. Si vous ne parvenez pas à vous connecter, demandez l’accès via Experience League. [En savoir plus](https://helpx.adobe.com/fr/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}

Vous pouvez également rejoindre [la communauté Campaign](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community?profile.language=fr){target="_blank"} pour rechercher des réponses ou poser des questions aux experts.

+++

+++ Avec quels systèmes et composants Campaign v8 est-il compatible ?

Vous trouverez la liste de tous les systèmes et composants pris en charge dans le dernier build de Campaign dans la [matrice de compatibilité Adobe Campaign](compatibility-matrix.md).

+++

+++ Puis-je utiliser Campaign v8 avec d’autres solutions Adobe ?

Oui. Campaign v8 s’intègre de manière transparente aux solutions Adobe Experience Cloud pour un écosystème marketing unifié.

**Intégrations clés :** Adobe Experience Platform (profils unifiés, données en temps réel), Adobe Analytics (mesure des performances), Adobe Target (personnalisation), Adobe Experience Manager (gestion de contenu), Adobe Audience Manager (segments d’audience).

**Configuration :** nécessite une authentification Adobe IMS, automatiquement configurée pour Campaign v8 Managed Cloud Services.

**Rubriques connexes :**

[Intégrations Adobe Campaign](../connect/integration.md) | [Connexion à Adobe ID](connect.md)

+++

+++ Quelles sont les limites de Campaign v8 ?

Campaign v8 apporte des améliorations significatives en termes de performances, mais présente quelques différences architecturales par rapport à Campaign Classic v7, en particulier dans les déploiements FFDA.

**Considérations principales :**

* **Architecture FFDA** - Utilise la base de données cloud (Snowflake) avec différents modèles d’accès aux données
* **Mises à jour de données** - doivent être effectuées dans des workflows, et non via un accès direct à la base de données.
* **Optimisé pour les lots** - Optimisé pour les opérations par lots plutôt que pour les mises à jour individuelles haute fréquence.
* **Non disponible dans FFDA** - Questionnaires, Marketing Resource Management (MRM), certains connecteurs spécifiques

**Impact de la migration :** le code personnalisé utilisant des écritures de base de données directes nécessite une refactorisation. Les intégrations d’API peuvent nécessiter une adaptation pour le traitement par lots.

Ces limitations évoluent à mesure qu’Adobe améliore v8. Consultez la documentation la plus récente pour connaître le statut actuel.

**Rubriques connexes :**

[Migration de Campaign v7 vers v8](../start/v7-to-v8.md#limitations) | [Architecture FFDA](../architecture/enterprise-deployment.md)

+++

+++ En tant qu&#39;utilisateur de Campaign Classic v7, puis-je migrer vers Campaign v8 ?

La migration automatisée depuis un environnement Campaign Classic v7 existant n’est pas encore disponible.

Campaign v8 est **uniquement** disponible en tant que Managed Cloud Service et ne peut pas être déployé dans des environnements On-Premise ou hybrides.

Pour plus d’informations sur le processus de migration, contactez votre représentant ou représentante Adobe.

Pour en savoir plus, consultez la section [Campaign v8 et versions précédentes](#v7-differences).

+++


## Mises à niveau {#upgrades}

Découvrez comment vérifier votre version de Campaign, comprendre le processus de mise à niveau et rester informé des nouvelles versions. Campaign v8 Managed Cloud Services gère automatiquement les mises à niveau avec un minimum d’interruption.

+++ Quelle est ma version de Campaign ?

Vérifiez les [numéros de version et de build](upgrades.md#version) depuis le menu **Aide > A propos...** de la console cliente de Campaign.

+++

+++ Comment effectuer une mise à niveau de Campaign vers la dernière version ?

Adobe Campaign fait l’objet de mises à jour régulières. Des versions mineures sont publiées chaque année avec de nouvelles fonctionnalités, des améliorations et des correctifs. En outre, nous publions périodiquement des builds avec des correctifs cumulatifs uniquement.

Cette fréquence régulière de mise à jour a pour but de vous fournir les dernières fonctionnalités et améliorations. Vous bénéficiez ainsi d&#39;un environnement sécurisé et d&#39;une expérience optimale avec notre produit. C’est la raison pour laquelle nous pensons qu’il est important que vous exécutiez la version la plus récente d’Adobe Campaign.

**Remarque :** en tant qu’utilisateur Managed Cloud Services, votre instance est mise à niveau par Adobe avec de nouvelles versions.

En savoir plus sur les [versions et mises à niveau de Campaign](upgrades.md).

+++

+++ Comment recevoir des informations sur la sortie d’une nouvelle version ?

Restez informé des nouvelles versions de Campaign par le biais des canaux suivants :

* **Représentant Adobe** - Vous contacte directement lorsqu&#39;une nouvelle version est disponible
* **Notes de mise à jour** - Toutes les versions et modifications documentées dans [Notes de mise à jour de Campaign](release-notes.md)
* **Mises à jour de produit prioritaires par Adobe** - [Abonnement](https://www.adobe.com/fr/subscription/priority-product-update.html){target="_blank"} pour les notifications par e-mail
* **Communauté Campaign** - Rejoignez les [discussions](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community?profile.language=fr){target="_blank"} pour obtenir des mises à jour précoces.

En tant qu’utilisateur Managed Cloud Services, Adobe gère les mises à niveau et coordonne le timing avec vous.

**Rubriques connexes :**

[Notes de mise à jour](release-notes.md) | [Nouveautés](whats-new.md) | [Versions et mises à niveau de Campaign](upgrades.md)

+++

+++ Pourquoi mon entreprise a-t-elle besoin d’une mise à niveau ?

La mise à niveau vers la dernière version de Campaign est essentielle pour la sécurité, les performances et la qualité de support.

**Principaux avantages :**

* **Sécurité renforcée** - Protection contre les vulnérabilités, correctifs les plus récents, protection des données renforcée
* **Meilleure prise en charge** - Résolution plus rapide des problèmes, accès aux correctifs, prise en charge prioritaire des versions récentes
* **Performances améliorées** - Optimisation des bases de données et des workflows, meilleure évolutivité, opérations plus fiables
* **Nouvelles fonctionnalités** - Dernières fonctionnalités, intégrations Adobe Experience Cloud améliorées, améliorations de l’interface utilisateur moderne

Adobe recommande vivement d’exécuter la version la plus récente. En tant que client(e) Managed Cloud Services, Adobe effectue les mises à niveau avec un minimum d’interruption.

**Rubriques connexes :**

[Versions et mises à niveau de Campaign](upgrades.md) | [Nouveautés](whats-new.md) | [Matrice de compatibilité](compatibility-matrix.md)

+++

+++ Quel est le processus et la chronologie d’une mise à niveau ?

En tant que client(e) Managed Cloud Services, Adobe gère l’ensemble du processus de mise à niveau avec un impact minimal sur vos opérations.

**Processus:**

1. **Notification** - Adobe vous avertit des semaines à l’avance
2. **Planification** - Planifiez la mise à niveau au moment optimal avec votre représentant Adobe
3. **Préparation** - Adobe prépare l’environnement et le valide
4. **Exécution** - Adobe met à niveau l’infrastructure avec un temps d’arrêt minimal
5. **Validation** - Tests réalisés par Adobe après la mise à niveau
6. **Mise à niveau de la console cliente** - Mettez à niveau vos consoles clientes pour qu’elles correspondent à la version du serveur

**Vos responsabilités :**

* Coordonner les parties prenantes internes pour le timing
* [Mettre à niveau les consoles clientes](connect.md#upgrade-ac-console) vers la nouvelle version
* Tester les campagnes et les workflows après la mise à niveau
* Signaler les problèmes à l’assistance Adobe

Adobe effectue la mise à niveau de l’infrastructure. Vous n’avez pas besoin d’effectuer d’actions techniques sur les serveurs.

**Rubriques connexes :**

[Versions et mises à niveau de Campaign](upgrades.md) | [Mettre à niveau la console cliente](connect.md#upgrade-ac-console) | [Notes de mise à jour](release-notes.md)

+++


## Campaign v8 et versions précédentes {#v7-differences}

Découvrez les principales différences entre Campaign v8 et les versions précédentes (Classic v7 et Standard), notamment l’architecture, le déploiement, les chemins de migration et les modifications de fonctionnalités. Que vous veniez de Campaign Classic v7 ou de Campaign Standard, découvrez les nouveautés et comment effectuer une transition en douceur.


+++ Quelles sont les principales différences entre Campaign v8 et les versions précédentes ?

Campaign v8 repose sur une architecture moderne native cloud, avec des améliorations significatives :

* **Managed Cloud Services uniquement** - Entièrement hébergé par Adobe (aucune option on-premise/hybride)
* **Performances supérieures** - Jusqu’à 20 millions d’opérations/heure, avec une architecture Full Federated Data Access (FFDA)
* **Nouvelle UI web de Campaign** - Interface moderne et intuitive, en plus de la console classique
* **Mises à niveau automatiques** - Toujours sur la dernière version sans interruption
* **Fonctionnalités améliorées** - Assistant IA, notifications push enrichies, SMS mis à niveau, intégrations améliorées avec Adobe Experience Cloud

**Pour les utilisateurs de Campaign Classic v7 :** découvrez [la transition de la v7 vers la v8](v7-to-v8.md) notamment les modifications d’architecture, les fonctionnalités non disponibles et les considérations relatives à la migration.

**Pour les utilisateurs de Campaign Standard :** découvrez le [guide de migration vers la v8](acs-to-v8.md) et le [guide de migration de Campaign Standard](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

**Rubriques connexes :**

[Fonctionnalités clés de Campaign v8](whats-new.md) | [&#x200B; Architecture de Campaign v8 &#x200B;](../architecture/architecture.md) | [Matrice des fonctionnalités](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/start/capability-matrix){target="_blank"} | [Mécanismes de sécurisation et limitations](ac-guardrails.md)

+++

+++ Dois-je migrer de Campaign Classic v7 ou Campaign Standard vers v8 ?

Campaign v8 est une plateforme Adobe idéale pour les organisations qui ont besoin de campagnes volumineuses (20 millions d’opérations par heure), d’une interface utilisateur web moderne, d’avantages natifs dans le cloud et d’une prise en charge à long terme.

**Principaux avantages :**

* **Pour les utilisateurs de Campaign Standard** interface utilisateur web familière, parité des fonctionnalités (rapports dynamiques, API REST, pages de destination), migration fluide des données
* **Pour les utilisateurs de Campaign Classic v7** : interface double (console + interface utilisateur web), meilleures performances, mises à niveau automatiques, architecture FFDA améliorée

**Envisagez une migration si vous :**

* Vous gérez des volumes de données importants ou rencontrez des problèmes de performances.
* Envie de réduire les frais généraux informatiques et la gestion de l’infrastructure
* Intégration de Adobe Experience Cloud/Platform requise
* Vous souhaitez disposer d’une technologie évolutive avec des mises à jour automatiques.

**Étapes suivantes :** contactez votre représentant ou représentante Adobe pour évaluer la préparation à la migration et accéder aux outils de migration.

**Rubriques connexes :**

[De Campaign Classic v7 vers v8](v7-to-v8.md) | [Guide de transition Campaign Standard](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/start/acs-migration){target="_blank"} | [Matrice des fonctionnalités](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/start/capability-matrix){target="_blank"}

+++

+++ Campaign v8 peut-il être installé dans un environnement on-premise ou hybride ?

Non. Campaign v8 est exclusivement disponible en tant que **Managed Cloud Service**, entièrement hébergé par Adobe.

**Principaux avantages de Managed Cloud Services :**

* Des performances et une évolutivité supérieures
* Mises à niveau automatiques : toujours sur la dernière version
* Sécurité renforcée avec surveillance continue
* Pas de gestion de l’infrastructure ni de frais généraux informatiques
* Haute disponibilité et reprise après sinistre intégrées

En savoir plus sur l’[architecture de Campaign v8](../architecture/architecture.md) et les [&#x200B; différences entre Campaign v8 et Classic v7](../start/v7-to-v8.md).

+++

+++ Comment migrer mon environnement Campaign Classic v7 On-Premise ou hybride vers Adobe Managed Services ?

La migration vers Adobe Managed Services offre une voie stratégique depuis la version on-premise/hybride v7 vers le cloud, offrant une évolutivité améliorée, une sécurité accrue et une réduction des frais généraux informatiques. Il s’agit souvent d’un tremplin avant de passer à Campaign v8.

**Points clés :**

* Aucun outil de migration automatisée disponible : planification et exécution manuelles requises
* Support Adobe Professional Services vivement recommandé
* Les avantages incluent l’infrastructure cloud, les correctifs de sécurité automatiques, l’assistance d’expertes et d’experts et un accès plus facile à v8.
* La migration implique les vérifications nécessaires, l’audit de l’environnement, le nettoyage des données, la migration intermédiaire et le basculement en production.

**Prise en main :** contactez votre représentant ou représentante Adobe pour évaluer votre environnement et développer un plan de migration détaillé avec Adobe Professional Services.

En savoir plus sur la [migration vers Managed Services](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic-blogs/migrate-your-adobe-campaign-v7-onprem-hybrid-environment-to/ba-p/681605?profile.language=fr){target="_blank"} y compris sur les défis, les bonnes pratiques et la feuille de route de migration détaillée.

+++

+++ Quelles sont les principales différences terminologiques et fonctionnelles dans Campaign v8 ?

Campaign v8 offre la plupart des fonctionnalités v7/Standard avec des améliorations, mais certains termes et fonctionnalités diffèrent. Vous trouverez un résumé des principales modifications ci-dessous.

**Modifications terminologiques importantes (Campaign Standard → v8) :**

* Ressources personnalisées → **Schémas** | Messages → **Diffusions** | Utilisateurs du produit → **opérateurs**
* Groupes de sécurité → **groupes d’opérateurs** | Entités organisationnelles → **Autorisations des dossiers**

**Mises à jour de l’interface utilisateur web de Campaign :**

* Destinataires → **Profils** | Adresses de contrôle → **Profils de test** | Analyse d’une diffusion → **Préparation de la diffusion**
* Listes → **audiences** | Aperçu de l’e-mail → **Simuler du contenu**

**Non disponible dans v8:**

* Déploiements On-premise/hybrides (Managed Cloud Services uniquement)
* Accès direct à la base de données (utilisation des API)
* Gestion manuelle de l’infrastructure (gérée par Adobe)

**Nouvelles fonctionnalités pour les utilisateurs de Campaign Standard :**

* Rapports dynamiques, valorisation de marque centralisée, API REST, améliorations des pages de destination, fragments visuels

**Rubriques connexes :**

[Matrice des fonctionnalités](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/start/capability-matrix){target="_blank"} | Guide de transition [v7 vers v8](v7-to-v8.md) | [Transition de Campaign Standard vers v8](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/start/acs-migration){target="_blank"}

+++


## Profils et audiences {#audiences}

Trouvez des réponses aux questions sur la gestion des profils, la création d’audiences, l’importation de données et le ciblage des destinataires pour vos campagnes.

+++ Comment créer des destinataires ?

Créer manuellement des destinataires dans la console cliente pour des profils individuels, importer depuis des fichiers (CSV/TXT) pour des ajouts en masse, utiliser des formulaires web pour l’auto-enregistrement ou intégrer via des API de systèmes externes. Utilisez des workflows d’importation pour les chargements de données récurrents.

**Rubriques connexes :**

[Création manuelle de profils](../audiences/create-profiles.md) | [Importer des profils depuis un fichier](../audiences/import-profiles.md) | [Collecter des profils avec des formulaires web](../audiences/collect-profiles.md)

+++

+++ Import de profils?

Campaign propose plusieurs méthodes d&#39;import : import de fichiers simple à l&#39;aide de l&#39;assistant d&#39;import, import basé sur les workflows pour les transformations complexes, imports récurrents avec workflows planifiés depuis SFTP et import d&#39;API pour l&#39;intégration par programmation.

Pour les imports de fichiers, préparez votre fichier de données (codage CSV/TXT, UTF-8), utilisez l’assistant ou le workflow d’import, mappez les colonnes aux champs de Campaign, définissez des règles de mise à jour/insertion et testez-les d’abord avec un petit échantillon. Utiliser des workflows pour les imports récurrents et appliquer des règles de déduplication.

**Rubriques connexes :**

[Guide d’importation des données](../start/import.md) | [Workflow d’import récurrent](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html?lang=fr){target="_blank"} | [Activité de chargement des données](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=fr){target="_blank"}

+++

+++ Comment créer des profils de test pour mes diffusions ?

Les profils de test (adresses de contrôle) vous permettent de cibler des destinataires qui ne correspondent pas à des critères de ciblage définis. Vous pouvez ainsi tester votre diffusion avant l’envoi à votre audience principale. Ajoutez-les via **[!UICONTROL Adresses de contrôle]** dans les propriétés de la diffusion ou utilisez le dossier **[!UICONTROL Adresses de contrôle]**.

En savoir plus sur les [profils de test](../audiences/test-profiles.md).

+++

+++ Comment définir la population cible d&#39;une campagne marketing ?

Campaign propose plusieurs méthodes de ciblage : créer des requêtes avec des critères visuels, cibler des listes ou des segments existants, importer des destinataires à partir de fichiers externes (CSV, TXT) ou appliquer des filtres prédéfinis. Vous pouvez combiner des critères avec une logique AND/OR, exclure des populations spécifiques, utiliser des populations témoins et fractionner les critères pour les tests A/B. Prévisualisez toujours la taille de votre population cible avant l’envoi.

**Rubriques connexes :**

[Définir des cibles de campagne](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=fr){target="_blank"} | [Activité Requête](https://experienceleague.adobe.com/fr/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=fr){target="_blank"} | [Créer des audiences](../audiences/create-audiences.md)

+++

+++ Comment créer une liste de profils ?

Une liste est un ensemble statique de destinataires que vous pouvez cibler dans les diffusions et réutiliser dans les campagnes.

**Trois méthodes de création :**

* **Création manuelle :** accédez à **[!UICONTROL Profils et cibles > Listes]** et cliquez sur **[!UICONTROL Créer]**. Ajouter des destinataires à partir d&#39;une requête, par sélection individuelle ou à partir d&#39;un dossier.

* **Automatisation des workflows :** utilisez l’activité **[!UICONTROL Mise à jour de liste]** pour créer et gérer automatiquement des listes à partir des résultats de requête ou des données importées.

* **Lors de l’import :** lors de l’import de profils, créez une liste pour les enregistrer en tant que groupe réutilisable.

**Conseil :** utilisez des workflows pour les listes nécessitant des mises à jour régulières et une création manuelle pour la segmentation ponctuelle.

**Rubriques connexes :**

[Créer des audiences](../audiences/create-audiences.md) | [Activité de mise à jour de liste](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/list-update.html?lang=fr){target="_blank"}

+++

+++ Comment dédupliquer une population avant d&#39;envoyer un message ?

Utilisez l&#39;activité **[!UICONTROL Déduplication]** dans un workflow pour supprimer les destinataires en double avant la diffusion. Placez-le entre vos activités **[!UICONTROL Requête]** et **[!UICONTROL Diffusion]**, puis choisissez vos critères de déduplication (généralement l&#39;adresse e-mail ou l&#39;identifiant du destinataire) et l&#39;enregistrement à conserver.

**Conseil :** toujours dédupliquer avant l’envoi pour s’assurer que chaque personne ne reçoit votre message qu’une seule fois.

En savoir plus sur l’activité [&#x200B; Déduplication &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html?lang=fr){target="_blank"}

+++

+++ Comment identifier et cibler les abonnés à une newsletter ?

Campaign effectue automatiquement le suivi des abonnements aux newsletters par le biais de services d’information. Pour cibler les abonnés :

* Utilisez une activité **[!UICONTROL Requête]** et filtrez sur **[!UICONTROL Abonnements]** > sélectionnez votre service de newsletter
* Ciblez les abonnés directement depuis votre diffusion en choisissant **[!UICONTROL A > Abonnés d&#39;un service d&#39;information]**
* Créer des listes d’abonnés à l’aide de l’activité de workflow **[!UICONTROL Services d’inscription]**

Campaign effectue le suivi de l’historique des abonnements/désabonnements et gère automatiquement les processus d’opt-in/opt-out.

**Rubriques connexes :**

[Gérer les abonnements](../start/subscriptions.md) | [Activité Requête](https://experienceleague.adobe.com/fr/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=fr){target="_blank"}

+++

+++ Quelle est la bonne pratique pour exclure des profils d&#39;une population cible ?

Utilisez l’activité **[!UICONTROL Exclusion]** dans un workflow pour supprimer les profils indésirables de votre cible. Placez-le après vos activités de ciblage et définissez la population à exclure.

En savoir plus sur l’activité [&#x200B; Exclusion &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/exclusion.html?lang=fr){target="_blank"}

+++


## Conception de message {#design}

Découvrez comment concevoir des messages marketing efficaces dans Campaign v8, y compris des modèles d’e-mail, des techniques de personnalisation et du contenu multilingue. Concevez vos messages dans la console cliente ou utilisez la version moderne **Email Designer** de l’interface utilisateur web de Campaign pour améliorer l’expérience de modification visuelle.

+++ Quelles sont les bonnes pratiques pour concevoir des emails dans Campaign ?

Directives clés : assurez-vous d’une conception réactive pour les appareils mobiles, utilisez du code compatible HTML 4.0/XHTML avec le CSS intégré, optimisez les images (sous 100KB) avec du texte de remplacement, utilisez des champs de fusion de personnalisation, testez les clients de messagerie avant l’envoi et incluez une version en texte brut. Visez la taille totale des e-mails sous 500KB pour une délivrabilité optimale.

**Rubriques connexes :**

[Guide de conception des emails](../send/email.md) | [&#x200B; Bonnes pratiques de diffusion &#x200B;](delivery-best-practices.md)

+++

+++ Qu’est-ce qu&#39;un modèle de diffusion ? 

Un modèle de diffusion est une diffusion préconfigurée qui enregistre tous les paramètres et paramètres en vue de les réutiliser dans plusieurs campagnes. Les modèles comprennent les règles de la cible, la conception du contenu, la personnalisation, les paramètres techniques (expéditeur, destinataire) et les règles de typologie. Créez-en une et réutilisez-la pour maintenir la cohérence et accélérer la création de campagnes.

Découvrez comment [créer des modèles de diffusion](../send/create-templates.md)

+++

+++ Est-il possible d&#39;importer facilement du contenu HTML existant pour créer un email dans Campaign ? 

Oui. Importez du contenu HTML par copier/coller direct dans l’éditeur de contenu, par chargement de fichier à partir de votre ordinateur ou par chargement à partir d’une URL. Assurez-vous que votre HTML utilise du code compatible avec les e-mails (HTML 4.0/XHTML) avec le CSS intégré et hébergez les images sur un serveur public. Campaign ajoute automatiquement la personnalisation et le tracking aux HTML importées.

**Conseil :** pour une expérience de conception d’e-mail optimale, utilisez le **Designer d’e-mail** dans l’interface utilisateur web de Campaign, qui offre des fonctionnalités modernes de glisser-déposer et des modèles réactifs intégrés, plutôt que d’importer des données HTML brutes.

Découvrez comment [importer du contenu HTML](../send/defining-the-email-content.md)

+++

+++ Comment créer une newsletter par abonnement dans Campaign ? 

Oui. Utilisez les services d’information de Campaign pour gérer les abonnements aux newsletters. Les fonctionnalités clés incluent la gestion automatique des souscriptions/désinscriptions, le suivi des abonnements, la gestion de la conformité (RGPD, CAN-SPAM), la prise en charge de plusieurs newsletters, l’intégration web pour les formulaires d’inscription et la diffusion ciblée aux abonnés.

Découvrez comment [&#x200B; gérer les abonnements &#x200B;](../start/subscriptions.md)

+++

+++ Comment personnaliser les messages ? 

Campaign offre des fonctionnalités de personnalisation pour créer des messages pertinents et ciblés en fonction des données, du comportement et des préférences des destinataires.

**Options de Personalization :**

* **Champs de personnalisation** - Insérez les données du destinataire (par exemple, `"Hello {{firstName}}")`
* **Blocs de personnalisation** - Utilisez des blocs de contenu prédéfinis ou personnalisés
* **Contenu conditionnel** - Affichez un contenu différent en fonction des critères du destinataire
* **Données comportementales** - Exploitez l’historique de navigation, les modèles d’achat ou les mesures d’engagement

Testez la personnalisation avant l’envoi pour vérifier que les champs de fusion et la logique conditionnelle fonctionnent correctement.

**Rubriques connexes :**

Guide de [Personalization](../send/personalize.md) | [&#x200B; Champs de personnalisation &#x200B;](../send/personalization-fields.md) | [Contenu conditionnel](../send/conditions.md)

+++

+++ Comment personnaliser l’objet des e-mails ?

Les objets personnalisés augmentent considérablement les taux d’ouverture. Campaign vous permet d’insérer de manière dynamique les données de destinataire, d’appliquer une logique conditionnelle et de tester des variations afin d’optimiser l’engagement.

**techniques Personalization :**

* **Champs de base** - Insérer le prénom, le nom, l’emplacement : `"<%@ firstName %>, exclusive offer for you"`
* **Contenu conditionnel** - Différents sujets par segment : `"<% if (recipient.gender == 'F') { %>Special offer just for you<% } else { %>Exclusive deal inside<% } %>"`
* **Données dynamiques** - Incluez l’historique d’achats, les points de fidélité ou les informations de compte
* **Émoticônes** - Ajoutez un aspect visuel (testez d’abord les clients de messagerie).

**Bonnes pratiques :** conservez moins de 50 caractères, testez les jetons de personnalisation avant l’envoi, utilisez les tests A/B pour optimiser, éviter les mots de déclenchement de spam, inclure une proposition de valeur ou une urgence.

**Rubriques connexes :**

[&#x200B; Champs de personnalisation &#x200B;](../send/personalization-fields.md) | [Contenu conditionnel](../send/conditions.md)

+++

+++ Puis-je envoyer des messages multilingues ? 

Oui. Campaign v8 offre des fonctionnalités multilingues. L’approche la plus simple est celle de l’**interface utilisateur web de Campaign**. L’interface utilisateur web offre une diffusion multilingue native avec des variantes de langue : ajoutez des variantes de langue à votre diffusion et Campaign envoie automatiquement la version appropriée en fonction de la langue préférée du destinataire. Disponible pour les e-mails, notifications push, SMS et messages transactionnels.

Fonctionnalités clés : duplication automatique du contenu, envoi automatique basé sur la langue, basculement de la langue par défaut et gestion facile des variantes.

La console cliente prend également en charge le contenu multilingue à l’aide de contenu et de workflows conditionnels, mais nécessite une configuration plus manuelle.

**Rubriques connexes :**

[Diffusions multilingues (interface utilisateur web)](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/msg/multilingual){target="_blank"} | [Contenu conditionnel (console cliente)](../send/conditions.md)

+++

+++ Puis-je localiser un formulaire web ?

Oui. Les applications web de Campaign prennent en charge la localisation multilingue. Définissez des traductions pour tous les éléments de formulaire (libellés, boutons, messages, texte d’erreur), avec la détection automatique de la langue en fonction du profil du destinataire ou des paramètres du navigateur. Plusieurs versions linguistiques sont prises en charge dans une seule application web, avec une langue de remplacement par défaut si nécessaire.

En savoir plus sur [la localisation des applications web](../dev/webapps.md)

+++

+++ Puis-je utiliser du contenu optimisé par l’IA dans mes e-mails ?

Oui, mais **uniquement via l’interface utilisateur web de Campaign**. L’assistant AI, optimisé par Microsoft Azure OpenAI et Adobe Firefly, permet de créer du contenu professionnel et cohérent sur les marques par e-mail, SMS et notifications push.

**Fonctionnalités principales :**

* Générer du texte (copie d’e-mail, lignes d’objet, contenu SMS/push) et des images alignées sur la marque
* Créer des variations de contenu optimisées pour différentes audiences
* Affiner le contenu (élaborer, résumer, reformuler, simplifier)
* Chargement de ressources de marque et obtention du score d’alignement de la marque
* Utiliser du contenu existant comme référence et charger des images de référence de style

**Remarque :** l’assistant d’IA est disponible exclusivement dans l’interface utilisateur web de Campaign et ne prend actuellement en charge que l’anglais. Les utilisateurs ont besoin des autorisations appropriées et doivent accepter un contrat d’utilisation.

**Rubriques connexes :**

[Présentation de l’assistant AI](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/content/ai-assistant/generative-gs){target="_blank"} | [Cas d’utilisation de l’assistant AI](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/content/ai-assistant/generative-uc){target="_blank"} | [Alignement des marques](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/content/ai-assistant/ai-assistant/brands-score){target="_blank"}

+++

## Test et envoi de messages {#send}

Découvrez les bonnes pratiques relatives au test, à la validation, à l’envoi et au suivi de vos messages marketing pour garantir une diffusion réussie de la campagne.

+++ Comment améliorer la délivrabilité des e-mails ?

La délivrabilité des e-mails, composant essentiel de la réussite du programme marketing de chaque expéditeur, est caractérisée par des critères et des règles en constante évolution. Pour naviguer efficacement dans ce monde numérique, il est nécessaire d&#39;affiner régulièrement votre stratégie d&#39;e-mail, en tenant compte des principales tendances de délivrabilité, afin d&#39;atteindre au mieux vos audiences.

Consultez ce guide pour découvrir [bonnes pratiques en matière de délivrabilité](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=fr){target="_blank"}

Découvrir comment implémenter la délivrabilité dans Campaign [dans ce guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html?lang=fr){target="_blank"}

**Rubriques connexes :**

[Prise en main de la délivrabilité](../send/about-deliverability.md) | [Contrôler le contenu du message](../send/control-message-content.md) | [Surveiller la délivrabilité](../send/monitoring-deliverability.md) | [&#x200B; SpamAssassin &#x200B;](../send/spamassassin.md)

+++

+++ Comment puis-je m’assurer que ma diffusion est envoyée sans erreur ?

**Avant l’envoi :** exécutez l’analyse de la diffusion, envoyez des BAT de test, passez en revue les avertissements et vérifiez le nombre cible.

**Pendant/après l’envoi :** surveiller le tableau de bord des diffusions (envoyées, diffusées, retours, erreurs), vérifier les logs de diffusion, suivre les taux de succès/retours, consulter les adresses en quarantaine.

**Bonnes pratiques :** configurer des alertes, utiliser des vagues pour les gros volumes, tester d’abord avec de petits volumes, nettoyer régulièrement la base de données des destinataires, surveiller la réputation de l’expéditeur.

**Rubriques connexes :**

[Suivre et surveiller les diffusions](../send/tracking.md) | [&#x200B; Bonnes pratiques de diffusion &#x200B;](delivery-best-practices.md)

+++

+++ Qu&#39;est-ce que l&#39;analyse de la diffusion ?

L’analyse de la diffusion est une phase de validation que Campaign exécute avant l’envoi. Il calcule la population cible, valide le contenu, recherche les erreurs, applique les règles de typologie et estime le volume de diffusion.

Campaign génère des logs qui affichent les avertissements et les erreurs. Les erreurs bloquent la diffusion et doivent être corrigées ; les avertissements sont indicatifs. Consultez toujours les journaux d’analyse avant de les envoyer.

Pour en savoir plus, consultez le [&#x200B; Guide de l’analyse de la diffusion &#x200B;](../send/delivery-analysis.md)

+++

+++ Pourquoi créer des bons à tirer ?

Les BAT sont des messages de test qui valident votre diffusion avant envoi à votre audience principale. Utilisez des BAT pour vérifier la personnalisation, tester le rendu du contenu sur les clients de messagerie, confirmer les liens et le travail de suivi, vérifier les images et les pièces jointes et valider la réactivité mobile.

Les BAT permettent de détecter les erreurs avant qu’elles n’atteignent des milliers de destinataires, d’activer l’approbation des parties prenantes et de tester l’emplacement de la boîte de réception. Envoyez des BAT à plusieurs clients de messagerie et appareils et obtenez toujours une approbation avant l’envoi des BAT par l’exploitation.

Pour en savoir plus, consultez le guide [BAT et aperçu](../send/preview-and-proof.md)

+++

+++ Comment utiliser les adresses de contrôle dans Adobe Campaign ?

Les adresses de contrôle sont des destinataires spéciaux automatiquement ajoutés à chaque diffusion à des fins de test, d’assurance qualité et de surveillance, sans correspondre à vos critères cibles. Utile pour la surveillance continue, les tests d’emplacement de la boîte de réception, la validation du publipostage direct et la visibilité des parties prenantes.

**Principales différences par rapport aux BAT :**

* **Adresses de contrôle** - ajoutées automatiquement aux diffusions de production, comptabilisées dans le volume d’envoi
* **BAT** - Le test envoie avant la production, ne pas comptabiliser dans le volume, utilisé pour la validation.

Gérez les adresses de contrôle dans **[!UICONTROL Ressources > Gestion de campagne > Adresses de contrôle]**. Gardez les listes petites pour éviter d’impacter les mesures de diffusion.

Pour en savoir plus, consultez le [guide des adresses de contrôle](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/delivery-control.html?lang=fr){target="_blank"}

+++

+++ Comment configurer un processus de validation avant l&#39;envoi des messages ?

Campaign fournit des workflows de validation pour s’assurer que les messages répondent aux normes de qualité avant envoi. Configurez les validations du contenu, de la cible, de l’extraction (publipostage direct) et du budget au niveau de la campagne ou de la diffusion.

**Configuration:**

Créez des groupes d’opérateurs dans **[!UICONTROL Administration > Gestion des accès > Groupes d’opérateurs]**, puis affectez des groupes de validation dans les propriétés de la campagne ou de la diffusion. Campaign envoie des e-mails de notification aux réviseurs qui peuvent approuver, rejeter ou demander des modifications.

**Pour les diffusions autonomes (hors campagne) :**

Utilisez les **BAT comme processus d’approbation**. Envoyez des BAT à votre groupe d’approbation pour validation et envoyez toujours un nouveau BAT après avoir apporté des modifications pour vous assurer que les parties prenantes examinent la dernière version.

**Rubriques connexes :**

[&#x200B; Validation de la diffusion &#x200B;](../send/preview-and-proof.md) | [Validations de campagne](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=fr){target="_blank"}

+++

+++ Puis-je exécuter des tests A/B sur mes diffusions ?

Oui ! Campaign vous permet d’exécuter des tests A/B (également appelés tests de partage) pour optimiser les objets, le contenu, les noms d’expéditeur, les heures d’envoi, etc. en comparant les performances entre différentes variantes.

**Ce que vous pouvez tester :**

* **Lignes d&#39;objet** - Comparez les taux d&#39;ouverture sur différents objets
* **Variations de contenu** - Testez différentes dispositions, appels à l’action ou images
* **Informations sur l’expéditeur** - Tester l’impact du nom de l’expéditeur ou de l’adresse
* **Heure d’envoi** - Identifier les fenêtres de diffusion optimales
* **Stratégies Personalization** - Comparer du contenu personnalisé au contenu générique

**Fonctionnement :**

1. Créer votre diffusion et définir des variantes de test (3 maximum)
2. Partagez votre audience (généralement entre 10 et 20 % pour les segments de test).
3. Campaign envoie des variantes pour tester les segments et suivre les performances
4. La variante gagnante envoie automatiquement à l’audience restante (ou vous sélectionnez manuellement le gagnant).

**Disponible dans :** l’interface utilisateur web de Campaign et la console cliente. L’interface utilisateur web offre une configuration plus simple avec une comparaison visuelle.

**Rubriques connexes :**

[Analyse de la diffusion](../send/delivery-analysis.md) | [Envoyer et suivre les diffusions](../send/send.md)

+++

+++ Qu&#39;est-ce qu&#39;une règle de typologie ?

Les règles de typologie sont une logique commerciale automatisée appliquée lors de l’analyse de la diffusion pour valider et optimiser l’envoi des messages. Ils assurent la conformité aux politiques marketing, protègent la délivrabilité et évitent la fatigue des clients.

**Principaux types de règle :**

* placer sur la liste bloquée **Règles de filtrage** - Exclure les destinataires (inscrits, désabonnés, mis en quarantaine)
* **Règles de pression** - Contrôlez la fréquence des messages pour éviter de surcharger les destinataires
* **Règles de capacité** - Limite le volume de messages pour les limites de capacité de traitement ou de FAI.
* **Règles de contrôle** - Vérifier la validité du message (objet, lien de désabonnement, format de l’expéditeur)

Les règles sont regroupées en typologies et appliquées lors de l&#39;analyse de la diffusion. Campaign peut exclure des destinataires, bloquer la diffusion ou générer des avertissements en fonction des règles.

Pour en savoir plus, consultez le [guide des règles de typologie](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=fr){target="_blank"}

+++

+++ Comment envoyer des emails par vagues ?

Oui. L’envoi par vague divise votre diffusion en plusieurs lots envoyés à des intervalles planifiés. Cela est essentiel pour les campagnes à volume élevé afin d’équilibrer la charge du serveur, d’empêcher le ralentissement des FAI, de construire la réputation de l’expéditeur avec de nouvelles adresses IP et de gérer les désinscriptions/bounces entre les vagues.

**Configuration:**

Dans les propriétés de votre diffusion, activez l’envoi de vagues et définissez le nombre de vagues (ou la taille du lot), l’intervalle entre les vagues et la répartition des vagues (pourcentages linéaires ou personnalisés). Campaign divise automatiquement votre population cible et envoie chaque vague selon le calendrier prévu.

Utilisez les vagues pour les campagnes volumineuses, surveillez les performances de la première vague avant de continuer et patientez suffisamment entre les vagues pour traiter les rebonds et les désinscriptions.

Découvrez comment [&#x200B; Configurer l’envoi de vagues &#x200B;](../send/configure-and-send.md#sending-using-multiple-waves)

+++

+++ Comment planifier une diffusion ?

Campaign vous permet de planifier des diffusions pour des envois futurs afin d’optimiser les heures d’envoi et de coordonner les campagnes.

**Options de planification :**

* **Propriétés de diffusion** - Envoi immédiat, planification d’une date/heure spécifique ou report par heures/jours
* **Niveau de la campagne** - Coordonner toutes les diffusions d’une campagne
* **Activité Planificateur de workflow** - Pour les diffusions récurrentes, les modèles complexes et les campagnes déclenchées par un événement

Campaign prend également en charge l’optimisation des dates de contact (meilleure heure d’envoi par destinataire) et l’adaptation des fuseaux horaires (même heure locale pour tous les destinataires).

Découvrez comment [&#x200B; Planifier l’envoi de diffusion &#x200B;](../send/configure-and-send.md#schedule-delivery-sending)

+++

+++ Est-il possible d&#39;ajouter une pièce jointe aux emails ?

Oui. Campaign prend en charge les pièces jointes statiques (même fichier pour tous les destinataires) et les pièces jointes personnalisées (différents fichiers par destinataire en fonction des données de profil). Ajoutez des pièces jointes dans la section **[!UICONTROL Pièces jointes]** des propriétés de votre diffusion.

**Remarques importantes :**

* Conserver les pièces jointes de moins de 1 Mo pour une délivrabilité optimale
* Les pièces jointes peuvent déclencher des filtres antispam ; à tester minutieusement avant l’envoi
* Évitez les types de fichiers généralement bloqués par les clients de messagerie (.exe, .zip, .js)
* Pour les fichiers volumineux, pensez à utiliser plutôt des liens de téléchargement suivis

Utilisez des formats de fichiers sécurisés (PDF, JPEG, PNG, DOCX) et testez-les avec des adresses de contrôle avant les envois en production.

Pour en savoir plus, consultez le guide [&#x200B; Pièces jointes d’e-mail &#x200B;](../send/email.md#attachments)

+++

+++ Comment configurer des liens suivis dans une diffusion d&#39;email ?

Campaign convertit automatiquement toutes les URL de votre e-mail en liens trackés afin de surveiller l’engagement des destinataires. Accédez à la section **[!UICONTROL Tracking]** de votre diffusion pour configurer les paramètres de tracking de chaque lien.

**Options de configuration :**

* **Activer/désactiver le suivi** - Contrôler le suivi par lien
* **Libellés du lien** - Ajoutez des noms descriptifs pour les rapports (par exemple, « Shop Now CTA »).
* **Catégories de liens** - Regroupez les liens par type pour une analyse agrégée.
* **Type de tracking** - Effectuez le suivi des clics, des ouvertures ou des deux

Campaign effectue le suivi des liens de contenu, des liens de page miroir et des liens de désabonnement. Elle peut également inclure un pixel de suivi facultatif pour les ouvertures d’e-mail. Utilisez des libellés et des catégories pertinents pour simplifier la création de rapports et identifier rapidement le contenu hautement performant.

**Rubriques connexes :**

[&#x200B; Guide de suivi des liens &#x200B;](../send/tracking.md) | [Bonnes pratiques de tracking](../send/send.md)

+++

+++ Où se trouvent les logs de diffusion et de tracking ?

Accédez directement aux logs de diffusion et de tracking depuis chaque tableau de bord de diffusion. Dans la console cliente, cliquez sur l’onglet **[!UICONTROL Diffusion]** dans la partie inférieure. Dans l’interface utilisateur web de Campaign, accédez à la section **[!UICONTROL Journaux]**.

**Journaux disponibles :**

* **Logs de diffusion** - Messages envoyés avec les détails et le statut du destinataire (envoyés, en attente, en échec)
* **Logs de tracking** - Interactions des destinataires (ouvertures, clics) avec horodatage
* **Logs d&#39;exclusion** - Destinataires exclus avec leurs raisons (quarantaine, règles de typologie, doublons)
* **Journaux de diffusion** - Historique complet des envois, y compris les reprises et les erreurs

Utilisez ces journaux pour résoudre les problèmes de diffusion, analyser l’engagement et maintenir l’hygiène de la liste.

**Rubriques connexes :**

[Surveillance des diffusions](../send/send.md) | [Guide de tracking](../send/tracking.md)

+++

+++ Où obtenir des rapports de diffusion ?

Campaign fournit des rapports intégrés complets pour analyser les performances des diffusions, l’engagement des destinataires et l’efficacité des campagnes. Accédez aux rapports à partir de l’onglet **[!UICONTROL Rapports]** dans n’importe quelle diffusion, depuis le tableau de bord de la campagne ou à partir du menu global **[!UICONTROL Rapports]** pour une analyse intercampagnes.

**Les principaux rapports sont les suivants :**

* **Résumé de diffusion** - Envoi de statistiques, ouvertures, clics, bounces et désabonnements
* **Position des clics** - Carte thermique visuelle des performances des liens
* **Indicateurs de tracking** - Taux de clics publicitaires et mesures d’engagement
* **Échecs** - Analyse des retours avec les raisons des échecs

Les rapports sont disponibles dans la console cliente et l’interface utilisateur web de Campaign avec des visualisations modernes.

**Rubriques connexes :**

[Rapports de diffusion intégrés](../reporting/delivery-reports.md) | [Rapports de campagne](../reporting/gs-reporting.md)

+++

+++ Comment Adobe Campaign qualifie-t-il et gère-t-il les adresses en quarantaine ?

Campaign gère automatiquement une liste de quarantaine pour protéger la réputation de votre expéditeur et améliorer la délivrabilité. Les adresses en quarantaine sont automatiquement exclues des prochaines diffusions jusqu&#39;à ce qu&#39;elles soient validées ou supprimées de la quarantaine.

**Pourquoi les adresses sont-elles mises en quarantaine**

* **Erreurs hard** - Échecs de diffusion permanents (adresse e-mail non valide, domaine inexistant, boîte aux lettres supprimée)
* **Seuil de soft bounce** - Échecs temporaires répétés (boîte pleine, serveur temporairement indisponible) dépassant le seuil d&#39;erreur
* **Plaintes contre le spam** - Les destinataires marquent vos e-mails comme spam
* **Adresses non valides** - Adresses présentant des erreurs de syntaxe ou dont la validation a échoué
* **Placé sur la liste bloquée** - Destinataires qui se sont désinscrits ou ont demandé à être exclus

**Fonctionnement de la quarantaine :**

Campaign effectue le suivi des erreurs de diffusion pour chaque adresse. Lorsqu&#39;une adresse atteint le seuil d&#39;erreur configuré, elle est automatiquement mise en quarantaine et exclue de toutes les prochaines diffusions lors de l&#39;analyse. Les hard bounces (échecs permanents) sont mis en quarantaine immédiatement, tandis que les soft bounces nécessitent plusieurs échecs avant mise en quarantaine.

**Gestion des adresses en quarantaine :**

Accédez à la gestion des quarantaines dans **[!UICONTROL Administration > Gestion de campagnes > Gestion des échecs]**. Vous pouvez afficher les adresses en quarantaine, supprimer manuellement les adresses validées de la quarantaine ou configurer des règles de nettoyage automatique.

**Conseil :** surveiller régulièrement votre liste de quarantaine. L&#39;augmentation des taux de quarantaine signale souvent des problèmes de qualité des données qui nécessitent une attention particulière avant d&#39;affecter la réputation de l&#39;expéditeur.

**Rubriques connexes :**

[&#x200B; Guide de gestion des quarantaines &#x200B;](../send/quarantines.md) | [Gestion des bounces](../send/delivery-failures.md)

+++

## Workflows {#workflows}

Découvrez comment utiliser des workflows pour automatiser les processus, gérer les données et orchestrer des campagnes marketing complexes dans Adobe Campaign.

+++ Qu’est-ce qu&#39;un workflow ? 

Adobe Campaign contient des workflows pour orchestrer l&#39;ensemble des processus et tâches dans les différents modules du serveur applicatif. Cet environnement graphique complet permet de concevoir des processus englobant segmentation, exécution de campagnes, traitement de fichiers, participation humaine, etc. Le moteur de workflow exécute et assure le tracking de ces processus.

Un workflow permet par exemple de télécharger un fichier depuis un serveur, de le décompresser et d&#39;importer ses enregistrements dans la base de données Adobe Campaign.

Un workflow peut également faire intervenir des opérateurs afin de notifier ou valider une opération ou faire un choix. Ainsi, il est possible de créer une action de diffusion, d&#39;assigner une tâche à un ou plusieurs opérateurs qui seront chargés de saisir son contenu ou spécifier sa cible, puis de faire valider le BAT avant de démarrer la diffusion.

[En savoir plus](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=fr){target="_blank"} sur les workflows. Vous pouvez également consulter les [bonnes pratiques en matière de workflow](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=fr){target="_blank"}.

**Rubriques connexes :**

[Prise en main des workflows](../config/workflows.md) | [Créer votre premier workflow](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=fr){target="_blank"} | [Cas pratiques des workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [Surveillance de l’exécution des workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=fr){target="_blank"}

+++

+++ Est-il possible de surveiller l’exécution des workflows ?

Oui. Campaign fournit plusieurs outils de surveillance : tableau de bord des workflows (statut en temps réel et erreurs), logs des workflows (logs d&#39;exécution détaillés), carte thermique (visualisation des activités et des goulets d&#39;étranglement), journal d&#39;audit (suivi des modifications) et alertes (notifications d&#39;échecs).

Pour surveiller, ouvrez le workflow et cliquez sur l’onglet **Journaux**. Les activités ayant échoué apparaissent en rouge.

**Rubriques connexes :**

[Surveillance de l’exécution des workflows](https://experienceleague.adobe.com/fr/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"} | [&#x200B; Bonnes pratiques relatives aux workflows &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=fr){target="_blank"}

+++

+++ Quelles sont les principales étapes pour créer un workflow ?

Créez des workflows pour automatiser les processus marketing dans Campaign :

1. **Créer un workflow** - Accédez à **[!UICONTROL Profils et cibles > Tâches > Workflows de ciblage]** ou **[!UICONTROL Administration > Exploitation > Workflows techniques]** et cliquez sur **[!UICONTROL Créer]**
1. **Ajouter des activités** - Effectuez un glisser-déposer des activités depuis la palette (ciblage, contrôle de flux, activités d&#39;action)
1. **Configurer les activités** - Double-cliquez sur chaque activité pour définir des paramètres et une logique
1. **Connecter les activités** - Liez les activités aux transitions pour définir le flux d’exécution
1. **Tester et valider** - Utilisez le diagramme de workflow pour vérifier la logique, puis testez-le avec un petit jeu de données
1. **Exécuter** - Démarrez le workflow manuellement ou planifiez une exécution automatique

Modèles de workflow courants : importation de données, segmentation d’audience, envoi de diffusion, enrichissement des données et orchestration cross-canal.

**Rubriques connexes :**

[Créer un workflow](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=fr){target="_blank"} | [Activités de workflow](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/about-activities.html){target="_blank"} | [&#x200B; Bonnes pratiques relatives aux workflows &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=fr){target="_blank"} | [Cas pratiques des workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}

+++

+++ Comment automatiser les campagnes récurrentes ?

Utilisez des workflows avec l’activité **Planificateur** pour automatiser les campagnes qui s’exécutent selon un planning régulier (intervalle quotidien, hebdomadaire, mensuel ou personnalisé). Parfait pour les e-mails de bienvenue, les messages d’anniversaire, les envois de newsletter, les rappels de panier abandonné et les rapports réguliers.

**Modèle de configuration :**

1. **Planificateur** - Définir la fréquence (par exemple, « Tous les lundis à 9 h »)
2. **Requête** - Sélectionner l’audience cible avec les critères dynamiques
3. **Enrichissement** (facultatif) - Ajoutez des données de personnalisation
4. **Diffusion** - Configurez votre message (e-mail, SMS, notification push).
5. **Fin** - Le workflow se termine et attend la prochaine exécution planifiée

**Campagnes automatisées courantes :**

* **Série de bienvenue** - Workflow quotidien pour envoyer des e-mails d’intégration aux nouveaux abonnés
* **E-mails d&#39;anniversaire** - Vérification quotidienne des destinataires dont l&#39;anniversaire est spécifié, envoyer un message personnalisé
* **Réengagement** - Ciblage hebdomadaire des utilisateurs inactifs avec des offres de reconquête
* **Newsletters** - Diffusion de contenu hebdomadaire ou mensuelle planifiée
* **Abandon de panier** - Workflow horaire permettant d’identifier et de signaler les abandons de panier

**Conseil :** utilisez le type **diffusion récurrente** dans les workflows pour suivre chaque exécution séparément et conserver les rapports historiques.

**Rubriques connexes :**

[&#x200B; Activité Planificateur &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/scheduler.html?lang=fr){target="_blank"} | [Diffusions récurrentes &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/sending-a-birthday-email.html){target="_blank"} | [Automatisation de Campaign](https://experienceleague.adobe.com/docs/campaign/automation/home.html?lang=fr){target="_blank"}

+++

+++ Comment importer des données dans Campaign ?

**Méthodes :** Assistant d’import (CSV/TXT unique), import basé sur des workflows (**[!UICONTROL Activité Chargement (fichier)]** pour les imports complexes/récurrents avec transformations), API REST (synchronisation programmatique/en temps réel).

**Bonnes pratiques :** tester avec de petits échantillons, utiliser le codage UTF-8, mapper correctement les champs, appliquer la déduplication, planifier des importations volumineuses en période creuse.

**Rubriques connexes :**

[Bonnes pratiques d’import](../start/import.md) | [Activité de chargement des données](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=fr){target="_blank"} | [Workflow d’import récurrent](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html?lang=fr){target="_blank"}

+++

+++ Comment puis-je garantir la qualité des données lors des importations ?

La qualité des données est essentielle pour la réussite de l’exécution d’une campagne. De mauvaises données entraînent des échecs de diffusion, du gaspillage de ressources et des risques de non-conformité. Campaign fournit des outils pour valider, nettoyer et enrichir les données pendant le processus d’importation.

**Étapes de validation des données :**

1. **Validation avant importation** - Vérification du format de fichier, codage (UTF-8), mappage des colonnes, présence des champs obligatoires.
2. **Déduplication** - Utilisez l’activité **[!UICONTROL Déduplication]** pour identifier et gérer les doublons par e-mail, ID ou clés personnalisées
3. **Enrichissement des données** - Utilisez l’activité **[!UICONTROL Enrichissement]** pour ajouter les données manquantes dans les tables Campaign existantes
4. **Normalisation des formats** - Normalisez les numéros de téléphone, les adresses e-mail, les dates, les codes pays à l’aide de JavaScript ou d’un enrichissement.
5. **Règles de validation** - Appliquez des contraintes (format d’e-mail valide, champs obligatoires, plages de valeurs).

**Problèmes courants et correctifs :**

* **Erreurs de codage des caractères** → toujours utiliser le codage UTF-8
* **Le format de date ne correspond pas** → Normaliser au format AAAA-MM-JJ.
* **Adresses e-mail non valides** → utilisez des règles de validation ou JavaScript pour effectuer le filtrage.
* **Enregistrements en double** → toujours inclure l&#39;activité de déduplication avant les mises à jour
* **Champs obligatoires manquants** → Définissez des valeurs par défaut ou rejetez les enregistrements incomplets

**Bonne pratique :** créez un modèle de workflow « qualité des données » réutilisable avec des activités de validation et de nettoyage standard que vous pouvez appliquer à toutes les importations.

**Rubriques connexes :**

[&#x200B; Guide de qualité des données &#x200B;](../start/import.md) | [Activité Déduplication](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html?lang=fr){target="_blank"} | [Activité Enrichissement](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html?lang=fr){target="_blank"}

+++

+++ Quels sont les cas pratiques courants des workflows dans Campaign ?

Les workflows automatisent les processus marketing, notamment :

**Gestion des données :** Importer/charger des données, nettoyage, enrichissement, gestion des listes\
**Automatisation des campagnes :** série de bienvenue, campagnes d’anniversaire, réengagement, abandon de panier\
**Ciblage avancé :** tests A/B, segmentation dynamique, notation des prospects, orchestration cross-canal\
**Surveillance :** surveillance des workflows/diffusions, alertes, maintenance de la base de données\
**Intégration :** synchronisation CRM, intégrations d’API, workflows déclenchés par un événement

**Rubriques connexes :**

[Bibliothèque de cas pratiques de workflow](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"} | [Créer un workflow](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=fr){target="_blank"} | [&#x200B; Bonnes pratiques relatives aux workflows &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=fr){target="_blank"}

+++

+++ Comment mettre à jour les données de Campaign avec un workflow ?

Utilisez l&#39;activité **[!UICONTROL Mise à jour de données]** pour les opérations de base de données en bloc : Insérer (ajout de nouveaux enregistrements), Mettre à jour (modification d&#39;enregistrements existants), Insérer ou mettre à jour (upsert), Supprimer (suppression des enregistrements correspondants).

**Utilisations courantes :** mettre à jour les attributs de profil, synchroniser avec des systèmes externes, tenir à jour les appartenances à des listes, nettoyer/dédupliquer les données, appliquer des modifications d’état en bloc.

Configurez les clés de réconciliation pour une correspondance précise et choisissez les options de mise à jour.

**Rubriques connexes :**

[Activité Mise à jour de données](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html?lang=fr){target="_blank"} | [Activités de Data Management](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/about-action-activities.html){target="_blank"}

+++

+++ Comment utiliser les fonctionnalités de Data Management ?

Les activités de Data Management permettent des opérations sophistiquées : Enrichissement (ajout de données provenant de tables associées), Partage (populations de segments), Déduplication (suppression des doublons), Mise à jour de données (opérations en masse), Changement de dimension (changement de dimension de ciblage), Intersection/Union/Exclusion (combinaison/filtrage des populations).

**Utilisations courantes :** enrichir avec des données d’achat/comportement, segmenter les audiences, supprimer les doublons, intégrer des bases de données externes (FDA), créer des requêtes complexes à plusieurs tables.

**Rubriques connexes :**

[Activités de Data Management](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/about-targeting-activities.html){target="_blank"} | [Activité Enrichissement](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html?lang=fr){target="_blank"}

+++

+++ Est-il possible d’automatiser l’envoi de messages personnalisés ?

Oui. Créer des workflows automatisés : Requête (audience cible) → Enrichissement (ajout de données de personnalisation) → Partage (segments facultatifs) → Diffusion (messages personnalisés) → Planificateur (exécution récurrente).

**Personalization:** Utilisation des données de profil, des données comportementales, du contenu conditionnel et des valeurs dynamiques. Scénarios courants : campagnes d’anniversaire, abandon de panier, programmes de fidélité, reconquête, messages déclenchés par un événement.

**Rubriques connexes :**

Guide de [Personalization](../send/personalize.md) | [Cas pratiques des workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=fr){target="_blank"}

+++

+++ Comment partager une audience en sous-ensembles avec un workflow ?

Utilisez l’activité **[!UICONTROL Partage]** pour diviser les populations : conditions de filtrage (âge, emplacement, statut du VIP), répartition en pourcentage (test A/B), enregistrements de limite (N premiers, X premiers %), regroupement des données (un sous-ensemble par valeur).

**Utilisations courantes :** tests A/B, routage des préférences de canal, déploiement progressif, messagerie spécifique au segment, équilibrage de charge. Chaque sous-ensemble est acheminé vers une transition distincte pour un traitement différent.

**Rubriques connexes :**

[Activité Partage](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/split.html?lang=fr){target="_blank"} | [Guide de test A/B](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/a-b-testing.html){target="_blank"}

+++

+++ Comment mettre à jour les données des destinataires à partir d&#39;un fichier externe ?

Oui. Workflow : chargement des données (fichier) → enrichissement (facultatif) → réconciliation (clés de correspondance telles que l’e-mail/l’ID) → mise à jour des données (mise à jour des enregistrements correspondants, insertion de nouvelles si aucune correspondance n’est trouvée).

**Utilisations courantes :** mettre à jour les attributs de profil à partir du CRM, actualiser les statuts d’abonnement, synchroniser les points de fidélité, mettre à jour les préférences d’opt-in/opt-out.

**Bonnes pratiques :** utilisez des identifiants uniques, validez d’abord les données, testez-les avec des exemples, planifiez des mises à jour régulières.

**Rubriques connexes :**

[Guide d’importation des données](../start/import.md) | [Activité de chargement des données](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=fr){target="_blank"} | [Activité Mise à jour de données](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html?lang=fr){target="_blank"}

+++

+++ Comment identifier et cibler de nouveaux destinataires ?

Champ Requête **[!UICONTROL Date de création]** pour sélectionner les destinataires ajoutés dans un délai spécifique.

**Workflow de bienvenue automatisé :** Planificateur (exécution quotidienne) → Requête (sélection de nouveaux destinataires) → Déduplication (facultatif) → Diffusion (message de bienvenue) → Mise à jour des données (marquer comme « bienvenue »).

**Avancé :** utilisez des fonctions d’agrégat pour identifier dynamiquement les ajouts récents.

**Rubriques connexes :**

[Activité Requête](https://experienceleague.adobe.com/fr/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=fr){target="_blank"} | [Utilisation d&#39;agrégats](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html?lang=fr){target="_blank"}

+++

+++ Comment utiliser les activités de workflow ?

Quatre catégories d&#39;activités :

**Ciblage : requête**, partage, déduplication, enrichissement, intersection, union, exclusion (définir/affiner l’audience)\
**Contrôle de flux :** Planificateur, Attente, Test, Branchement, Rendez-vous, Rendez-vous, Saut (gérer la logique/le timing)\
**Action : diffusion**, mise à jour de données, chargement/extraction de données, code JavaScript (exécution d’opérations)\
**Événement :** Signal externe, collecteur de fichiers, transfert HTTP (réagir aux déclencheurs)

Faire glisser depuis la palette, double-cliquer pour configurer, se connecter avec les transitions.

**Rubriques connexes :**

[Activités de ciblage](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html?lang=fr){target="_blank"} | [Contrôle de flux](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html?lang=fr){target="_blank"} | [Activités d&#39;action](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html?lang=fr){target="_blank"}

+++

+++ Quelles sont les bonnes pratiques en matière de workflow ?

**Conception :** effacer les noms, ajouter des libellés/descriptions, regrouper les activités associées, diviser les processus complexes en workflows plus petits\
**Performances :** limiter les tailles de requête, utiliser des tables temporaires, planifier les heures creuses et éviter les boucles excessives.\
**Gestion des erreurs :** ajouter des chemins d’erreur, configurer des alertes, tester avec des exemples, consulter les journaux\
**Maintenance :** permet d’archiver les workflows obsolètes, de contrôler les versions, de limiter la complexité (&lt;20 activités) et d’utiliser des modèles.\
**Sécurité :** appliquer des autorisations, nettoyer les données temporaires, utiliser des variables et non des valeurs codées en dur

**Rubriques connexes :**

[&#x200B; Guide des bonnes pratiques relatives aux workflows &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=fr){target="_blank"} | [Surveillance des workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=fr){target="_blank"}

+++

## Paramètres de la campagne {#settings}

Configurez votre instance Campaign avec les paramètres, intégrations et configurations appropriés pour optimiser vos opérations marketing.

+++ Puis-je changer la langue de l&#39;interface de Campaign ? 

Cela dépend de l’interface que vous utilisez. La langue **console cliente** est fixe, mais l’**interface utilisateur web de Campaign** permet aux utilisateurs individuels de modifier leurs préférences linguistiques.

**Console cliente (application de bureau) :**

* La langue est définie lors de la création de votre instance et ne peut pas être modifiée
* La console cliente et le serveur doivent utiliser la même langue
* Chaque instance Campaign fonctionne dans une seule langue
* Pour les installations en anglais, vous pouvez choisir entre l’anglais des États-Unis et l’anglais du Royaume-Uni (les formats de date et d’heure diffèrent)

**Interface utilisateur web de Campaign :**

* Les utilisateurs peuvent modifier leur langue d&#39;interface indépendamment via leurs préférences de profil
* Plusieurs langues sont prises en charge avec un formatage spécifique aux paramètres régionaux pour les dates, heures et nombres
* Votre préférence linguistique pour l’UI web est indépendante de la langue du serveur Campaign et de celle de la console cliente


**Rubriques connexes :**

[Modification de la langue dans l’interface utilisateur web de Campaign](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/start/connect-to-campaign#language-pref){target="_blank"} | [Prise en main de la console cliente Campaign](connect.md)

+++

+++ Qu’est-ce que le Panneau de Contrôle Campaign et comment y accéder ?

Le Panneau de Contrôle Campaign est une interface administrative web qui permet aux administrateurs de Campaign d’accroître l’efficacité en gérant les paramètres et en surveillant l’utilisation des instances Campaign. Il permet de gérer les configurations d’instances critiques en libre-service sans contacter l’assistance Adobe.

**Fonctionnalités principales :**

* **Gestion des sous-domaines** - Déléguer et gérer des sous-domaines, surveiller les certificats SSL
* **Surveillance du stockage** - Suivre l’utilisation des bases de données et prévenir les problèmes de stockage
* **Gestion SFTP** - Surveillez le stockage SFTP, gérez les places sur la liste autorisée IP et les clés SSH
* **Paramètres des instances** - Configurer les places sur la liste autorisée IP, gérer les autorisations d’URL, consulter les détails de l’instance
* **Surveillance des profils actifs** - Suivez l’utilisation des profils actifs par rapport aux droits
* **Surveillance des performances** - Surveillez les performances des bases de données et des workflows.
* **Délivrabilité des e-mails** - Configurez DMARC, BIMI et d’autres enregistrements d’authentification

**Conditions d’accès requises :**

* **Utilisateurs administrateurs uniquement** - Le Panneau de Contrôle est limité aux utilisateurs disposant de droits d’administrateur
* **Authentification Adobe IMS** - Accès via Adobe Experience Cloud avec votre Adobe ID
* **Campaign v8 Managed Cloud Services** - Disponible uniquement pour les instances hébergées

**Ressources supplémentaires :**

[Documentation du Panneau de Contrôle &#x200B;](https://experienceleague.adobe.com/fr/docs/control-panel/using/control-panel-home){target="_blank"} | [Tutoriels vidéo Panneau de Contrôle &#x200B;](https://experienceleague.adobe.com/fr/docs/control-panel-learn/tutorials/control-panel-overview){target="_blank"}

+++

+++ Quelle est la procédure pour la délégation de domaine ?

Un sous-domaine est une division de votre domaine qui peut être utilisée pour isoler vos marques ou divers types de trafic (messages transactionnels, informations marketing, etc.).

>[!NOTE]
>
>En tant qu’utilisateur ou utilisatrice de Managed Cloud Services, contactez Adobe pour déléguer vos sous-domaines à Adobe.

+++

+++ Comment configurer les fonctionnalités de tracking sur mon instance Campaign ? 

Campaign v8 fournit un suivi complet pour surveiller les interactions des destinataires avec vos messages. Le suivi nécessite une configuration appropriée des paramètres de votre instance et de vos messages.

**Ce que vous pouvez suivre :**

* **Ouvertures d’e-mails** - Via le pixel de tracking (1x1 image transparente)
* **Clics sur les liens** - Toutes les URL sont automatiquement converties en liens suivis
* **Désabonnements** - Suivi des liens d’opt-out
* **Pages miroir vues** - Lorsque les destinataires consultent la version web
* **Paramètres personnalisés** - Ajout de données de tracking aux URL pour une analyse avancée

**Étapes clés de configuration :**

1. Configurer l’URL du serveur de suivi dans les paramètres de votre instance (gérés par Adobe pour v8)
2. Activer le tracking dans les propriétés de la diffusion
3. Configurer automatiquement le suivi de liens individuels ou de tous les liens
4. Définir la période de validité du tracking et la conservation des logs

**Bonne pratique :** testez toujours le suivi avec des BAT avant l’envoi à votre audience principale pour vous assurer que les liens fonctionnent correctement et que les données sont capturées.

**Rubriques connexes :**

[Suivre et surveiller les diffusions](../send/tracking.md) | [Configuration des liens suivis](../send/tracked-links.md) | [Suivi des tests](../send/testing-tracking.md)

+++

+++ Comment configurer la délivrabilité des emails ? 

La délivrabilité des e-mails dépend de la configuration technique, de la qualité du contenu et de la réputation de l&#39;expéditeur. Campaign v8 fournit des outils et des paramètres pour optimiser l’emplacement de la boîte de réception.

**Étapes de configuration essentielles :**

* **Authentification de domaine** - Configurez les enregistrements SPF, DKIM et DMARC pour vérifier votre domaine d’envoi
* **Réchauffement des adresses IP** - Augmentez progressivement le volume d’envoi sur les nouvelles adresses IP pour établir la réputation.
* **Configuration de l&#39;expéditeur** - Utilisez des adresses et des noms d&#39;expéditeur cohérents et reconnaissables
* **Gestion des erreurs** - Configurez des règles de quarantaine pour gérer automatiquement les erreurs hard et soft
* **Boucles de retours** - Configurez le traitement des plaintes pour gérer les rapports de spam

**Bonnes pratiques relatives au contenu :**

* Test d&#39;emails avec SpamAssassin pour vérifier le score de spam
* Conserver un rapport texte/image correct
* Inclure la version en texte brut avec HTML
* Toujours fournir un lien de désabonnement
* Évitez les mots de déclenchement de spam et les majuscules excessives

**Surveillance :** utilisez les rapports de délivrabilité de Campaign pour suivre les taux de rebond, les taux de plaintes et l’emplacement des boîtes de réception. Pour Campaign v8, Adobe fournit une optimisation de la délivrabilité au niveau de l’infrastructure.

**Rubriques connexes :**

[À propos de la délivrabilité dans Campaign](../send/about-deliverability.md) | [&#x200B; Guide des bonnes pratiques en matière de délivrabilité &#x200B;](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=fr){target="_blank"}

+++

+++ À quelles bases de données externes est-il possible de connecter Campaign ? 

Campaign v8 prend en charge les connexions FDA (Federated Data Access) aux principaux systèmes de base de données d’entreprise (bases de données cloud, bases de données d’entreprise, entrepôts de données, plateformes de big data).

Les versions de base de données prises en charge et les exigences de connexion varient. Vérifiez la [matrice de compatibilité](compatibility-matrix.md) de votre version de Campaign v8 pour confirmer la prise en charge de bases de données spécifiques et assurez-vous que les licences des connecteurs FDA sont correctes.

Voir [Configuration des connexions FDA](../connect/fda.md)

+++

+++ Adobe Campaign peut-il s’intégrer aux systèmes CRM ?

Oui. Campaign fournit des connecteurs CRM natifs pour une synchronisation bidirectionnelle avec les principaux systèmes CRM. Synchronise les données de contact, les leads, les comptes, les logs de diffusion, les données de tracking et les mesures d’engagement. Prend en charge les modes de synchronisation planifiés, manuels et en temps réel (via l’API).

Utilisez l’assistant Connecteur CRM de Campaign pour mapper les champs, sélectionner des tables et planifier la synchronisation. Vérifiez la [matrice de compatibilité](compatibility-matrix.md) pour connaître les versions CRM prises en charge.

**Rubriques connexes :**

[Configuration du connecteur CRM](../connect/crm.md) | [Activités Workflow CRM](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/crm-connector.html?lang=fr){target="_blank"}

+++

+++ Comment vider le cache de la console cliente ?

L’effacement du cache de la console cliente résout de nombreux problèmes courants d’affichage et de fonctionnalité. Le cache stocke les fichiers de configuration locaux qui peuvent parfois être corrompus ou obsolètes.

**Quand vider le cache :**

* Les nouveaux éléments de branding (logos, couleurs) ne s’affichent pas correctement
* Échec inattendu des fonctions d’export/d’import
* Les éléments d’interface ne sont pas mis à jour après des modifications de configuration.
* Problèmes de performances ou réponse lente de la console
* Après la mise à niveau vers une nouvelle version de la console cliente

**Procédure d’effacement du cache :**

1. Ouvrir la console cliente Campaign
2. Accéder au menu **[!UICONTROL Fichier]**
3. Sélectionner **[!UICONTROL Vider le cache local…]**
4. Confirmer l’action lorsque vous recevez l’invitation.
5. Redémarrer la console cliente

Pour en savoir plus, consultez [Installation et configuration de la console cliente](connect.md)

+++

+++ Puis-je configurer les paramètres de l’interface utilisateur ?

Oui. Les administrateurs et administratrices de Campaign peuvent personnaliser l’interface utilisateur pour refléter le branding organisationnel et optimiser l’expérience utilisateur. Configurez les paramètres au niveau de l’instance ou de l’utilisateur ou utilisatrice.

**Éléments personnalisables :**

* **Image de marque** - Logo, couleurs et éléments d’identité visuelle
* **Vues par défaut** - Disposition de la page d’accueil, visibilité de la structure des dossiers
* **Configurations de liste** - Colonnes par défaut, ordre de tri, filtres dans les listes de données
* **Navigation** - Éléments de menu et raccourcis disponibles
* **Paramètres régionaux** - Formats date/heure, formats numériques, fuseaux horaires
* **Notifications** - Alertes par e-mail, notifications in-app, alertes de workflow

**Niveaux de configuration :**

* **À l’échelle de l’instance** - Appliquer à tous les utilisateurs (nécessite des droits d’administrateur)
* **Spécifique à l’utilisateur** - Préférences individuelles et paramètres personnels

**Rubriques connexes :**

[Configurer les paramètres de l’interface utilisateur](../config/ui-settings.md) | [Autorisations utilisateur](gs-permissions.md)

+++

+++ Puis-je créer des champs et des tableaux personnalisés ?

Oui. Le modèle de données flexible de Campaign vous permet d&#39;étendre les schémas intégrés avec des champs personnalisés et de créer des tables entièrement nouvelles pour répondre aux besoins spécifiques de votre entreprise.

**Éléments personnalisables :**

* **Ajouter des champs aux tables existantes** - Étendez la table des destinataires avec des points de fidélité, des préférences personnalisées et des identifiants externes
* **Créer des tables personnalisées** - Stocker les produits, les transactions, les niveaux de fidélité, les entités personnalisées
* **Définir des relations** - Lier des tables personnalisées à des tables Campaign existantes
* **Étendre les formulaires** - Mettez à jour l’interface utilisateur pour afficher et modifier les champs personnalisés

**Cas d’utilisation courants :**

* Stocker les attributs de profil supplémentaires (valeur de durée de vie du client, magasin préféré, statut VIP)
* Gestion des catalogues de produits avec des attributs personnalisés
* Suivi des événements et interactions personnalisés
* Intégrer des identifiants de système externes pour la synchronisation des données
* Créer des modèles de données spécifiques au secteur (vente au détail, finance, voyages)

**Rubriques connexes :**

[Étendre le modèle de données](../dev/extend-schema.md) | [Structure d&#39;un schéma](../dev/schemas.md) | [Bonnes pratiques relatives au modèle de données](../dev/datamodel-best-practices.md)

+++

## Rapports {#reporting}

Obtenez des informations sur les fonctionnalités de reporting de Campaign, y compris les rapports intégrés, les rapports personnalisés et les outils d’analyse de données tels que les cubes.

+++ Comment créer de nouveaux rapports ?

Campaign propose plusieurs options de reporting en fonction de vos besoins et de votre expertise technique : rapports intégrés, analyse descriptive, rapports personnalisés dans la console cliente et cubes.

**Options de création de rapports :**

* **Rapports intégrés** - Rapports de diffusion, de campagne et de tracking prêts à l’emploi accessibles à partir de l’onglet **[!UICONTROL Rapports]**
* **Analyse descriptive** - Rapports statistiques rapides sur toutes les données avec une interface pilotée par un assistant
* **Rapports personnalisés** - Rapports avancés créés par les utilisateurs et utilisatrices techniques à l’aide de l’éditeur de rapports
* **Cubes** - Exploration des données multidimensionnelles et analyse des tableaux croisés dynamiques

**Important :** Campaign est conçu pour le reporting des opérations marketing, et non comme un outil spécialisé de Business Intelligence. Pour les besoins analytiques complexes, envisagez l’intégration à Adobe Analytics ou à des plateformes de BI dédiées.

**Rubriques connexes :**

[Prise en main du reporting](../reporting/gs-reporting.md) | [Rapports de l’interface utilisateur web de Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}

+++

+++ Comment concevoir et partager des rapports statistiques sur les populations ?

Utilisez l’outil d’analyse descriptive de Campaign pour générer rapidement des rapports statistiques sur n’importe quelle donnée de population. Cette fonctionnalité pilotée par un assistant vous permet d’analyser les distributions, les tendances et les modèles sans expertise technique.

**Ce que vous pouvez analyser :**

* Répartition des données démographiques et de segmentation des destinataires
* Mesures des performances de la campagne et taux de réponse
* Répartition des attributs de profil (âge, emplacement, préférences)
* Statistiques de diffusion et modèles d’engagement
* Valeurs de champ personnalisées et mesures de qualité des données

**Création :** sélectionnez une liste ou un résultat de requête → cliquez avec le bouton droit de la souris → **[!UICONTROL Actions > Analyser]** → sélectionnez le type d’analyse (qualitative ou quantitative) → configurez les options d’affichage → Générez le rapport.

**Partage :** exportez les rapports vers Excel/PDF ou enregistrez-les dans le dossier **[!UICONTROL Rapports]** pour permettre à l’équipe d’y accéder avec les autorisations appropriées.

En savoir plus sur l’[analyse descriptive](../reporting/built-in-reports.md)

+++

+++ Comment concevoir des rapports avancés sur mes données ?

Utilisez la console cliente pour créer des rapports personnalisés avancés dotés de fonctionnalités d’analyse complexes.

Dans la console cliente, vous pouvez :

* Créer des rapports complexes à l’aide de requêtes SQL et de calculs personnalisés
* Créer des rapports de plusieurs pages avec des graphiques, des tableaux et des tableaux croisés dynamiques
* Conception de formatage conditionnel et de contenu dynamique
* Accéder au modèle de données Campaign complet et aux bases de données externes (FDA)

Découvrez comment [&#x200B; Créer des rapports personnalisés (console cliente)](../reporting/custom-reports.md)

+++

+++ Qu’est-ce qu’un cube et comment l’utiliser pour la création de rapports ?

Les cubes sont des structures de données multidimensionnelles qui permettent aux utilisateurs professionnels d&#39;explorer et d&#39;analyser les données de Campaign par le biais de tableaux croisés dynamiques sans compétences techniques. Considérez-les comme des modèles de données préconfigurés qui simplifient les rapports complexes. Cet outil de reporting est disponible dans la console cliente et dans l’interface utilisateur web de Campaign.

* Les utilisateurs et utilisatrices techniques créent et configurent des cubes définissant les dimensions (temps, zone géographique, canaux) et les mesures (ouvertures, clics, chiffre d’affaires)
* Les utilisateurs professionnels sélectionnent un cube lors de la création de rapports et font glisser et déposer des dimensions pour explorer les données
* Les données sont automatiquement agrégées et calculées en fonction de la configuration du cube
* Les résultats peuvent être affichés sous forme de tableaux croisés dynamiques, de graphiques ou exportés vers Excel

Découvrez comment [Explorer des données avec des cubes](../reporting/gs-cubes.md)

+++

+++ Est-il possible de créer un rapport à partir des réponses à un questionnaire en ligne ?

Oui ! Campaign comprend un module Questionnaire qui permet de créer des questionnaires en ligne et de générer des rapports intégrés sur les réponses aux questionnaires.

**Important :** la gestion des questionnaires n’est pas disponible dans les déploiements Campaign v8 Enterprise (FFDA). [En savoir plus](../architecture/enterprise-deployment.md).

**Fonctionnalités de l’enquête :**

* Créer des questionnaires en ligne avec plusieurs pages et types de questions
* Collecter les réponses dans la base de données ou les variables locales
* Afficher le suivi en temps réel des réponses à un questionnaire
* Générer des rapports dédiés sur les réponses aux questionnaires (répartition par question, statistiques générales)
* Exporter les réponses au questionnaire vers Excel, PDF ou CSV pour une analyse plus approfondie
* Utilisation des données de questionnaire dans les workflows de ciblage pour personnaliser les campagnes

**Analyse avancée :**

* Accéder aux réponses à un questionnaire à partir de l&#39;onglet **[!UICONTROL Réponses]** et exporter les données
* Utilisez l’activité **[!UICONTROL Réponses à un questionnaire]** dans les workflows pour cibler les destinataires en fonction de leurs réponses
* Combiner les données d’enquête avec d’autres données Campaign pour la segmentation et la personnalisation
* Créer des rapports et des cubes personnalisés pour l&#39;analyse multidimensionnelle des questionnaires

**Rubriques connexes :**

[Prise en main des questionnaires](https://experienceleague.adobe.com/fr/docs/campaign-classic/using/online-surveys/about-surveys){target="_blank"} | [Rapports d’enquête](https://experienceleague.adobe.com/fr/docs/campaign-classic/using/online-surveys/publish-track-and-use-collected-data#reports-on-surveys){target="_blank"}

+++

+++ Comment partager l’accès à mes rapports ?

Contrôlez la visibilité des rapports grâce aux autorisations de dossiers et aux droits nommés dans Campaign.

**Méthodes de contrôle d’accès :**

* **Autorisations des dossiers** - Placez les rapports dans des dossiers disposant des droits d’accès appropriés pour les groupes d’utilisateurs
* **Droits nommés** - Attribuez des droits pour afficher, créer ou modifier des rapports
* **Contexte d’affichage** - Définissez l’emplacement d’affichage des rapports (dossier Rapports, onglets de campagne, écrans de diffusion)

**Configuration :** enregistrer le rapport dans un dossier spécifique → configurer l’accès aux dossiers pour les groupes d’opérateurs → définir les propriétés du rapport et le contexte d’affichage.

**Rubriques connexes :**

[&#x200B; Rapports personnalisés &#x200B;](../reporting/custom-reports.md) | [Autorisations utilisateur](gs-permissions.md)

+++

+++ Puis-je exporter des rapports dans différents formats ?

Oui, Campaign prend en charge plusieurs formats d’exportation pour les rapports de la console cliente et de l’interface utilisateur web, ce qui facilite le partage avec les parties prenantes et l’intégration à d’autres outils.

**Formats d’exportation disponibles :**

* **Excel (.xlsx)** - Idéal pour la manipulation des données, une analyse plus approfondie et les tableaux croisés dynamiques
* **PDF** - Idéal pour les présentations, les résumés exécutifs et les rapports imprimés
* **CSV** - Parfait pour les importations de données dans d’autres systèmes et outils de BI
* **OpenDocument (.ods)** - Format de feuille de calcul Open Source
* **XML** - Pour les intégrations système et le traitement automatisé

**Comment exporter :**

* **Console cliente :** ouvrir le rapport → cliquez sur le bouton **[!UICONTROL Exporter]** → Choisissez le format → Enregistrer le fichier
* **Interface utilisateur web :** ouvrir le tableau de bord → cliquer sur l’icône d’exportation → sélectionner le format → télécharger
* **Exportations automatisées :** planification d’exportations régulières à l’aide de workflows avec des activités d’exportation

**Bonnes pratiques :**

* Utilisez Excel pour les rapports nécessitant une analyse des parties prenantes et des annotations
* Utilisez PDF pour les rapports statiques envoyés aux cadres ou archivés à des fins de conformité
* Utiliser CSV pour les intégrations avec des entrepôts de données ou des outils d’analyse externes
* Test des rapports exportés pour garantir la mise en forme et la précision des données

**Rubriques connexes :**

[&#x200B; Rapports personnalisés &#x200B;](../reporting/custom-reports.md) | [Rapports de l’interface utilisateur web de Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}

+++

## Développeurs {#developers}

Accédez aux informations techniques destinées aux développeurs, notamment les détails du modèle de données, les schémas, les API et les fonctionnalités de personnalisation.

+++ Quel est le modèle de données de Campaign ? 

Le modèle de données de Campaign est une structure de base de données relationnelle pilotée par un schéma et composée de tables intégrées (destinataires, diffusions, campagnes) qui peuvent être étendues en fonction des besoins de votre entreprise.

**Concepts clés : schémas** (définitions XML), tables intégrées, liens (relations), énumérations (listes de valeurs), extensions (champs personnalisés/tables).

**Schémas principaux :** destinataire (`nms:recipient`), diffusion (`nms:delivery`), workflow (`xtk:workflow`), campagne (`nms:operation`), logs de tracking.

Il est essentiel de comprendre le modèle de données pour les workflows, les requêtes, les extensions de schéma et les intégrations.

**Rubriques connexes :**

[Modèle de données de Campaign](../dev/datamodel.md) | [Bonnes pratiques relatives au modèle de données](../dev/datamodel-best-practices.md)

+++

+++ Comment utiliser des schémas de Campaign ?

Les schémas définissent la structure des données de Campaign au format XML, en spécifiant la structure des tables, les propriétés des champs, les relations, les index et le contrôle d’accès.

**Utilisation des schémas :**

* **Affichage :** accès via **[!UICONTROL Administration > Configuration > Schémas de données]**
* **Étendre :** permet de créer des schémas d’extension (par exemple, `cus:recipient`) pour ajouter des champs personnalisés sans modifier les schémas principaux.
* **Créer :** crée de nouvelles tables pour les données spécifiques à l’entreprise
* **Mettre à jour :** appliquer des modifications via **[!UICONTROL Outils > Avancé > Mettre à jour la structure de la base de données]**

**Utilisations courantes :** ajoutez des champs personnalisés au tableau des destinataires, créez des tableaux personnalisés, définissez des relations, implémentez des modèles commerciaux spécifiques.

**Important :** ne modifiez jamais directement les schémas prédéfinis. Utilisez toujours des schémas d’extension pour la compatibilité de mise à niveau.

**Rubriques connexes :**

[Prise en main des schémas](../dev/schemas.md) | [Étendre un schéma](../dev/extend-schema.md)

+++

+++ Comment utiliser une table de destinataires personnalisée ?

Utilisez une table des destinataires personnalisée lors du ciblage des comptes B2B, des données d’abonné distinctes, des systèmes externes ou des architectures multi-marques au lieu de la table des destinataires standard.

**Implémentation :** créez un schéma personnalisé avec des champs obligatoires (e-mail, clé primaire, exclusions) → Configurez les mappings de ciblage → Mettez à jour les modèles de diffusion → Adaptez les workflows/requêtes.

**Considérations principales :** doit inclure les champs de diffusion obligatoires, les workflows/formulaires doivent être adaptés et les tests doivent être critiques avant la migration de production.

**Bonne pratique :** d’abord étendre la table des destinataires standard. N’utilisez des tableaux personnalisés que lorsque cela est vraiment nécessaire en raison de la complexité accrue.

**Rubriques connexes :**

[Table des destinataires personnalisée](../dev/custom-recipient.md) | [Mappings de ciblage](../audiences/target-mappings.md)

+++

+++ Quelles sont les bonnes pratiques pour définir des requêtes dans Campaign ? 

Le requêteur de Campaign crée visuellement des requêtes de base de données sans SQL. Il est utilisé dans les activités de workflow, le ciblage de diffusion, les listes, les rapports et les filtres.

**Bonnes pratiques :**

* Démarrer simple : créez progressivement, testez chaque étape
* Utiliser des dimensions de filtrage - tirer parti des relations entre les tables
* Optimisation des performances : indexez les champs interrogés et évitez les calculs complexes.
* Réutilisation des filtres prédéfinis par souci de cohérence
* Tester d’abord avec de petits échantillons
* Documenter les requêtes complexes

**Modèles courants :** cibler les personnes créant les diffusions, trouver les contacts inactifs, segmenter par comportement, exclure les destinataires précédents.

**Accès :** **[!UICONTROL Outils > Éditeur de requêtes générique]** pour l’exploration ad hoc.

**Rubriques connexes :**

[Requêteur](../start/query-editor.md) | [Activité Requête](https://experienceleague.adobe.com/fr/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=fr){target="_blank"}

+++

+++ Comment importer un package de données ? 

Importez des packages via **[!UICONTROL Outils > Avancé > Importer un package]** dans la console cliente. Les packages contiennent les configurations Campaign (schémas, workflows, typologies) et les données nécessaires au déploiement entre les instances.

**Types de package :** package utilisateur (configurations personnalisées), package plateforme (fourni par Adobe), package de données (données réelles).

**Bonnes pratiques :** Test en développement en premier, sauvegarde avant l’importation, exportation à partir de la même version ou d’une version antérieure.

En savoir plus dans [&#x200B; Utilisation des packages de données &#x200B;](../dev/packages.md)

+++

+++ Où puis-je trouver la liste des API de Campaign v8 ?

Campaign v8 fournit des API SOAP (opérations de console cliente), des API REST (intégrations modernes) et des API JavaScript (script de workflow).

**Utilisations courantes :** Intégrer à CRM/ERP, automatiser les campagnes, synchroniser les données, créer des solutions de surveillance, créer des interfaces externes.

**Accès :** [Documentation de l’API Campaign v8](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=fr){target="_blank"}

+++


+++ Comment surveiller les workflows à partir de l’API ?

Les API Campaign vous permettent de contrôler par programmation les workflows : démarrage, pause/reprise, arrêt, état des requêtes, récupération de journaux, surveillance de la progression des activités.

**Point d’entrée de l’API :** `POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

**Commandes :** `{"method":"start"}`, `{"method":"pause"}`, `{"method":"resume"}`, `{"method":"stop"}`

**Cas pratiques :** création de tableaux de bord de surveillance, implémentation d’alertes automatisées, orchestration à partir de planificateurs externes, création de dépendances entre les instances, génération de rapports personnalisés.

**Bonne pratique :** combinez la surveillance des API avec le journal d&#39;audit pour une gouvernance complète.

Voir [Workflows de contrôle via l’API](../dev/api/controlling-a-workflow.md)

+++

+++ Comment mettre à jour la structure de la base de données ?

Après avoir modifié les schémas (ajout de champs, création de tables, modification des types de données), mettez à jour la structure physique de la base de données via **[!UICONTROL Outils > Avancé > Mettre à jour la structure de la base de données]** pour appliquer les modifications.

**Si nécessaire :** ajout de champs, création/extension de tables, modification des propriétés de champ, ajout/suppression de liens, création d’index.

**Important :** la sauvegarde d’abord, les tests en développement, la planification des temps d’arrêt pour les modifications importantes, la coordination avec l’assistance d’Adobe (Managed Cloud Services), notez que certaines modifications peuvent entraîner une perte de données.


**Rubriques connexes :**

[Mettre à jour la structure de la base de données](../dev/update-database-structure.md) | [Étendre le schéma](../dev/extend-schema.md)

+++

## Confidentialité {#privacy}

Découvrez comment Adobe Campaign vous aide à vous conformer aux réglementations de confidentialité comme le RGPD et le CCPA, et à gérer les demandes des titulaires de données.

+++ Quels sont les concepts clés de la confidentialité dans Campaign ?

Campaign vous aide à vous conformer aux règlements sur la confidentialité (RGPD, CCPA, PDPA, LGPD) par le biais d’outils de gestion des droits des titulaires de données, du consentement et de la conservation des données. Les concepts clés incluent les réglementations de confidentialité, l’identification des données personnelles, les droits des titulaires de données (accès, suppression, portabilité), la gestion du consentement et les politiques de conservation des données.

En tant que contrôleur de données, vous êtes chargé de traiter les demandes des titulaires de données, de tenir à jour les enregistrements de consentement et d’assurer une utilisation transparente des données.

En savoir plus sur la [gestion de la confidentialité](../start/privacy.md)

+++

+++ Comment puis-je garantir la conformité en matière de confidentialité dans Campaign ?

Campaign fournit des outils pour le respect de la confidentialité, mais vous êtes responsable devant la loi. Collaborez avec le service juridique de votre programme de confidentialité.

**Actions essentielles :**

* Établissez des processus pour le traitement des demandes des titulaires de données (accès, suppression)
* Implémenter la gestion du consentement avec les horodatages et le suivi de la portée
* Inclure des liens de désabonnement dans tous les e-mails marketing
* Contrôler les sources de données et supprimer les données inutilisées
* Appliquer les contrôles d’accès avec les privilèges les plus faibles

Campaign propose l’intégration de Privacy Core Service, le suivi du consentement, des workflows de suppression automatisés et des pistes d’audit pour la conformité.

En savoir plus sur la [gestion de la confidentialité](../start/privacy.md)

+++

+++ Comment collecter et gérer le consentement des utilisateurs dans Campaign ?

Un consentement valide nécessite un accord actif, spécifique, éclairé et révocable. Les utilisateurs doivent prendre des mesures explicites : ne pas cocher de case et ne pas donner leur consentement. Séparer les consentements à différentes fins (dissociation), fournir des explications claires et conserver les enregistrements avec horodatage.

**Bonnes pratiques :** proposez des options de souscription granulaires, actualisez régulièrement le consentement, facilitez l’accès aux centres de préférences et définissez le consentement comme un élément de confiance.

**Implémentation technique dans Campaign :**

Campaign fournit des services d’abonnement, des centres de préférences, des indicateurs d’opt-out et des champs de consentement personnalisés pour le suivi du consentement.

* Étendre le schéma des destinataires pour les champs de consentement (date, type, source)
* Créer des services d’abonnement pour chaque type de consentement
* Créer des formulaires web de centre de préférences
* Utilisation de workflows pour appliquer le consentement dans le ciblage
* Tenir à jour les journaux d&#39;audit

Consultez le service juridique pour vous assurer que votre implémentation répond aux exigences réglementaires.

**Rubriques connexes :**

[Services d’abonnement](../start/subscriptions.md) | [Confidentialité et consentement](../start/privacy.md#consent-retention-roles) | [&#x200B; Gestion de la confidentialité &#x200B;](../start/privacy.md)

+++

+++ Quelles données sont supprimées lorsque je traite une demande de suppression ?

Campaign supprime automatiquement toutes les données liées à un titulaire de données : profil du destinataire, logs de diffusion et de tracking, données personnalisées avec relations de propriété et historique d&#39;abonnement.

**Fonctionnement :** Campaign supprime toutes les données pour lesquelles le lien vers le destinataire a `integrity="own"` dans la définition de schéma, assurant ainsi une suppression en cascade sur les tables associées.

Vous pouvez personnaliser la portée de la suppression en modifiant l’intégrité des liens dans les schémas, mais consultez d’abord un service juridique. La suppression est permanente et ne peut pas être annulée.

**Rubriques connexes :**

[&#x200B; Gestion de la confidentialité &#x200B;](../start/privacy.md) | [&#x200B; Liens de schéma &#x200B;](../dev/schemas.md)

+++

+++ Les suppressions d’informations personnelles affectent-elles mes rapports de diffusion ?

Non. Les rapports de campagne sont basés sur des mesures agrégées précalculées (total envoyé, ouvertures, clics), et non sur des requêtes actives sur des journaux individuels. La suppression des données de destinataires individuels ne modifie pas les statistiques agrégées historiques.

Les statistiques globales de diffusion et les mesures de performances restent intactes, tandis que les logs de tracking individuels et les détails personnels sont supprimés. Cela vous permet de gérer les analyses marketing tout en respectant les droits des titulaires de données.

**Rubriques connexes :**

[&#x200B; Gestion de la confidentialité &#x200B;](../start/privacy.md) | [Rapports](../reporting/gs-reporting.md)

+++

+++ Comment empêcher la réimportation des données supprimées ?

Vous devez supprimer des données de tous les systèmes sources, et pas seulement de Campaign. Les données proviennent souvent de systèmes externes (CRM, e-commerce, entrepôts de données).

**Actions requises :** identifier toutes les sources de données, les supprimer des systèmes sources, les ajouter aux listes d’exclusion/suppression, mettre à jour les workflows d’importation pour respecter les indicateurs de suppression et documenter le processus.

En tant que contrôleur de données, vous êtes responsable de la suppression complète des données dans l’ensemble de votre écosystème technologique.

**Rubriques connexes :**

[&#x200B; Gestion de la confidentialité &#x200B;](../start/privacy.md) | [Workflows d’import](../config/workflows.md)

+++

+++ Les utilisateurs supprimés peuvent-ils à nouveau s’inscrire ?

Oui. Les titulaires de données peuvent à nouveau donner leur accord après la suppression. Campaign crée un enregistrement de destinataire entièrement nouveau sans lien vers les données supprimées précédentes : le profil commence à zéro.

Le journal d&#39;audit de Campaign enregistre à la fois l&#39;événement de suppression et la création d&#39;un nouveau profil, démontrant la conformité et montrant que le nouveau processus d’opt-in a été librement consenti après la suppression.

**Rubriques connexes :**

[&#x200B; Gestion de la confidentialité &#x200B;](../start/privacy.md) | [Abonnements](../start/subscriptions.md)

+++

## Vous avez encore besoin d&#39;aide ? {#get-help}

Vous ne trouvez pas ce que vous recherchez ? Voici des ressources supplémentaires pour vous aider à réussir avec Adobe Campaign v8.

### Soutien de la communauté

Communiquez avec d’autres utilisateurs de Campaign et des experts d’Adobe pour partager vos connaissances et obtenir des réponses.

* **[Communauté Adobe Campaign &#x200B;](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community?profile.language=fr){target="_blank"}** - Posez des questions, partagez des solutions et communiquez avec la communauté Campaign
* **[Forums Experience League &#x200B;](https://experienceleaguecommunities.adobe.com/?profile.language=fr){target="_blank"}** - Parcourez les discussions sur tous les produits Adobe
* **[Heures de bureau de la communauté Campaign](https://experienceleague.adobe.com/fr){target="_blank"}** - Participez à des sessions en direct avec des experts d’Adobe

### Documentation et apprentissage

Accédez à des guides, tutoriels et supports de formation complets.

* **[Tutoriels Campaign](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/overview.html?lang=fr){target="_blank"}** - Guides vidéo détaillés et tutoriels pratiques
* **[Nouveautés](whats-new.md)** - Dernières fonctionnalités
* **[Notes de mise à jour](release-notes.md)** - Informations sur les versions actuelle et précédente
* **[Versions et mises à niveau](upgrades.md)** - Découvrez les versions et mises à niveau de Campaign et comment vérifier votre version

### Ressources techniques

Recherchez une documentation technique détaillée et des ressources pour les développeurs.

* **[API Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=fr){target="_blank"}** - Documentation complète de référence sur les API
* **[Matrice de compatibilité](compatibility-matrix.md)** - Systèmes et versions pris en charge
* **[FAQ sur les versions et mises à niveau](upgrades.md)** - Vérifiez votre version et découvrez les mises à niveau

### Assistance et services

Obtenez de l’aide de l’équipe d’assistance Adobe et gérez votre instance.

* **[Adobe Admin Console](https://adminconsole.adobe.com/){target="_blank"}** - Consigner les cas d&#39;assistance et gérer les utilisateurs
* **[Assistance clientèle Adobe &#x200B;](https://helpx.adobe.com/fr/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}** - Contactez l’équipe d’assistance
* **[Panneau de Contrôle &#x200B;](https://experienceleague.adobe.com/fr/docs/control-panel/using/control-panel-home.html?lang=fr){target="_blank"}** - Gérer les paramètres de votre instance Campaign
* **[Statut du système](https://status.adobe.com/){target="_blank"}** - Vérifiez le statut des services Adobe

### Formation et certification

Améliorez vos compétences grâce aux programmes de formation et de certification officiels d’Adobe.

* **[Aide d’Experience League &#x200B;](https://experienceleague.adobe.com/fr/browse/campaign/campaign-v8){target="_blank"}** - Ressources d’aide pour Campaign v8 (interface utilisateur web et console cliente)
* **[Adobe Digital Learning Services &#x200B;](https://learning.adobe.com/){target="_blank"}** - Cours officiels dispensés par un instructeur et à son propre rythme
* **[Certification Adobe Campaign &#x200B;](https://experienceleague.adobe.com/docs/certification/program/overview.html?lang=fr){target="_blank"}** - Validez votre expertise avec la certification professionnelle
* **[Parcours d’apprentissage Experience League &#x200B;](https://experienceleague.adobe.com/fr?lang=fr#dashboard/learning){target="_blank"}** - parcours d’apprentissage guidés

### Autres ressources utiles

* **[Documentation de Campaign Classic v7 &#x200B;](https://experienceleague.adobe.com/docs/campaign-classic/using/campaign-classic-home.html?lang=fr){target="_blank"}** - Référence pour les utilisateurs de Classic v7
* **[Documentation sur l’interface utilisateur web de Campaign](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/campaign-web-home){target="_blank"}** - Nouveau guide de l’interface web
* **[Bonnes pratiques en matière de délivrabilité](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=fr){target="_blank"}** - Optimisation de la diffusion e-mail

