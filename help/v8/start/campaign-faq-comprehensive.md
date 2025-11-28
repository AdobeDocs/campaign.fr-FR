---
title: Questions fréquentes sur Campaign v8
description: Obtenez des réponses aux questions courantes d’Adobe Campaign v8 sur l’installation, la configuration, la messagerie, les workflows, etc
feature: Overview
role: User
level: Beginner
keywords: FAQ, Campaign v8, questions, réponses, aide, support, dépannage
hide: true
hidefromtoc: true
source-git-commit: 4f9b580ed4aeec0666fcb3343861b955a6787f01
workflow-type: tm+mt
source-wordcount: '12528'
ht-degree: 10%

---

# Questions fréquentes {#faq}

Obtenez des réponses rapides aux questions les plus courantes sur Adobe Campaign v8. Que vous débutiez ou que vous recherchiez une aide de configuration avancée, vous trouverez des réponses organisées par sujet ci-dessous.

**Vous découvrez Campaign ?** par [questions générales](#general) et [concepts clés](#key-concepts).\
**Besoin d’aide technique ?** vérifier [développeurs](#developers) et [paramètres de Campaign](#settings).\
**Vous ne trouvez pas la réponse ?** Visitez notre [Forums communautaires](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community?profile.language=fr){target="_blank"} ou [contactez l’assistance](#get-help).

**Conseil :** utilisez Ctrl+F (Cmd+F sur Mac) pour rechercher des mots-clés spécifiques sur cette page. Cliquez sur une question pour développer la réponse.


## Questions générales {#general}

Obtenez des réponses aux questions les plus fréquentes sur Adobe Campaign v8, y compris sur la connexion, la mise à niveau et l’assistance.

+++ Comment se connecter à Campaign v8 ?

Vous devez télécharger et installer la console cliente Campaign pour vous connecter à Adobe Campaign.

[Pour en savoir plus, cliquez ici](connect.md).

À compter de la version 8.6 de Campaign, vous avez accès à l’**interface utilisateur web de Campaign**, disponible via l’environnement Adobe Experience Cloud central. Experience Cloud est une famille intégrée d’applications, de produits et de services de marketing numérique d’Adobe.

Découvrez comment vous connecter à Adobe Experience Cloud et accéder à l’interface web d’Adobe Campaign [sur cette page](campaign-ui.md#ac-web-ui). Pour en savoir plus, consultez la [documentation sur l’interface d’utilisation d’Adobe Campaign Web](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/campaign-web-home){target="_blank"}.


**Rubriques connexes :**

* [Installer la console cliente](connect.md)
* [Interface utilisateur de Campaign](campaign-ui.md)
* [Autorisations utilisateur](gs-permissions.md)

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

+++ Comment effectuer une mise à niveau de Campaign vers la dernière version ?

Adobe Campaign fait l’objet de mises à jour régulières. Des versions mineures sont publiées chaque année avec de nouvelles fonctionnalités, des améliorations et des correctifs. En outre, nous publions périodiquement des builds avec des correctifs cumulatifs uniquement.

Cette fréquence régulière de mise à jour a pour but de vous fournir les dernières fonctionnalités et améliorations. Vous bénéficiez ainsi d&#39;un environnement sécurisé et d&#39;une expérience optimale avec notre produit. C’est la raison pour laquelle nous pensons qu’il est important que vous exécutiez la version la plus récente d’Adobe Campaign.

**Remarque :** en tant qu’utilisateur Managed Cloud Services, votre instance est mise à niveau par Adobe avec de nouvelles versions.

En savoir plus sur les [versions et mises à niveau de Campaign](upgrades.md).

+++

+++ Comment améliorer la délivrabilité des e-mails ?

La délivrabilité des e-mails, composant essentiel de la réussite du programme marketing de chaque expéditeur, est caractérisée par des critères et des règles en constante évolution. Pour naviguer efficacement dans ce monde numérique, il est nécessaire d&#39;affiner régulièrement votre stratégie d&#39;e-mail, en tenant compte des principales tendances de délivrabilité, afin d&#39;atteindre au mieux vos audiences.

Consultez ce guide pour découvrir [bonnes pratiques en matière de délivrabilité](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=fr){target="_blank"}

Découvrir comment implémenter la délivrabilité dans Campaign [dans ce guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html?lang=fr){target="_blank"}

**Rubriques connexes :**

[À propos de la délivrabilité](../send/about-deliverability.md) | [Contrôler le contenu du message](../send/control-message-content.md) | [Surveiller la délivrabilité](../send/monitoring-deliverability.md) | [&#x200B; SpamAssassin &#x200B;](../send/spamassassin.md)

+++

+++ Comment puis-je m’assurer que ma diffusion est envoyée sans erreur ?

Pour garantir la réussite de la diffusion, procédez comme suit :

**Avant l’envoi :**

* Exécutez l&#39;analyse de la diffusion pour détecter les erreurs (personnalisation manquante, destinataires non valides, problèmes de contenu)
* Envoyer des BAT pour vérifier le rendu et la personnalisation
* Consulter les avertissements pendant la préparation
* Vérifier le nombre de populations cibles

**Pendant et après l’envoi :**

* Surveillez le tableau de bord de la diffusion pour obtenir des statistiques en temps réel (envoyés, diffusés, bounces, erreurs).
* Vérifier les logs de diffusion pour connaître l’état au niveau du message
* Suivi des taux de succès, de rebond et d’erreur
* Vérifier les adresses en quarantaine

**Bonnes pratiques :**

* Configurer des alertes pour les seuils d’erreur
* Utiliser des vagues (envoi par lots) pour les gros volumes
* Tester d’abord avec de petits volumes
* Nettoyez régulièrement la base de données des destinataires
* Surveiller la réputation de l&#39;expéditeur

En savoir plus sur les [surveillance des diffusions](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=fr){target="_blank"} et [bonnes pratiques de diffusion](delivery-best-practices.md).

+++

+++ Est-il possible de surveiller l’exécution des workflows ?

Oui. Campaign fournit plusieurs outils pour surveiller l’exécution des workflows :

* **Tableau de bord des workflows** - Affichez le statut, la progression et les erreurs en temps réel pour chaque activité de workflow
* **[Journaux de workflow](https://experienceleague.adobe.com/fr/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution#displaying-logs){target="_blank"}** - Accédez aux journaux d’exécution détaillés pour résoudre les problèmes
* **[Carte thermique &#x200B;](https://experienceleague.adobe.com/fr/docs/campaign/automation/workflows/monitoring-workflows/heatmap){target="_blank"}** - Visualisez l’activité des workflows et identifiez les goulots d’étranglement au niveau des performances
* **[Journal d&#39;audit](../reporting/audit-trail.md)** - Suivez toutes les modifications apportées aux workflows
* **[Alertes](https://experienceleague.adobe.com/fr/docs/campaign/automation/workflows/use-cases/monitoring/send-alerts-to-operators){target="_blank"}** - Configurez des notifications pour les échecs ou les retards de workflow

Pour surveiller un workflow, ouvrez-le et cliquez sur l’onglet **Journaux**. Les activités ayant échoué sont mises en surbrillance en rouge et vous pouvez afficher les détails des erreurs en cliquant dessus.

En savoir plus sur [surveillance de l’exécution des workflows](https://experienceleague.adobe.com/fr/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"} et [bonnes pratiques relatives aux workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=fr){target="_blank"}.

+++

+++ Avec quels systèmes et composants Campaign v8 est-il compatible ?

Vous trouverez la liste de tous les systèmes et composants pris en charge dans le dernier build de Campaign dans la [matrice de compatibilité Adobe Campaign](compatibility-matrix.md).

+++

+++ Comment télécharger Campaign ?

Vous pouvez obtenir le programme d&#39;installation et la console cliente à partir du Centre de téléchargement d&#39;Adobe.

En tant qu’utilisateur administrateur, accédez à Adobe [Distribution logicielle](https://experience.adobe.com/#/downloads/content/software-distribution/fr/campaign.html){target="_blank"} pour télécharger Adobe Campaign.

En savoir plus sur le Centre de distribution [sur cette page](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html?lang=fr){target="_blank"}.

+++

+++ Comment signaler un problème ?

La création d&#39;un ticket vous permet de contacter l&#39;équipe du Service clientèle d&#39;Adobe pour tout problème lié à vos produits Adobe. La console Adobe Admin Console vous permettra de discuter avec le Service clientèle d&#39;Adobe pour résoudre vos problèmes.

Pour enregistrer un problème ou démarrer une session de conversation dans ce nouveau système, connectez-vous à la console [Adobe Admin Console](https://adminconsole.adobe.com/overview){target="_blank"}.

Ce système nécessite des comptes individuels pour chaque utilisateur, avec les autorisations adéquates. Si vous constatez que vous ne pouvez pas vous connecter à l’aide de votre Adobe ID, demandez l’accès par le biais d’Experience League. L’équipe d’assistance clientèle vous assistera dès que possible. [En savoir plus](https://helpx.adobe.com/fr/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}

Rejoignez la communauté Campaign et recherchez des réponses parmi les questions existantes ou consultez les experts. [Prenez part à la conversation](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community?profile.language=fr){target="_blank"}

+++


## Concepts clés {#key-concepts}

Découvrez les concepts fondamentaux de Campaign, notamment l’authentification, l’interface utilisateur, les workflows et les fonctionnalités de base pour démarrer efficacement.

+++ Puis-je me connecter à Campaign v8 avec un Adobe ID ?

Oui ! Grâce à l&#39;intégration avec l&#39;IMS (système Adobe Identity Management), les utilisateurs se connectent à la console Adobe Campaign à l&#39;aide de leur Adobe ID. Cette intégration présente les avantages suivants :

* utilisation d&#39;un même identifiant pour toutes les solutions Experience Cloud
* mémorisation de la connexion lors de l&#39;utilisation d&#39;Adobe Campaign avec les différentes intégrations
* politique de gestion de mot de passe plus sécurisée
* utilisation de comptes de type Federated ID (fournisseur d&#39;identité externe)

[En savoir plus](connect.md) sur l’accès à Campaign v8 avec un Adobe ID.

+++

+++ Quelle est ma version de Campaign ?

Vérifiez les [numéros de version et de build](upgrades.md#version) depuis le menu **Aide > A propos...** de la console cliente de Campaign.

+++

+++ Quelles sont les différences entre Campaign Classic v7 et Campaign v8 ?

Campaign v8 est la version de nouvelle génération de Campaign, conçue pour Managed Cloud Services. Elle apporte des améliorations significatives en termes d’infrastructure, de sécurité, de délivrabilité et de surveillance.

Adobe Campaign v8 est exclusivement disponible en tant que **Managed Cloud Service** et ne peut pas être déployé dans un environnement on-premise ou hybride.

[En savoir plus sur la transition de Campaign Classic v7 vers v8](v7-to-v8.md).

+++

+++ Comment configurer les autorisations utilisateur ?

En tant qu&#39;administrateur de Campaign, vous pouvez configurer des autorisations pour les utilisateurs de votre organisation.

Il s&#39;agit d&#39;un ensemble de droits et de restrictions qui autorisent ou refusent :

* Accès à certaines fonctionnalités
* l’accès à certaines données
* Créer, modifier et/ou supprimer des données

[En savoir plus](../start/gs-permissions.md) sur les autorisations utilisateur dans Campaign v8.

**Rubriques connexes :**

* [Prise en main des autorisations](gs-permissions.md)
* [Gérer les autorisations utilisateur](manage-permissions.md)
* [Ajouter des autorisations aux dossiers](folder-permissions.md)

+++

+++ Comment assurer la conformité de la confidentialité avec Campaign ?

Adobe Campaign propose un ensemble d’outils pour vous aider à respecter la confidentialité dans le cadre du RGPD, du CCPA et d’autres règlements sur la confidentialité.

[En savoir plus](../start/privacy.md) sur la gestion de la confidentialité et les outils et fonctionnalités fournis par Adobe Campaign pour vous aider à respecter vos obligations de conformité en matière de confidentialité.

+++

+++ Quelles notions concernant l&#39;interface utilisateur de Campaign faut-il connaître ? 

Reportez-vous à [cette section](campaign-ui.md) pour en savoir plus sur les bases de l’interface utilisateur d’Adobe Campaign.

À compter de la version 8.6 de Campaign, vous avez également accès à la nouvelle **interface utilisateur web de Campaign**, disponible via l’environnement Adobe Experience Cloud central.

[En savoir plus dans la documentation de l’interface utilisateur web d’Adobe Campaign](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/campaign-web-home){target="_blank"}.

+++

+++ Comment sélectionner l’audience de mes messages ? 

Avec Adobe Campaign, vous pouvez utiliser différentes stratégies pour créer des audiences et sélectionner des personnes destinataires cibles.

[En savoir plus](../audiences/gs-audiences.md) sur la définition des audiences dans Campaign v8.

+++

+++ Qu’est-ce qu&#39;un workflow ? 

Adobe Campaign contient des workflows pour orchestrer l&#39;ensemble des processus et tâches dans les différents modules du serveur applicatif. Cet environnement graphique complet permet de concevoir des processus englobant segmentation, exécution de campagnes, traitement de fichiers, participation humaine, etc. Le moteur de workflow exécute et assure le tracking de ces processus.

Un workflow permet par exemple de télécharger un fichier depuis un serveur, de le décompresser et d&#39;importer ses enregistrements dans la base de données Adobe Campaign.

Un workflow peut également faire intervenir des opérateurs afin de notifier ou valider une opération ou faire un choix. Ainsi, il est possible de créer une action de diffusion, d&#39;assigner une tâche à un ou plusieurs opérateurs qui seront chargés de saisir son contenu ou spécifier sa cible, puis de faire valider le BAT avant de démarrer la diffusion.

[En savoir plus](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/about-workflows.html?lang=fr){target="_blank"} sur les workflows. Vous pouvez également consulter les [bonnes pratiques en matière de workflow](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=fr){target="_blank"}.

**Rubriques connexes :**

* [Commencer avec les workflows](../config/workflows.md)
* [Créer votre premier workflow](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=fr){target="_blank"}
* [Cas pratiques des workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}
* [Surveillance de l’exécution des workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=fr){target="_blank"}

+++

+++ Comment créer et envoyer un premier email ? 

La création de votre premier e-mail dans Campaign v8 implique plusieurs étapes clés :

1. **Créer la diffusion** - Commencez par créer une diffusion e-mail à partir d’un modèle ou de zéro
1. **Définir l’audience** - Sélectionnez vos destinataires cibles à l’aide de requêtes, de listes ou de workflows
1. **Concevoir le contenu** - Utilisez le concepteur d’e-mail pour créer votre message avec de la personnalisation
1. **Test avec des BAT** - Envoyez des e-mails de test pour valider le contenu et la personnalisation
1. **Analyser et envoyer** - Exécutez l’analyse de diffusion pour vérifier les erreurs, puis envoyez votre e-mail

Campaign v8 propose deux interfaces pour la création d’e-mails :

* **Console cliente** : application de bureau complète dotée de fonctionnalités avancées
* **Interface utilisateur web de Campaign** - Interface web moderne et intuitive pour une création d’e-mails plus rapide

[En savoir plus sur la conception et la validation des emails](../send/email.md) dans Campaign v8.

**Rubriques connexes :**

* [Créer votre première diffusion](create-message.md) - Guide détaillé
* [Utilisation de modèles de diffusion](../send/create-templates.md) - Gagnez du temps grâce aux modèles
* [Bonnes pratiques de diffusion &#x200B;](delivery-best-practices.md) - Recommandations pour réussir
* [Définir le contenu de l’e-mail](../send/defining-the-email-content.md) - Options de création de contenu
* [Prévisualisation et BAT](../send/preview-and-proof.md) - Test avant envoi
* [Configurer et envoyer](../send/configure-and-send.md) - Dernières étapes d’envoi
* [Personnaliser le contenu](../send/personalize.md) - Ajouter une personnalisation dynamique

+++

+++ Comment envoyer des SMS ? 

L’envoi de SMS avec Campaign v8 nécessite une configuration initiale, puis suit un processus de diffusion simple :

**Configuration initiale (configuration unique) :**

1. **Configurer le canal SMS** - Configurer les paramètres de diffusion SMS et le compte externe
1. **Configurer la connexion SMPP** - Se connecter à votre fournisseur de services SMS via le protocole SMPP
1. **Tester la connexion** - Valider la connectivité avec votre fournisseur SMS
1. **Configurer le routage** - Définissez la manière dont les SMS sont routés via votre fournisseur

**Création et envoi de SMS:**

1. **Créer une diffusion SMS** - Démarrez une nouvelle diffusion SMS à partir d’un modèle
1. **Définir des destinataires** - Sélectionnez votre audience mobile à l’aide des champs de numéro de téléphone
1. **Écrire du contenu SMS** - Créez votre message (160 caractères standard ou plus avec concaténation)
1. **Ajouter une personnalisation** - Inclure des champs dynamiques spécifiques à chaque destinataire
1. **Envoyer des BAT** - Tester la diffusion par SMS pour valider le contenu et la diffusion
1. **Analyser et envoyer** - Exécutez l’analyse et envoyez-la à votre audience.

**Principales fonctionnalités SMS :**

* **Connecteurs SMPP multiples** - Prise en charge de différents fournisseurs et protocoles SMS
* **Rapports de diffusion** - Effectuez le suivi des messages envoyés, diffusés et en échec
* **Encodage des caractères** - Prise en charge de GSM7, Unicode et des caractères spéciaux
* **Prise en charge longue des SMS** - Concaténation automatique des messages pour les textes plus longs
* **SMS bidirectionnels** - Gérer les réponses SMS entrantes avec des workflows

[En savoir plus sur la configuration et l&#39;envoi de SMS](../send/sms/sms.md) dans Campaign v8.

**Rubriques connexes :**

* [Prise en main des SMS](../send/sms/sms.md) - Guide complet sur les SMS
* [Paramètres de diffusion SMS](../send/sms/sms-delivery-settings.md) - Options de configuration
* [Paramètres du compte externe SMPP](../send/sms/smpp-external-account.md) - Configuration du fournisseur
* [Créer une diffusion SMS](../send/sms/create-sms.md) - Création étape par étape
* [Contenu SMS](../send/sms/sms-content.md) - Consignes de conception de contenu
* [Envoyer des BAT de SMS](../send/sms/sms-proofs.md) - Test des SMS
* [Surveiller les SMS](../send/sms/sms-monitor.md) - Suivre et analyser les diffusions

+++

+++ Comment envoyer des notifications push ? 

L’envoi de notifications push avec Campaign v8 implique la configuration de l’intégration de votre application mobile et la création de notifications attrayantes :

**Configuration initiale (configuration unique) :**

1. **Configurer le canal push** - Configurer les paramètres du canal de notification push dans Campaign
1. **Intégrer Campaign SDK** - Ajoutez Adobe Campaign SDK à votre application mobile (ou utilisez la collecte de données).
1. **Configuration d’une application mobile** - Enregistrez vos applications iOS et Android dans Campaign.
1. **Configuration des certificats** - Configuration du certificat APNs (iOS) et de la clé FCM (Android)
1. **Enregistrement de test** - Vérifiez que les appareils peuvent enregistrer et recevoir des jetons

**Création et envoi de notifications push :**

1. **Créer une diffusion push** - Démarrer une nouvelle notification push à partir d&#39;un modèle
1. **Sélectionner la plateforme** - Sélectionnez iOS, Android ou les deux plateformes
1. **Définir l&#39;audience** - Cibler les abonnés à l&#39;aide des données d&#39;abonnement aux applications mobiles
1. **Notification de conception** - Créez un titre, un message et du contenu multimédia enrichi
1. **Configurer le comportement** - Définir les actions de clic, les liens profonds et les données personnalisées
1. **Envoyer des notifications de test** - Valider sur des appareils réels avant l’envoi
1. **Analyser et envoyer** - Vérifier le ciblage et envoyer à votre audience mobile

**Fonctionnalités de notification push :**

* **Notifications push riches** - Incluez des images, des vidéos et des boutons interactifs (iOS et Android)
* **Personalization** - Contenu dynamique basé sur le profil et le comportement de l&#39;utilisateur
* **Lien profond** - Diriger les utilisateurs vers des écrans d’application ou du contenu spécifiques
* **Planification** - Envoi à des heures optimales en fonction du fuseau horaire de l’utilisateur
* **Tests A/B** - Tester différents messages et optimiser l’engagement
* **Suivi** - surveiller les ouvertures, les clics et les conversions

**Fonctionnalités spécifiques à Platform :**

* **iOS** - Notifications silencieuses, catégories de notification, personnalisation audio
* **Android** - Modèles push riches, canaux de notification, mises en page personnalisées

[En savoir plus sur la configuration des notifications push](../send/push-settings.md) dans Campaign v8.

**Rubriques connexes :**

* [Créer et envoyer des notifications push](../send/push.md) - Compléter le guide push
* [Configuration du canal de notification push](../send/push-settings.md) - Configuration du canal
* [Concevoir une notification push riche Android](../send/rich-push-android.md) - Notifications riches Android
* [Concevoir une notification push riche iOS](../send/rich-push-ios.md) - Notifications riches iOS
* [Configuration d’avec la collecte de données](../send/push-data-collection.md) - Méthode d’intégration révisée moderne
* [Suivi et surveillance](tracking.md) - Analyse des performances des notifications push

+++

+++ Comment créer une landing page ? 

Vous pouvez utiliser le Digital Content Editor d’Adobe Campaign pour concevoir des landing pages et définir le mapping avec les champs de la base de données.

[En savoir plus](../dev/landing-pages.md) dans la documentation de Campaign v8.

Vous pouvez également utiliser l&#39;interface utilisateur web de Campaign pour créer et publier des pages de destination - [En savoir plus](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}.

+++

+++ Comment effectuer un tracking des diffusions ? 

Vous pouvez suivre les diffusions envoyées avec Campaign v8 par le biais de [rapports de diffusion](../reporting/delivery-reports.md) dédiés, puis surveiller vos diffusions.

En savoir plus sur la gestion du tracking dans Campaign [sur cette page](../start/tracking.md).

**Rubriques connexes :**

* [Tracking et surveillance des messages](tracking.md)
* [Rapports de diffusion](../reporting/delivery-reports.md)
* [Comprendre les diffusions en échec](../send/delivery-failures.md)
* [Configuration des liens trackés](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html){target="_blank"} (documentation de Campaign Classic v7)

+++

+++ Comment traduire un message d’erreur ? 

Un message d&#39;erreur est affiché dans une langue étrangère ? Tous les messages d&#39;erreur et leur traduction sont répertoriés sur [cette page](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=fr){target="_blank"}.

+++

+++ Est-il possible de créer un formulaire web et collecter les réponses dans Campaign ? 

Oui. Créez des formulaires web à l’aide de **Applications web de Campaign et Forms** (console cliente) pour un contrôle total de la logique et de la validation des formulaires, ou utilisez **Pages de destination de Campaign** (interface utilisateur web) avec une interface moderne par glisser-déposer pour les abonnements et la génération de pistes. Tous deux collectent des données directement dans Campaign et les intègrent à des workflows pour des actions automatisées.

[En savoir plus sur les applications et les formulaires web](../dev/webapps.md) | [Pages de destination de l’interface utilisateur web de Campaign](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/landing-pages/get-started-lp){target="_blank"}

+++



## Campaign v8 et versions précédentes {#v7-differences}

Découvrez les principales différences entre Campaign v8 et les versions précédentes (Classic v7 et Standard), notamment l’architecture, le déploiement, les chemins de migration et les modifications de fonctionnalités. Que vous veniez de Campaign Classic v7 ou de Campaign Standard, découvrez les nouveautés et comment effectuer une transition en douceur.

+++ Quelles sont les principales différences entre Campaign v8 et les versions précédentes ?

Campaign v8 est une refonte complète d’Adobe Campaign, conçue pour une architecture moderne native cloud, qui apporte des améliorations significatives par rapport à Campaign Classic v7 et à Campaign Standard :

**Modèle de déploiement :**

* **v8:** Managed Cloud Services uniquement : entièrement hébergé et géré par Adobe
* **v7/Standard :** options On-premise, hybrides ou hébergées disponibles
* **Avantage :** zéro gestion de l’infrastructure, mise à l’échelle automatique, sécurité de niveau entreprise, surveillance proactive

**Architecture et performances :**

* Architecture Full FDA (FFDA) améliorée **v8:** avec la base de données PostgreSQL
* **v8:** Débit de traitement par lots atteignant jusqu’à 20 millions d’opérations par heure **&#x200B;**
* **v8:** Débit des messages transactionnels de **1 million par heure**
* **v8:** Exploration des données en temps réel et création rapide d’audiences (minutes contre heures)
* **Bénéfice :** de meilleures performances pour les opérations à grande échelle et les campagnes complexes

**Interface utilisateur :**

* **v8:** Nouvelle **interface utilisateur web de Campaign** avec la console cliente : intuitive, accessible, idéale pour les marketeurs
* **v8:** Conception moderne et réactive avec fonctions de glisser-déposer
* **v8:** Workflows simplifiés de création et de gestion de campagnes
* **v8:** partage de nombreuses similitudes avec l’interface de Campaign Standard.
* **Avantage :** intégration plus rapide, exécution plus facile des campagnes, meilleure accessibilité, courbe d’apprentissage minimale

**Nouvelles fonctionnalités clés :**

* **Notifications push riches** avec images, vidéos, boutons interactifs, carrousels et minuteries
* **Assistant IA** pour la génération de contenu (e-mail, SMS, notification push) avec score d’alignement de la marque
* **Mise à niveau de l’infrastructure SMS (SMS v2.0)** avec une fiabilité et une compatibilité améliorées
* **Intégration d’Adobe Experience Manager as a Cloud Service** pour une gestion de contenu transparente
* **Rapports améliorés** y compris les rapports dynamiques pour les utilisateurs de Campaign Standard

**Mises à niveau et maintenance :**

* **v8:** Mises à niveau automatiques gérées par Adobe : toujours sur la dernière version stable avec modèle de diffusion continu
* **v7/Standard :** planification et exécution manuelles de la mise à niveau requises
* **Avantage :** charge de maintenance réduite, accès immédiat aux nouvelles fonctionnalités, pas de temps d’arrêt

**API et intégration :**

* API REST **v8:** modernes avec des performances et une fiabilité améliorées
* Intégration transparente d’**v8:** avec Adobe Experience Cloud et Adobe Experience Platform
* **Avantage :** intégrations plus faciles, meilleure interopérabilité, pratiques de développement modernes

[En savoir plus sur les fonctionnalités clés de Campaign v8](whats-new.md)

**Rubriques connexes :**

* [De Campaign Classic v7 vers v8](v7-to-v8.md) | Guide de transition [v7 vers v8](https://experienceleague.adobe.com/fr/docs/campaign/campaign-v8/new/v7-to-v8){target="_blank"}
* [De Campaign Standard à v8](acs-to-v8.md) | [Transition Campaign Standard](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/start/acs-migration){target="_blank"}
* [Guide d’adoption de Campaign v8](https://experienceleague.adobe.com/fr/docs/campaign-web/acs-to-ac/home){target="_blank"}
* [Matrice des fonctionnalités de Campaign v8](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
* [Architecture de Campaign v8](../architecture/architecture.md)
* [Mécanismes de sécurisation et limitations](ac-guardrails.md)

+++

+++ Dois-je migrer de Campaign Classic v7 ou Campaign Standard vers v8 ?

**Campaign v8 est idéal pour les organisations qui ont besoin de :**

* **Campagnes à volume élevé** - Envoyez des millions de messages avec des performances et une fiabilité améliorées (20 millions d’opérations/heure)
* **Évolutivité d’entreprise** - Développez votre base de données et vos campagnes sans souci de performances
* **Interface utilisateur web moderne** - Interface utilisateur web intuitive et réactive de Campaign pour accélérer la création de campagnes et améliorer l’expérience utilisateur
* **Avantages natifs du cloud** - Tirez parti des mises à jour automatiques, de l’infrastructure gérée, de la mise à l’échelle élastique et de la surveillance proactive
* **Prise en charge à long terme** - Campaign v8 est une plateforme stratégique d’Adobe avec une prise en charge étendue. Les versions précédentes atteindront la fin de la prise en charge dans les années à venir
* **Réduction des frais généraux informatiques** - Élimination de la gestion de l’infrastructure et planification des mises à niveau
* **Fonctionnalités avancées** - Assistant IA, notification push enrichie, SMS amélioré, intégration de Adobe Experience Platform

**Pour les utilisateurs de Campaign Standard :**

Les utilisateurs de Campaign Standard peuvent désormais passer à Campaign v8 Managed Cloud Services. Les principaux avantages sont les suivants :

* **Interface familière** - L’interface utilisateur web de Campaign partage de nombreuses similitudes avec Campaign Standard, ce qui réduit la courbe d’apprentissage
* **Parité des fonctionnalités** - Des fonctionnalités Campaign Standard essentielles ont été ajoutées à v8 (rapports dynamiques, valorisation de marque centralisée, API REST, pages de destination, fragments visuels)
* **Prise en charge améliorée** - Assistance de premier ordre pour une transition en douceur et une surveillance continue des plateformes
* **Migration des données** - Toutes vos données Campaign Standard sont importées avec un minimum d’interruption
* **Expérience utilisateur cohérente** - Continuez à travailler avec des workflows et une interface familiers

**Pour les utilisateurs de Campaign Classic v7 :**

Campaign v8 apporte des améliorations substantielles tout en conservant les fonctionnalités de base de Campaign :

* **Double interface** - Accédez à la fois à la puissante console cliente et à l’interface utilisateur web moderne de Campaign
* **Meilleures performances** - Amélioration significative des performances des requêtes et du traitement des données
* **Avantages du cloud** - Mises à niveau automatiques, correctifs de sécurité, sauvegarde/récupération gérée par Adobe
* **Architecture moderne** - Architecture FFDA améliorée avec PostgreSQL pour une meilleure évolutivité

**Quand envisager une migration :**

* Votre instance Campaign actuelle gère d’importants volumes de données (des millions de profils)
* Vous rencontrez des problèmes de performances avec les workflows ou le ciblage complexes
* Vous voulez réduire les coûts de gestion et d&#39;entretien de l&#39;infrastructure
* Vous avez besoin d’une intégration transparente à Adobe Experience Cloud ou Adobe Experience Platform
* De toute façon, vous prévoyez une mise à niveau ou une actualisation majeure de l’infrastructure
* **Vous souhaitez une technologie à l’épreuve du temps** - Les versions précédentes arriveront en fin de prise en charge
* **Votre équipe a besoin d’une interface moderne** - L’interface utilisateur web de Campaign offre une meilleure accessibilité pour les professionnels du marketing

**Considérations relatives à la migration :**

* Adobe fournit une assistance, des conseils et des outils pour la migration
* v8 est Managed Cloud Service uniquement (aucun déploiement on-premise ou hybride)
* Certaines implémentations techniques peuvent être différentes. Consultez la [&#x200B; matrice des fonctionnalités](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
* La migration et le test des données nécessitent une planification et des ressources
* **Pour les utilisateurs de Campaign Standard** - La transition est conçue pour être fluide avec une perturbation minimale des workflows

**Étapes suivantes :**

Contactez votre représentant Adobe pour :

* Évaluation de la préparation et du calendrier de votre migration
* Comprendre les avantages spécifiques à votre cas d’utilisation
* Planifier la stratégie de migration et l’allocation des ressources
* Accéder aux outils et au support de migration

**Rubriques connexes :**

**Pour les utilisateurs de Campaign Classic v7 :**

* [De Campaign Classic v7 à v8](v7-to-v8.md)
* Guide détaillé [v7 à v8](https://experienceleague.adobe.com/fr/docs/campaign/campaign-v8/new/v7-to-v8){target="_blank"}

**Pour les utilisateurs de Campaign Standard :**

* Transition de [Campaign Standard vers v8](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/start/acs-migration){target="_blank"}
* [Guide d’adoption de Campaign v8](https://experienceleague.adobe.com/fr/docs/campaign-web/acs-to-ac/home){target="_blank"}
* [Présentation de Campaign Standard vers v8](https://experienceleague.adobe.com/fr/docs/campaign-web/acs-to-ac/overview){target="_blank"}
* [Prise en main pour les professionnels du marketing](https://experienceleague.adobe.com/fr/docs/campaign-web/acs-to-ac/marketers){target="_blank"}
* [Prise en main pour les administrateurs/développeurs](https://experienceleague.adobe.com/fr/docs/campaign-web/acs-to-ac/admin-developers){target="_blank"}

**Ressources générales :**

* [Matrice des fonctionnalités de Campaign v8](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/start/capability-matrix){target="_blank"}
* [Matrice de compatibilité](compatibility-matrix.md)

+++

+++ Quelles sont les principales différences terminologiques et fonctionnelles dans Campaign v8 ?

Campaign v8 offre la plupart des fonctionnalités de Campaign Classic v7 et de Campaign Standard avec des améliorations, mais certaines fonctionnalités ont été modifiées en raison de l’architecture native au cloud et la terminologie diffère entre les versions.

**Différences de terminologie (Campaign Standard vers v8) :**

* Les **ressources personnalisées** sont désormais **Schémas**
* Les **messages** sont appelés **diffusions**
* Les **utilisateurs de produits** sont désormais **opérateurs**.
* Les **rôles** sont configurés avec **droits nommés**
* Les **groupes de sécurité** sont désormais **groupes d’opérateurs**
* **Les entités organisationnelles** sont gérées via **Autorisations des dossiers**

**Mises à jour de la terminologie de l’interface utilisateur web de Campaign :**

Les termes suivants ont été mis à jour dans l’interface utilisateur web de Campaign (la console cliente utilise des termes traditionnels) :

* **Destinataires** sont désormais **Profils**
* Les **adresses de contrôle** sont désormais **Profils de test**
* L’**analyse de la diffusion** s’appelle désormais **Préparation de la diffusion** (cliquez sur le bouton **Préparer**).
* **Aperçu de l’e-mail** est disponible via le bouton **Simuler le contenu**
* Les **listes** sont désormais **audiences**

**Non disponible dans v8:**

* **Déploiements On-premise et hybrides** - v8 est Managed Cloud Services uniquement
* **Accès direct à la base de données** - Utilisez plutôt les API et les outils fournis
* **Infrastructure gérée par le client** - Adobe gère l’ensemble de l’infrastructure
* **Mises à niveau manuelles des builds** - Désormais automatique (géré par Adobe)

**Différentes implémentations dans v8:**

* **Workflows techniques** - Certains optimisés pour l’architecture cloud peuvent fonctionner différemment
* **Structure de la base de données** - L’architecture FFDA améliorée peut nécessiter des adaptations de schéma
* **Intégrations personnalisées** - Peut nécessiter des mises à jour pour l’architecture cloud
* **Personnalisations de bas niveau** - Certaines nécessitent des approches différentes dans l’environnement géré

**amélioré ou remplacé dans v8:**

* **Mises à niveau de build** - Automatique avec modèle de diffusion continu plutôt que manuel
* **Réglage des performances** - Géré par l’optimisation de l’infrastructure Adobe
* **Correctifs de sécurité** - Appliqués automatiquement par Adobe
* **Sauvegarde et récupération** - Géré par Adobe dans le cadre du service
* **Interface utilisateur** - Nouvelle interface utilisateur web de Campaign avec la console cliente

**Fonctionnalités ajoutées pour les utilisateurs de Campaign Standard passant à la version 8:**

* **Rapports dynamiques** - Rapports en temps réel personnalisables avec analyse démographique
* **Branding centralisé** - Définissez des directives visuelles et techniques pour la marque.
* **API REST** - Créez des intégrations et construisez votre écosystème
* **Améliorations des pages de destination** - Parité des fonctionnalités améliorée avec Campaign Standard
* **Fragments visuels** - Composants visuels réutilisables pour les e-mails et les modèles de contenu

**Important :** la plupart des fonctionnalités marketing et opérationnelles sont disponibles et améliorées dans v8. Les fonctionnalités techniques et au niveau de l’infrastructure sont gérées par Adobe dans l’environnement cloud.

**Rubriques connexes :**

* [Matrice des fonctionnalités](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/start/capability-matrix){target="_blank"} - Comparaison des fonctionnalités entre les interfaces
* [Matrice de compatibilité](compatibility-matrix.md) - Systèmes et composants pris en charge
* [Mécanismes de sécurisation et limitations](ac-guardrails.md)
* [guide de transition de v7 vers v8](v7-to-v8.md)
* [Transition de Campaign Standard vers v8](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/start/acs-migration){target="_blank"}

+++

## Profils et audiences {#audiences}

Trouvez des réponses aux questions sur la gestion des profils, la création d’audiences, l’importation de données et le ciblage des destinataires pour vos campagnes.

+++ Comment créer des destinataires ?

Créer manuellement des destinataires dans la console cliente pour des profils individuels, importer depuis des fichiers (CSV/TXT) pour des ajouts en masse, utiliser des formulaires web pour l’auto-enregistrement ou intégrer via des API de systèmes externes. Utilisez des workflows d’importation pour les chargements de données récurrents.

[Création manuelle de profils](../audiences/create-profiles.md) | [Importer des profils depuis un fichier](../audiences/import-profiles.md) | [Collecter des profils avec des formulaires web](../audiences/collect-profiles.md)

+++

+++ Import de profils?

Campaign propose plusieurs méthodes d&#39;import : import de fichiers simple à l&#39;aide de l&#39;assistant d&#39;import, import basé sur les workflows pour les transformations complexes, imports récurrents avec workflows planifiés depuis SFTP et import d&#39;API pour l&#39;intégration par programmation.

Pour les imports de fichiers, préparez votre fichier de données (codage CSV/TXT, UTF-8), utilisez l’assistant ou le workflow d’import, mappez les colonnes aux champs de Campaign, définissez des règles de mise à jour/insertion et testez-les d’abord avec un petit échantillon. Utiliser des workflows pour les imports récurrents et appliquer des règles de déduplication.

[Guide d’importation des données](../start/import.md) | [Workflow d’import récurrent](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html?lang=fr){target="_blank"} | [Activité de chargement des données](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=fr){target="_blank"}

+++

+++ Comment définir la population cible d&#39;une campagne marketing ?

Campaign propose plusieurs méthodes de ciblage : créer des requêtes avec des critères visuels, cibler des listes ou des segments existants, importer des destinataires à partir de fichiers externes (CSV, TXT) ou appliquer des filtres prédéfinis. Vous pouvez combiner des critères avec une logique AND/OR, exclure des populations spécifiques, utiliser des populations témoins et fractionner les critères pour les tests A/B. Prévisualisez toujours la taille de votre population cible avant l’envoi.

[Définir des cibles de campagne](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=fr){target="_blank"} | [Activité Requête](https://experienceleague.adobe.com/fr/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=fr){target="_blank"} | [Créer des audiences](../audiences/create-audiences.md)

+++

+++ Comment créer une liste de profils ?

Une liste est un ensemble statique de destinataires que vous pouvez cibler dans les diffusions et réutiliser dans les campagnes.

**Trois méthodes de création :**

* **Création manuelle :** accédez à **[!UICONTROL Profils et cibles > Listes]** et cliquez sur **[!UICONTROL Créer]**. Ajouter des destinataires à partir d&#39;une requête, par sélection individuelle ou à partir d&#39;un dossier.

* **Automatisation des workflows :** utilisez l’activité **[!UICONTROL Mise à jour de liste]** pour créer et gérer automatiquement des listes à partir des résultats de requête ou des données importées.

* **Lors de l’import :** lors de l’import de profils, créez une liste pour les enregistrer en tant que groupe réutilisable.

**Conseil :** utilisez des workflows pour les listes nécessitant des mises à jour régulières et une création manuelle pour la segmentation ponctuelle.

[Créer des audiences](../audiences/create-audiences.md) | [Activité de mise à jour de liste](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/list-update.html?lang=fr){target="_blank"}

+++

+++ Comment dédupliquer une population avant d&#39;envoyer un message ?

Utilisez l&#39;activité **[!UICONTROL Déduplication]** dans un workflow pour supprimer les destinataires en double avant la diffusion. Placez-le entre vos activités **[!UICONTROL Requête]** et **[!UICONTROL Diffusion]**, puis choisissez vos critères de déduplication (généralement l&#39;adresse e-mail ou l&#39;identifiant du destinataire) et l&#39;enregistrement à conserver.

**Conseil :** toujours dédupliquer avant l’envoi pour s’assurer que chaque personne ne reçoit votre message qu’une seule fois.

[Activité Déduplication](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html?lang=fr){target="_blank"}

+++

+++ Comment identifier et cibler les abonnés à une newsletter ?

Campaign effectue automatiquement le suivi des abonnements aux newsletters par le biais de services d’information. Pour cibler les abonnés :

* Utilisez une activité **[!UICONTROL Requête]** et filtrez sur **[!UICONTROL Abonnements]** > sélectionnez votre service de newsletter
* Ciblez les abonnés directement depuis votre diffusion en choisissant **[!UICONTROL A > Abonnés d&#39;un service d&#39;information]**
* Créer des listes d’abonnés à l’aide de l’activité de workflow **[!UICONTROL Services d’inscription]**

Campaign effectue le suivi de l’historique des abonnements/désabonnements et gère automatiquement les processus d’opt-in/opt-out.

[Gérer les abonnements](../start/subscriptions.md) | [Activité Requête](https://experienceleague.adobe.com/fr/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=fr){target="_blank"}

+++

+++ Quelle est la bonne pratique pour exclure des profils d&#39;une population cible ?

Utilisez l’activité **[!UICONTROL Exclusion]** dans un workflow pour supprimer les profils indésirables de votre cible. Placez-le après vos activités de ciblage et définissez la population à exclure.

[Activité d’exclusion](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/exclusion.html?lang=fr){target="_blank"}

+++

+++ Puis-je utiliser des profils externes sans les importer dans Campaign ?

Oui, Campaign v8 vous permet de travailler avec des profils externes stockés dans une base de données externe sans les charger dans Adobe Campaign. [En savoir plus](../audiences/external-profiles.md).

+++

+++ Comment créer des profils de test pour mes diffusions ?

Les profils de test sont des destinataires spéciaux utilisés pour envoyer des BAT et valider les diffusions sans affecter votre base de données de production. Créez-les dans **[!UICONTROL Profils et cibles > Profils de test]** ou utilisez la fonctionnalité **[!UICONTROL Adresses de contrôle]** pour ajouter automatiquement des destinataires de test à vos diffusions à des fins d’assurance qualité et de surveillance de boîte de réception.

[Profils de test](../audiences/test-profiles.md)

+++

## Conception de message {#design}

Découvrez comment concevoir des messages marketing efficaces dans Campaign v8, y compris des modèles d’e-mail, des techniques de personnalisation et du contenu multilingue. Concevez vos messages dans la console cliente ou utilisez la version moderne **Email Designer** de l’interface utilisateur web de Campaign pour améliorer l’expérience de modification visuelle.

+++ Quelles sont les bonnes pratiques pour concevoir des emails dans Campaign ?

Directives clés : assurez-vous d’une conception réactive pour les appareils mobiles, utilisez du code compatible HTML 4.0/XHTML avec le CSS intégré, optimisez les images (sous 100KB) avec du texte de remplacement, utilisez des champs de fusion de personnalisation, testez les clients de messagerie avant l’envoi et incluez une version en texte brut. Visez la taille totale des e-mails sous 500KB pour une délivrabilité optimale.

[Guide de conception des emails](../send/email.md) | [&#x200B; Bonnes pratiques de diffusion &#x200B;](delivery-best-practices.md)

+++

+++ Qu’est-ce qu&#39;un modèle de diffusion ? 

Un modèle de diffusion est une diffusion préconfigurée qui enregistre tous les paramètres et paramètres en vue de les réutiliser dans plusieurs campagnes. Les modèles comprennent les règles de la cible, la conception du contenu, la personnalisation, les paramètres techniques (expéditeur, destinataire) et les règles de typologie. Créez-en une et réutilisez-la pour maintenir la cohérence et accélérer la création de campagnes.

[Création de modèles de diffusion](../send/create-templates.md)

+++

+++ Est-il possible d&#39;importer facilement du contenu HTML existant pour créer un email dans Campaign ? 

Oui. Importez du contenu HTML par copier/coller direct dans l’éditeur de contenu, par chargement de fichier à partir de votre ordinateur ou par chargement à partir d’une URL. Assurez-vous que votre HTML utilise du code compatible avec les e-mails (HTML 4.0/XHTML) avec le CSS intégré et hébergez les images sur un serveur public. Campaign ajoute automatiquement la personnalisation et le tracking aux HTML importées.

**Conseil :** pour une expérience de conception d’e-mail optimale, utilisez le **Designer d’e-mail** dans l’interface utilisateur web de Campaign, qui offre des fonctionnalités modernes de glisser-déposer et des modèles réactifs intégrés, plutôt que d’importer des données HTML brutes.

[Importer du contenu HTML](../send/defining-the-email-content.md)

+++

+++ Comment créer une newsletter par abonnement dans Campaign ? 

Oui. Utilisez les services d’information de Campaign pour gérer les abonnements aux newsletters. Les fonctionnalités clés incluent la gestion automatique des souscriptions/désinscriptions, le suivi des abonnements, la gestion de la conformité (RGPD, CAN-SPAM), la prise en charge de plusieurs newsletters, l’intégration web pour les formulaires d’inscription et la diffusion ciblée aux abonnés.

[Gérer les abonnements](../start/subscriptions.md)

+++

+++ Comment personnaliser les messages ? 

Campaign offre des fonctionnalités de personnalisation pour créer des messages pertinents et ciblés en fonction des données, du comportement et des préférences des destinataires.

**Options de Personalization :**

* **Champs de personnalisation** - Insérez les données du destinataire (par exemple, `"Hello {{firstName}}")`
* **Blocs de personnalisation** - Utilisez des blocs de contenu prédéfinis ou personnalisés
* **Contenu conditionnel** - Affichez un contenu différent en fonction des critères du destinataire
* **Données comportementales** - Exploitez l’historique de navigation, les modèles d’achat ou les mesures d’engagement

Testez la personnalisation avant l’envoi pour vérifier que les champs de fusion et la logique conditionnelle fonctionnent correctement.

Guide de [Personalization](../send/personalize.md) | [&#x200B; Champs de personnalisation &#x200B;](../send/personalization-fields.md) | [Contenu conditionnel](../send/conditions.md)

+++

+++ Puis-je envoyer des messages multilingues ? 

Oui. Campaign v8 offre des fonctionnalités multilingues. L’approche la plus simple est celle de l’**interface utilisateur web de Campaign**. L’interface utilisateur web offre une diffusion multilingue native avec des variantes de langue : ajoutez des variantes de langue à votre diffusion et Campaign envoie automatiquement la version appropriée en fonction de la langue préférée du destinataire. Disponible pour les e-mails, notifications push, SMS et messages transactionnels.

Fonctionnalités clés : duplication automatique du contenu, envoi automatique basé sur la langue, basculement de la langue par défaut et gestion facile des variantes.

La console cliente prend également en charge le contenu multilingue à l’aide de contenu et de workflows conditionnels, mais nécessite une configuration plus manuelle.

[Diffusions multilingues (interface utilisateur web)](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/msg/multilingual){target="_blank"} | [Contenu conditionnel (console cliente)](../send/conditions.md)

+++

+++ Puis-je localiser un formulaire web ?

Oui. Les applications web de Campaign prennent en charge la localisation multilingue. Définissez des traductions pour tous les éléments de formulaire (libellés, boutons, messages, texte d’erreur), avec la détection automatique de la langue en fonction du profil du destinataire ou des paramètres du navigateur. Plusieurs versions linguistiques sont prises en charge dans une seule application web, avec une langue de remplacement par défaut si nécessaire.

[Localisation d&#39;applications web](../dev/webapps.md)

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

[Présentation de l’assistant AI](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/content/ai-assistant/generative-gs){target="_blank"} | [Cas d’utilisation de l’assistant AI](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/content/ai-assistant/generative-uc){target="_blank"} | [Alignement des marques](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/content/ai-assistant/ai-assistant/brands-score){target="_blank"}

+++

## Test et envoi de messages {#send}

Découvrez les bonnes pratiques relatives au test, à la validation, à l’envoi et au suivi de vos messages marketing pour garantir une diffusion réussie de la campagne.

+++ Qu&#39;est-ce que l&#39;analyse de la diffusion ?

L’analyse de la diffusion est une phase de validation que Campaign exécute avant l’envoi. Il calcule la population cible, valide le contenu, recherche les erreurs, applique les règles de typologie et estime le volume de diffusion.

Campaign génère des logs qui affichent les avertissements et les erreurs. Les erreurs bloquent la diffusion et doivent être corrigées ; les avertissements sont indicatifs. Consultez toujours les journaux d’analyse avant de les envoyer.

[Guide d’analyse de la diffusion](../send/delivery-analysis.md)

+++

+++ Pourquoi créer des bons à tirer ?

Les BAT sont des messages de test qui valident votre diffusion avant envoi à votre audience principale. Utilisez des BAT pour vérifier la personnalisation, tester le rendu du contenu sur les clients de messagerie, confirmer les liens et le travail de suivi, vérifier les images et les pièces jointes et valider la réactivité mobile.

Les BAT permettent de détecter les erreurs avant qu’elles n’atteignent des milliers de destinataires, d’activer l’approbation des parties prenantes et de tester l’emplacement de la boîte de réception. Envoyez des BAT à plusieurs clients de messagerie et appareils et obtenez toujours une approbation avant l’envoi des BAT par l’exploitation.

[Guide de prévisualisation et des BAT](../send/preview-and-proof.md)

+++

+++ Comment utiliser les adresses de contrôle dans Adobe Campaign ?

Les adresses de contrôle sont des destinataires spéciaux automatiquement ajoutés à chaque diffusion à des fins de test, d’assurance qualité et de surveillance, sans correspondre à vos critères cibles. Utile pour la surveillance continue, les tests d’emplacement de la boîte de réception, la validation du publipostage direct et la visibilité des parties prenantes.

**Principales différences par rapport aux BAT :**

* **Adresses de contrôle** - ajoutées automatiquement aux diffusions de production, comptabilisées dans le volume d’envoi
* **BAT** - Le test envoie avant la production, ne pas comptabiliser dans le volume, utilisé pour la validation.

Gérez les adresses de contrôle dans **[!UICONTROL Ressources > Gestion de campagne > Adresses de contrôle]**. Gardez les listes petites pour éviter d’impacter les mesures de diffusion.

[&#x200B; Guide des adresses de contrôle &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/delivery-control.html?lang=fr){target="_blank"}

+++

+++ Comment configurer un processus de validation avant l&#39;envoi des messages ?

Campaign fournit des workflows de validation pour s’assurer que les messages répondent aux normes de qualité avant envoi. Configurez les validations du contenu, de la cible, de l’extraction (publipostage direct) et du budget au niveau de la campagne ou de la diffusion.

**Configuration:**

Créez des groupes d’opérateurs dans **[!UICONTROL Administration > Gestion des accès > Groupes d’opérateurs]**, puis affectez des groupes de validation dans les propriétés de la campagne ou de la diffusion. Campaign envoie des e-mails de notification aux réviseurs qui peuvent approuver, rejeter ou demander des modifications.

**Pour les diffusions autonomes (hors campagne) :**

Utilisez les **BAT comme processus d’approbation**. Envoyez des BAT à votre groupe d’approbation pour validation et envoyez toujours un nouveau BAT après avoir apporté des modifications pour vous assurer que les parties prenantes examinent la dernière version.

[&#x200B; Validation de la diffusion &#x200B;](../send/preview-and-proof.md) | [Validations de campagne](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=fr){target="_blank"}

+++

+++ Qu&#39;est-ce qu&#39;une règle de typologie ?

Les règles de typologie sont une logique commerciale automatisée appliquée lors de l’analyse de la diffusion pour valider et optimiser l’envoi des messages. Ils assurent la conformité aux politiques marketing, protègent la délivrabilité et évitent la fatigue des clients.

**Principaux types de règle :**

* placer sur la liste bloquée **Règles de filtrage** - Exclure les destinataires (inscrits, désabonnés, mis en quarantaine)
* **Règles de pression** - Contrôlez la fréquence des messages pour éviter de surcharger les destinataires
* **Règles de capacité** - Limite le volume de messages pour les limites de capacité de traitement ou de FAI.
* **Règles de contrôle** - Vérifier la validité du message (objet, lien de désabonnement, format de l’expéditeur)

Les règles sont regroupées en typologies et appliquées lors de l&#39;analyse de la diffusion. Campaign peut exclure des destinataires, bloquer la diffusion ou générer des avertissements en fonction des règles.

[&#x200B; Guide des règles de typologie &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=fr){target="_blank"}

+++

+++ Comment envoyer des emails par vagues ?

Oui. L’envoi par vague divise votre diffusion en plusieurs lots envoyés à des intervalles planifiés. Cela est essentiel pour les campagnes à volume élevé afin d’équilibrer la charge du serveur, d’empêcher le ralentissement des FAI, de construire la réputation de l’expéditeur avec de nouvelles adresses IP et de gérer les désinscriptions/bounces entre les vagues.

**Configuration:**

Dans les propriétés de votre diffusion, activez l’envoi de vagues et définissez le nombre de vagues (ou la taille du lot), l’intervalle entre les vagues et la répartition des vagues (pourcentages linéaires ou personnalisés). Campaign divise automatiquement votre population cible et envoie chaque vague selon le calendrier prévu.

Utilisez les vagues pour les campagnes volumineuses, surveillez les performances de la première vague avant de continuer et patientez suffisamment entre les vagues pour traiter les rebonds et les désinscriptions.

[Configurer l’envoi de vagues](../send/configure-and-send.md#sending-using-multiple-waves)

+++

+++ Quelles sont les principales étapes pour créer un email dans Campaign ?

La création d&#39;un email dans Campaign v8 implique les étapes clés suivantes : créer la diffusion, définir l&#39;audience cible, concevoir le contenu, ajouter de la personnalisation, configurer les paramètres (expéditeur, objet, destinataire), exécuter l&#39;analyse de la diffusion, envoyer des BAT pour les tests et enfin envoyer ou planifier.

**Étapes clés :**

1. **Créer la diffusion** - Sélectionnez le canal E-mail et éventuellement un modèle de diffusion
1. **Définir la cible** - Sélectionnez l’audience de vos destinataires à l’aide de requêtes, de listes ou de fichiers importés
1. **Concevoir le contenu** - Créez votre message à l’aide de l’éditeur d’e-mail (Web UI Email Designer ou éditeur de console cliente)
1. **Ajouter une personnalisation** - Insérer des champs dynamiques, des blocs de personnalisation et du contenu conditionnel
1. **Configurer les paramètres** - Définir l’adresse expéditeur, l’objet, le destinataire et les paramètres de diffusion
1. **Exécuter l’analyse de la diffusion** - Campaign valide le contenu, calcule la cible et vérifie les erreurs
1. **Envoyer des BAT** - Testez votre e-mail avec des groupes d’approbation pour valider le rendu et le contenu
1. **Envoyer ou planifier** - Envoyer immédiatement à la cible principale ou planifier une date ultérieure.

**Deux options d’interface :**

* **UI web de Campaign** - Interface moderne avec Designer d’e-mail améliorée, assistant d’IA et fonctionnalités multilingues
* **Console cliente** - Interface traditionnelle avec des fonctionnalités avancées de ciblage et de workflow

**Conseil :** utilisez l’interface utilisateur web de Campaign pour accélérer la création d’e-mails, plus intuitive, avec des outils de conception modernes. Utilisez la console cliente pour des campagnes complexes de ciblage ou basées sur des workflows avancés.

[Créer votre premier e-mail](create-message.md) | [Guide de conception des emails](../send/email.md)

+++

+++ Comment planifier une diffusion ?

Campaign vous permet de planifier des diffusions pour des envois futurs afin d’optimiser les heures d’envoi et de coordonner les campagnes.

**Options de planification :**

* **Propriétés de diffusion** - Envoi immédiat, planification d’une date/heure spécifique ou report par heures/jours
* **Niveau de la campagne** - Coordonner toutes les diffusions d’une campagne
* **Activité Planificateur de workflow** - Pour les diffusions récurrentes, les modèles complexes et les campagnes déclenchées par un événement

Campaign prend également en charge l’optimisation des dates de contact (meilleure heure d’envoi par destinataire) et l’adaptation des fuseaux horaires (même heure locale pour tous les destinataires).

[Planifier l’envoi de diffusion](../send/configure-and-send.md#schedule-delivery-sending)

+++

+++ Est-il possible d&#39;ajouter une pièce jointe aux emails ?

Oui. Campaign prend en charge les pièces jointes statiques (même fichier pour tous les destinataires) et les pièces jointes personnalisées (différents fichiers par destinataire en fonction des données de profil). Ajoutez des pièces jointes dans la section **[!UICONTROL Pièces jointes]** des propriétés de votre diffusion.

**Considérations importantes :**

* Conserver les pièces jointes de moins de 1 Mo pour une délivrabilité optimale
* Les pièces jointes peuvent déclencher des filtres antispam ; à tester minutieusement avant l’envoi
* Évitez les types de fichiers généralement bloqués par les clients de messagerie (.exe, .zip, .js)
* Pour les fichiers volumineux, pensez à utiliser plutôt des liens de téléchargement suivis

Utilisez des formats de fichiers sécurisés (PDF, JPEG, PNG, DOCX) et testez-les avec des adresses de contrôle avant les envois en production.

[Guide des pièces jointes à un email](../send/email.md#attachments)

+++

+++ Comment configurer des liens suivis dans une diffusion d&#39;email ?

Campaign convertit automatiquement toutes les URL de votre e-mail en liens trackés afin de surveiller l’engagement des destinataires. Accédez à la section **[!UICONTROL Tracking]** de votre diffusion pour configurer les paramètres de tracking de chaque lien.

**Options de configuration :**

* **Activer/désactiver le suivi** - Contrôler le suivi par lien
* **Libellés du lien** - Ajoutez des noms descriptifs pour les rapports (par exemple, « Shop Now CTA »).
* **Catégories de liens** - Regroupez les liens par type pour une analyse agrégée.
* **Type de tracking** - Effectuez le suivi des clics, des ouvertures ou des deux

Campaign effectue le suivi des liens de contenu, des liens de page miroir et des liens de désabonnement. Elle peut également inclure un pixel de suivi facultatif pour les ouvertures d’e-mail. Utilisez des libellés et des catégories pertinents pour simplifier la création de rapports et identifier rapidement le contenu hautement performant.

[&#x200B; Guide de suivi des liens &#x200B;](../start/tracking.md) | [Bonnes pratiques de tracking](../send/send.md)

+++

+++ Où se trouvent les logs de diffusion et de tracking ?

Accédez directement aux logs de diffusion et de tracking depuis chaque tableau de bord de diffusion. Dans la console cliente, cliquez sur l’onglet **[!UICONTROL Diffusion]** dans la partie inférieure. Dans l’interface utilisateur web de Campaign, accédez à la section **[!UICONTROL Journaux]**.

**Journaux disponibles :**

* **Logs de diffusion** - Messages envoyés avec les détails et le statut du destinataire (envoyés, en attente, en échec)
* **Logs de tracking** - Interactions des destinataires (ouvertures, clics) avec horodatage
* **Logs d&#39;exclusion** - Destinataires exclus avec leurs raisons (quarantaine, règles de typologie, doublons)
* **Journaux de diffusion** - Historique complet des envois, y compris les reprises et les erreurs

Utilisez ces journaux pour résoudre les problèmes de diffusion, analyser l’engagement et maintenir l’hygiène de la liste.

[Surveillance des diffusions](../send/send.md) | [Guide de tracking](../start/tracking.md)

+++

+++ Où obtenir des rapports de diffusion ?

Campaign fournit des rapports intégrés complets pour analyser les performances des diffusions, l’engagement des destinataires et l’efficacité des campagnes. Accédez aux rapports à partir de l’onglet **[!UICONTROL Rapports]** dans n’importe quelle diffusion, depuis le tableau de bord de la campagne ou à partir du menu global **[!UICONTROL Rapports]** pour une analyse intercampagnes.

**Les principaux rapports sont les suivants :**

* **Résumé de diffusion** - Envoi de statistiques, ouvertures, clics, bounces et désabonnements
* **Position des clics** - Carte thermique visuelle des performances des liens
* **Indicateurs de tracking** - Taux de clics publicitaires et mesures d’engagement
* **Échecs** - Analyse des retours avec les raisons des échecs

Les rapports sont disponibles dans la console cliente et l’interface utilisateur web de Campaign avec des visualisations modernes.

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

[&#x200B; Guide de gestion des quarantaines &#x200B;](../send/quarantines.md) | [Gestion des bounces](../send/delivery-failures.md)

+++

## Workflows {#workflows}

Découvrez comment utiliser des workflows pour automatiser les processus, gérer les données et orchestrer des campagnes marketing complexes dans Adobe Campaign.

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

* [Création d’un workflow](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=fr){target="_blank"}
* [Activités de workflow](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/about-activities.html){target="_blank"}
* [Bonnes pratiques relatives aux workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=fr){target="_blank"}
* [Cas pratiques des workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/about-workflow-use-cases.html){target="_blank"}

+++

+++ Comment importer des données dans Campaign ?

Importez des données dans Campaign à l&#39;aide de plusieurs méthodes en fonction de vos besoins :

**Import de fichier simple :**

* Utiliser l’assistant d’importation pour les importations CSV/TXT uniques avec une interface guidée
* Idéal pour les chargements manuels et les chargements rapides de données

**Importation basée sur les workflows :**

* Créer des workflows avec l&#39;activité **[!UICONTROL Chargement (fichier)]** pour des imports complexes
* Ajout de transformations, d’enrichissement et de déduplication des données
* Planifier des imports récurrents depuis SFTP, des répertoires locaux ou un espace de stockage dans le cloud

**Intégration d’API :**

* Utiliser les API REST pour importer des données par programmation à partir de systèmes externes
* Idéal pour la synchronisation en temps réel avec CRM, e-commerce ou d’autres plateformes

**Bonnes pratiques :** testez toujours avec de petits échantillons, utilisez le codage UTF-8, mappez correctement les champs, appliquez des règles de déduplication et planifiez des importations volumineuses pendant les heures creuses.

**Rubriques connexes :**

* [Bonnes pratiques d&#39;import](../start/import.md)
* [Activité de chargement des données](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=fr){target="_blank"}
* [Workflow d’import récurrent](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/recurring-import-workflow.html?lang=fr){target="_blank"}

+++

+++ Est-il possible de surveiller l’exécution des workflows ?

Oui. Campaign fournit des fonctionnalités complètes de surveillance des workflows pour suivre l’exécution, identifier les problèmes et optimiser les performances.

**Options de surveillance :**

* **Tableau de bord des workflows** - Affichez le statut d’exécution en temps réel, la progression et les états d’activité
* **Journaux d’exécution** - Accédez aux journaux détaillés de chaque activité et transition
* **Journal d&#39;audit** - Suivre les modifications apportées aux workflows et l&#39;historique de leur exécution
* **Alertes et notifications** - Configurez des alertes par e-mail en cas d’échec ou de conditions spécifiques

**Principales fonctionnalités de surveillance :**

* Indicateurs visuels de statut (en attente, en cours, terminé, en échec)
* Suivi du temps d’exécution pour l’optimisation des performances
* Messages d’erreur au niveau de l’activité pour la résolution des problèmes
* Suspendre, arrêter ou redémarrer les workflows selon les besoins

Le suivi des accès depuis **[!UICONTROL Administration > Exploitation > Objets créés automatiquement > Workflows des campagnes]** ou directement depuis le tableau de bord des workflows.

**Rubriques connexes :**

* [Surveillance de l’exécution des workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=fr){target="_blank"}
* [Bonnes pratiques relatives aux workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=fr){target="_blank"}
* [Démarrage d’un workflow](https://experienceleague.adobe.com/docs/campaign/automation/workflows/executing-a-workflow/start-a-workflow.html?lang=fr){target="_blank"}

+++

+++ Comment mettre à jour les données de Campaign avec un workflow ?

Utilisez l&#39;activité **[!UICONTROL Mise à jour de données]** dans les workflows pour effectuer des opérations en bloc sur votre base de données :

**Opérations prises en charge :**

* **Insérer** - Ajout de nouveaux enregistrements à la base de données
* **Mettre à jour** - Modifier les enregistrements existants en fonction des critères correspondants
* **Insérer ou mettre à jour** - Ajouter de nouveaux enregistrements ou mettre à jour les enregistrements existants (upsert)
* **Supprimer** - Supprime les enregistrements correspondant à des critères spécifiques

**Cas d’utilisation courants :**

* Mettre à jour les attributs de profil après l’enrichissement des données
* Synchronisation des données avec des systèmes externes
* Tenir à jour les appartenances à la liste en fonction du comportement
* Nettoyer et dédupliquer les données
* Application de modifications de statut en bloc (par exemple, désinscription, quarantaine)

Configurez les clés de réconciliation pour correspondre précisément aux enregistrements et choisissez les options de mise à jour (mettez à jour tous les champs ou uniquement les champs vides).

**Rubriques connexes :**

* [Activité Mise à jour de données](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html?lang=fr){target="_blank"}
* [Activités de Data Management](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/about-action-activities.html){target="_blank"}

+++

+++ Comment utiliser les fonctionnalités de Data Management ?

Les activités de gestion des données de Campaign permettent des opérations de données sophistiquées dans les workflows pour un ciblage et une segmentation complexes.

**Principales activités de Data Management :**

* **Enrichissement** - Ajoutez des données provenant de tables associées ou de sources externes à votre population active.
* **Fractionner** - Segmenter les populations en fonction de critères ou les répartir de manière aléatoire
* **Déduplication** - Supprime les enregistrements en double en fonction des clés spécifiées
* **Mise à jour de données** - Effectuez des opérations d’insertion, de mise à jour ou de suppression en bloc
* **Modifier la dimension** - Changez les dimensions de ciblage (par exemple, des destinataires aux abonnements)
* **Intersection/Union/Exclusion** - Combiner ou filtrer plusieurs populations

**Cas d’utilisation courants :**

* Enrichir les profils avec des données d’historique d’achat ou de comportement
* Segmenter les audiences en plusieurs groupes pour différents messages
* Supprimer les doublons avant la diffusion
* Intégrer des données provenant de bases de données externes (FDA - Federated Data Access)
* Créer des requêtes et des jointures complexes de plusieurs tables

Ces activités vous permettent d’utiliser des données qui ne se trouvent pas directement dans la table des destinataires principale et d’effectuer des opérations de base de données avancées.

**Rubriques connexes :**

* [Activités de Data Management](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/about-targeting-activities.html){target="_blank"}
* [Workflows de ciblage](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/targeting-workflows.html?lang=fr){target="_blank"}
* [Activité d’enrichissement](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html?lang=fr){target="_blank"}

+++

+++ Est-il possible d’automatiser l’envoi de messages personnalisés ?

Oui. Les workflows activent des campagnes de messages personnalisées entièrement automatisées basées sur les données, le comportement et les critères personnalisés des destinataires.

**Structure de workflow d’automatisation :**

1. **Requête** - Sélectionnez votre audience cible en fonction de critères
1. **Enrichissement** - Ajout de données de personnalisation provenant de tables associées
1. **Fractionner** - Segmenter en groupes pour différentes variantes de messages (facultatif)
1. **Diffusion** - Envoyez des messages personnalisés avec des champs de fusion
1. **Planificateur** - Configurer l’exécution récurrente des campagnes automatisées

**Options de Personalization :**

* Utiliser les données du profil du destinataire (nom, emplacement, préférences)
* Inclure les données comportementales (historique d’achat, scores d’engagement)
* Application de contenu conditionnel en fonction de segments ou d’attributs
* Calculer les valeurs dynamiques (points de fidélité, dates d’expiration)

Scénarios courants : campagnes d’anniversaire, abandon de panier, programmes de fidélité, campagnes de reconquête et messages déclenchés par un événement.

**Rubriques connexes :**

* [Guide de Personalization](../send/personalize.md)
* [Cas pratiques des workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=fr){target="_blank"}
* [Activité d’enrichissement](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/enrichment.html?lang=fr){target="_blank"}

+++

+++ Comment partager une audience en sous-ensembles avec un workflow ?

Utilisez l&#39;activité **[!UICONTROL Partage]** pour diviser une seule population en plusieurs sous-ensembles en fonction de critères ou de règles de distribution.

**Méthodes de partage :**

* **Conditions de filtrage** - Création de sous-ensembles en fonction de critères (par exemple, tranche d&#39;âge, lieu, statut VIP)
* **Distribution en pourcentage** - Divisez de manière aléatoire les pourcentages égaux ou personnalisés pour les tests A/B
* **Limiter les enregistrements** - Limiter les tailles des sous-ensembles (N premiers enregistrements, X premiers %, sélection aléatoire)
* **Groupement de données** - Créez un sous-ensemble par valeur distincte (par exemple, un sous-ensemble par pays)

**Cas d’utilisation courants :**

* Tests A/B avec populations témoins
* Routage des préférences de canal (e-mail ou SMS)
* Déploiement progressif (envoi à 10 %, puis à 90 %)
* Messages spécifiques au segment (VIP, standard, nouveaux clients)
* Répartition de charge sur plusieurs serveurs de diffusion

Chaque sous-ensemble divisé est dirigé vers une transition distincte, ce qui permet un traitement ou une diffusion différents pour chaque groupe.

**Rubriques connexes :**

* [Activité Partage](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/split.html?lang=fr){target="_blank"}
* [Guide de test A/B](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/a-b-testing.html){target="_blank"}

+++

+++ Comment mettre à jour les données des destinataires à partir d&#39;un fichier externe ?

Oui. Utilisez des workflows pour mettre à jour les données de Campaign avec des valeurs provenant de fichiers externes (CSV, TXT).

**Structure de workflow :**

1. **Chargement (fichier)** - Chargez le fichier externe et mappez les colonnes
1. **Enrichissement** (facultatif) - Ajoutez des données ou des transformations supplémentaires
1. **Réconciliation** - Définissez des clés pour faire correspondre les enregistrements de fichier aux enregistrements de base de données (par exemple, adresse e-mail, ID de destinataire).
1. **Mettre à jour les données** - Choisissez les options de mise à jour :
   * Mettre à jour uniquement les enregistrements correspondants
   * Mettre à jour les champs existants ou uniquement les champs vides
   * Insérer de nouveaux enregistrements si aucune correspondance trouvée

**Scénarios courants :**

* Mise à jour des attributs de profil à partir des exports CRM
* Actualiser les statuts d’abonnement depuis des systèmes externes
* Synchroniser les points de fidélité ou les scores des clients
* Mettre à jour les préférences d’opt-in/opt-out
* Enrichissement des profils avec des données comportementales

**Bonnes pratiques :** utilisez des identifiants uniques pour la réconciliation, validez les données avant la mise à jour, testez avec de petits échantillons et planifiez des mises à jour régulières pour une synchronisation en cours.

**Rubriques connexes :**

* [Guide d’importation des données](../start/import.md)
* [Activité de chargement des données](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/data-loading-file.html?lang=fr){target="_blank"}
* [Activité Mise à jour de données](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/update-data.html?lang=fr){target="_blank"}

+++

+++ Comment identifier et cibler de nouveaux destinataires ?

Utilisez des workflows avec des activités de requête pour identifier les destinataires récemment ajoutés et déclencher des campagnes de bienvenue automatisées.

**Approche de requête :**

Créez un filtrage de requête sur le champ **[!UICONTROL Date de création]** pour sélectionner les destinataires ajoutés au cours d’une période spécifique (par exemple, les dernières 24 heures, la semaine dernière).

**Structure de workflow de bienvenue automatisée :**

1. **Planificateur** - Exécuter quotidiennement ou à des intervalles spécifiques
1. **Requête** - Sélection des destinataires créés depuis la dernière exécution
1. **Déduplication** (facultatif) - Vérifiez qu’aucun doublon n’est présent
1. **Diffusion** - Envoyez un message de bienvenue
1. **Mise à jour de données** (facultatif) - Marquez les destinataires comme « bienvenus »

**Technique avancée avec des agrégats :**

Utilisez les fonctions d’agrégat pour identifier dynamiquement les ajouts les plus récents et les comparer aux destinataires précédemment traités pour une détection sophistiquée des nouveaux destinataires.

**Rubriques connexes :**

* [Activité Requête](https://experienceleague.adobe.com/fr/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=fr){target="_blank"}
* [Utilisation d&#39;agrégats](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/data-management/using-aggregates.html?lang=fr){target="_blank"}
* [Programmes de bienvenue](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=fr){target="_blank"}

+++

+++ Comment utiliser les activités de workflow ?

Les workflows de campagne sont créés à l&#39;aide de quatre catégories principales d&#39;activités, chacune poursuivant des objectifs spécifiques :

**Activités de ciblage** - Définissez et affinez votre audience

* Requête, Partage, Déduplication, Enrichissement, Intersection, Union, Exclusion
* Utilisez-les pour sélectionner des destinataires, segmenter des populations et combiner des sources de données

**Activités de contrôle de flux** - Gestion de la logique et de la durée des workflows

* Planificateur, Attente, Test, Branchement, Rendez-vous, Rendez-vous, Saut
* Contrôler le flux d’exécution, ajouter des conditions et gérer les chemins parallèles

**Activités d&#39;action** - Effectuer des opérations et envoyer des messages

* Diffusion, Mise à jour de données, Chargement (fichier), Extraction (fichier), Code JavaScript
* Exécuter des opérations de base de données, des transferts de fichiers et l’envoi de messages

**Activités d&#39;événement** - Réaction à des déclencheurs externes

* Signal externe, Collecteur de fichiers, Transfert HTTP, SMS, E-mail
* Gérer les données entrantes et les interactions système externes

Pour utiliser des activités, faites-les glisser de la palette vers la zone de travail de votre workflow, double-cliquez pour configurer des paramètres et associez-les à des transitions.

**Rubriques connexes :**

* [Référence des activités de ciblage](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/targeting-activities.html?lang=fr){target="_blank"}
* [Référence des activités de contrôle de flux](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/flow-control-activities/flow-control-activities.html?lang=fr){target="_blank"}
* [Référence des activités d’action](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/action-activities.html?lang=fr){target="_blank"}
* [Référence des activités d’événement](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/event-activities/event-activities.html?lang=fr){target="_blank"}

+++

+++ Quelles sont les bonnes pratiques en matière de workflow ?

Suivez ces bonnes pratiques pour créer des workflows efficaces, gérables et fiables :

**Conception et organisation :**

* Utiliser des noms clairs et descriptifs pour les workflows et les activités
* Ajout de libellés et de descriptions à la logique du document
* Regroupez visuellement les activités liées pour en faciliter la lecture
* Scinder des processus complexes en plusieurs workflows plus petits

**Optimisation des performances :**

* Limiter les tailles de résultats de requête avec les filtres appropriés
* Utiliser des tables temporaires pour le stockage intermédiaire des données
* Planification de workflows gourmands en ressources pendant les heures creuses
* Éviter les boucles inutiles et les itérations excessives

**Gestion et surveillance des erreurs :**

* Ajouter des chemins de gestion des erreurs avec les superviseurs
* Configurer des alertes pour les workflows ayant échoué
* Tester avec de petits échantillons de données avant l’exécution complète
* Consultez régulièrement les journaux d’exécution pour identifier les problèmes de performances

**Maintenance et gouvernance :**

* Archivage ou suppression de workflows obsolètes
* Modifications du workflow de contrôle de version et modifications du document
* Limiter la complexité du workflow (viser moins de 20 activités)
* Utiliser des modèles de workflow pour les modèles récurrents

**Sécurité et gestion des données :**

* Appliquer les autorisations d’opérateur appropriées
* Nettoyage des données temporaires à l’aide du nettoyage de workflow
* Évitez les valeurs de codage en dur : utilisez des variables et des options.
* Examinez et optimisez régulièrement les workflows peu performants

**Rubriques connexes :**

* [&#x200B; Guide des bonnes pratiques relatives aux workflows &#x200B;](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=fr){target="_blank"}
* [Création d’un workflow](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=fr){target="_blank"}
* [Surveiller les workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=fr){target="_blank"}

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


[Modification de la langue dans l’interface utilisateur web de Campaign](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/start/connect-to-campaign#language-pref){target="_blank"} | [Prise en main de la console cliente Campaign](connect.md)

+++

+++ Puis-je utiliser Campaign v8 avec d’autres solutions Adobe ?

Oui. Campaign v8 s’intègre de manière transparente aux solutions Adobe Experience Cloud pour créer un puissant écosystème marketing unifié. En tant que Managed Cloud Service, v8 est conçu pour une intégration native aux applications d’entreprise Adobe.

**Intégrations clés disponibles :**

* **Adobe Experience Platform** - Exploitez les profils clients unifiés et les données en temps réel
* **Adobe Analytics** - Mesurez les performances de la campagne et le comportement des clients sur l’ensemble des canaux
* **Adobe Target** - Personnaliser le contenu en fonction des segments et du comportement des clients
* **Adobe Experience Manager** - Centralisez la création de contenu et la gestion des ressources
* **Adobe Audience Manager** - Créez et activez des segments d’audience sur plusieurs plateformes

**Avantages :** données client unifiées, expériences utilisateur cohérentes, workflows rationalisés et fonctionnalités de personnalisation améliorées.

**Configuration :** l&#39;intégration avec les solutions Adobe nécessite une authentification Adobe Identity Management System (IMS), automatiquement configurée pour Campaign v8 Managed Cloud Services.

[Intégrations Adobe Campaign](../connect/integration.md) | [Connexion à Adobe ID](connect.md)

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

[Suivre et surveiller les diffusions](tracking.md) | [Configuration des liens suivis](../send/email.md)

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

[À propos de la délivrabilité dans Campaign](../send/about-deliverability.md) | [&#x200B; Guide des bonnes pratiques en matière de délivrabilité &#x200B;](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=fr){target="_blank"}

+++

+++ À quelles bases de données externes est-il possible de connecter Campaign ? 

Campaign v8 prend en charge les connexions FDA (Federated Data Access) aux principaux systèmes de base de données d’entreprise, ce qui vous permet d’exploiter les infrastructures de données existantes.

**Bases de données prises en charge :**

* **Bases de données cloud :** Amazon Redshift, Google BigQuery, Snowflake, Azure Synapse Analytics
* **Bases de données d’entreprise :** Oracle, Microsoft SQL Server, PostgreSQL, MySQL
* **Entrepôts de données :** Teradata, Vertica, SAP HANA
* **Big data :** Hadoop via Hive

**Considérations spécifiques à Platform :** les versions de base de données prises en charge et les exigences de connexion varient. Campaign v8 as a Managed Cloud Service peut avoir des exigences spécifiques en matière de réseau et de sécurité pour l’accès aux bases de données externes.

**Important :** vérifiez toujours la matrice de compatibilité officielle de votre version de Campaign v8 pour confirmer la prise en charge de versions de base de données spécifiques et assurez-vous que les licences des connecteurs de base de données externes sont correctes.

[Matrice de compatibilité](compatibility-matrix.md) | [Configuration des connexions FDA](../connect/fda.md)

+++

+++ Adobe Campaign peut-il s’intégrer aux systèmes CRM ?

Oui. Campaign fournit des connecteurs CRM natifs pour une synchronisation bidirectionnelle transparente entre Campaign et votre système CRM, ce qui garantit la cohérence des données client sur toutes les plateformes.

**Systèmes CRM pris en charge :**

* **Salesforce** - Leads, contacts, comptes, opportunités, campagnes
* **Microsoft Dynamics 365** - Contacts, comptes, prospects, entités personnalisées
* Autres CRM via des intégrations d’API personnalisées

**Synchronisations :**

* **De CRM à Campaign :** enregistrements de contacts, informations de compte, leads, champs personnalisés, données de segmentation
* **De Campaign vers CRM :** logs de diffusion, données de tracking, mesures d’engagement, réponses de campagne, statut d’abonnement

**Modes de synchronisation :**

* **Planifié** - Synchronisation automatique à intervalles définis (par heure, quotidiennement)
* **Manuel** - Synchronisation à la demande déclenchée par les opérateurs
* **Temps réel** - Via l’API pour des mises à jour immédiates (développement personnalisé)

**Configuration :** utilisez l’assistant de connecteur CRM intégré à Campaign pour mapper les champs CRM aux attributs Campaign, sélectionner les tables à synchroniser et planifier la synchronisation. Le connecteur gère la résolution des conflits et maintient la cohérence des données.

**Bonne pratique :** commencez par une synchronisation en lecture seule pour tester le mappage, puis activez la synchronisation bidirectionnelle. Surveillez les journaux de synchronisation à la recherche d&#39;erreurs et conservez des données propres sur les deux systèmes.

[Configuration du connecteur CRM](../connect/crm.md) | [Activités Workflow CRM](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/crm-connector.html?lang=fr){target="_blank"}

+++

+++ Comment effacer le cache de la console cliente ?

L’effacement du cache de la console cliente résout de nombreux problèmes courants d’affichage et de fonctionnalité. Le cache stocke les fichiers de configuration locaux qui peuvent parfois être corrompus ou obsolètes.

**Quand vider le cache :**

* Les nouveaux éléments de branding (logos, couleurs) ne s’affichent pas correctement
* Échec inattendu des fonctions d’exportation/d’importation
* Les éléments d’interface ne se mettent pas à jour après les modifications de configuration
* Problèmes de performances ou réponse lente de la console
* Après la mise à niveau vers une nouvelle version de la console cliente

**Procédure d’effacement du cache :**

1. Ouvrir la console cliente Campaign
2. Accéder au menu **[!UICONTROL Fichier]**
3. Sélectionnez **[!UICONTROL Effacer le cache local...]**
4. Confirmer l’action lorsque vous y êtes invité
5. Redémarrez la console cliente



[Installation et configuration de la console cliente](connect.md)

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
* **Groupe d’opérateurs** - Paramètres hérités par tous les membres du groupe


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


[Étendre le modèle de données](../dev/extend-schema.md) | [Structure d&#39;un schéma](../dev/schemas.md) | [Bonnes pratiques relatives au modèle de données](../dev/datamodel-best-practices.md)

+++

## Rapports {#reporting}

Obtenez des informations sur les fonctionnalités de reporting de Campaign, y compris les rapports intégrés, les rapports personnalisés et les outils d’analyse de données tels que les cubes.

+++ Comment créer de nouveaux rapports ?

Campaign propose plusieurs options de reporting en fonction de vos besoins et de votre expertise technique. Vous pouvez utiliser des rapports intégrés, créer des rapports personnalisés dans la console cliente ou concevoir des tableaux de bord visuels dans l’interface utilisateur web de Campaign.

**Options de création de rapports :**

* **Rapports intégrés** - Rapports de diffusion, de campagne et de tracking prêts à l’emploi accessibles à partir de l’onglet **[!UICONTROL Rapports]**
* **Analyse descriptive** - Rapports statistiques rapides sur toutes les données avec une interface pilotée par un assistant
* **Rapports personnalisés** - Rapports avancés créés par les utilisateurs et utilisatrices techniques à l’aide de l’éditeur de rapports
* **Tableaux de bord de l’interface utilisateur web** - Rapports visuels et tableaux de bord modernes avec interface par glisser-déposer
* **Cubes** - Exploration des données multidimensionnelles et analyse des tableaux croisés dynamiques

**Important :** Campaign est conçu pour le reporting des opérations marketing, et non comme un outil spécialisé de Business Intelligence. Pour les besoins analytiques complexes, envisagez l’intégration à Adobe Analytics ou à des plateformes de BI dédiées.

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

[Analyse descriptive](../reporting/built-in-reports.md)

+++

+++ Comment concevoir des rapports avancés sur mes données ?

Campaign propose deux approches pour créer des rapports personnalisés avancés : des rapports techniques dans la console cliente pour des analyses complexes et des tableaux de bord visuels pour une création de rapports plus facile.

Dans la console cliente, vous pouvez :

* Créer des rapports complexes à l’aide de requêtes SQL et de calculs personnalisés
* Créer des rapports de plusieurs pages avec des graphiques, des tableaux et des tableaux croisés dynamiques
* Conception de formatage conditionnel et de contenu dynamique
* Accéder au modèle de données Campaign complet et aux bases de données externes (FDA)


[Création de rapports personnalisés (console cliente)](../reporting/custom-reports.md)

+++

+++ Qu’est-ce qu’un cube et comment l’utiliser pour la création de rapports ?

Les cubes sont des structures de données multidimensionnelles qui permettent aux utilisateurs professionnels d&#39;explorer et d&#39;analyser les données de Campaign par le biais de tableaux croisés dynamiques sans compétences techniques. Considérez-les comme des modèles de données préconfigurés qui simplifient les rapports complexes.


* Les utilisateurs et utilisatrices techniques créent et configurent des cubes définissant les dimensions (temps, zone géographique, canaux) et les mesures (ouvertures, clics, chiffre d’affaires)
* Les utilisateurs professionnels sélectionnent un cube lors de la création de rapports et font glisser et déposer des dimensions pour explorer les données
* Les données sont automatiquement agrégées et calculées en fonction de la configuration du cube
* Les résultats peuvent être affichés sous forme de tableaux croisés dynamiques, de graphiques ou exportés vers Excel


[Explorer des données avec des cubes](../reporting/gs-cubes.md)

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

**Rapports d’enquête intégrés :**

* **Rapport général** - Tendances des réponses dans le temps, répartition par origine et par langue
* **Répartition des réponses** - Répartition détaillée des réponses pour chaque question
* **Rapport de documentation** - Représentation visuelle de la structure du questionnaire

**Analyse avancée :**

* Accéder aux réponses à un questionnaire à partir de l&#39;onglet **[!UICONTROL Réponses]** et exporter les données
* Utilisez l’activité **[!UICONTROL Réponses à un questionnaire]** dans les workflows pour cibler les destinataires en fonction de leurs réponses
* Combiner les données d’enquête avec d’autres données Campaign pour la segmentation et la personnalisation
* Créer des rapports et des cubes personnalisés pour l&#39;analyse multidimensionnelle des questionnaires


[Prise en main des questionnaires](https://experienceleague.adobe.com/fr/docs/campaign-classic/using/online-surveys/about-surveys){target="_blank"} | [Rapports d’enquête](https://experienceleague.adobe.com/fr/docs/campaign-classic/using/online-surveys/publish-track-and-use-collected-data#reports-on-surveys){target="_blank"}

+++

+++ Comment partager l’accès à mes rapports ?

Campaign offre des options flexibles pour partager des rapports avec différents groupes d’utilisateurs, contrôler la visibilité et les autorisations d’accès en fonction des rôles et des responsabilités.

**Contrôle d’accès aux rapports :**

* **Autorisations des dossiers** - Placez les rapports dans des dossiers disposant des droits d’accès en lecture/écriture appropriés pour les groupes d’utilisateurs
* **Droits nommés** - Attribuez des droits spécifiques pour afficher, créer ou modifier des rapports
* **Contexte d’affichage** - Définissez l’emplacement d’affichage des rapports : dans le dossier **[!UICONTROL Rapports]**, les onglets de campagne ou les écrans de diffusion
* **Partage de l’interface utilisateur web** - Partagez des liens de tableau de bord avec les membres de l’équipe via l’interface utilisateur web de Campaign

**Configuration de l’accès :**

1. Enregistrer le rapport dans un dossier spécifique de la console cliente
2. Configuration des autorisations d’accès aux dossiers pour les groupes d’opérateurs appropriés
3. Définir les propriétés du rapport : type de rapport, contexte d’affichage et disponibilité
4. Tester l’accès avec un utilisateur du groupe cible avant un déploiement plus large

**Bonne pratique :** créez des dossiers de rapports dédiés pour différentes équipes (marketing, opérations, gestion) avec des autorisations d’accès personnalisées. Objectif du rapport de document et plannings d’actualisation.

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

[&#x200B; Rapports personnalisés &#x200B;](../reporting/custom-reports.md) | [Rapports de l’interface utilisateur web de Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}

+++

## Développeurs {#developers}

Accédez aux informations techniques destinées aux développeurs, notamment les détails du modèle de données, les schémas, les API et les fonctionnalités de personnalisation.

+++ Quel est le modèle de données de Campaign ? 

Le modèle de données de Campaign est une structure de base de données relationnelle pilotée par un schéma qui définit la manière dont les données marketing sont organisées et associées. Elle se compose de tableaux intégrés pour les objets marketing principaux (destinataires, diffusions, campagnes) et peut être étendue pour répondre aux besoins spécifiques de votre entreprise.

**Concepts clés du modèle de données :**

* **Schémas** - Définitions XML décrivant la structure, les champs et les relations des tableaux
* **Tables intégrées** - Entités marketing principales (destinataires, diffusions, workflows, campagnes)
* **Liens** - Relations entre les tables (1-1, 1-N, N-N)
* **Énumérations** - Listes de valeurs prédéfinies pour les champs de liste déroulante
* **Extensions** - Champs et tableaux personnalisés ajoutés au modèle standard

**Principaux schémas intégrés :**

* **Destinataire (nms:recipient)** - Profils client et coordonnées
* **Diffusion (nms:delivery)** campagnes par e-mail, SMS et push
* **Workflow (xtk:workflow)** - Processus d’automatisation
* **Campaign (nms:operation)** - Orchestration des campagnes marketing
* **Logs de tracking** - Ouvertures, clics et données d’engagement

**Pourquoi est-ce important** comprendre le modèle de données est essentiel pour créer des workflows, créer des requêtes, étendre les schémas et développer des intégrations personnalisées. L’approche basée sur un schéma assure la cohérence des données et permet des fonctionnalités d’interrogation puissantes.

[Modèle de données de Campaign](../dev/datamodel.md) | [Bonnes pratiques relatives au modèle de données](../dev/datamodel-best-practices.md)

+++

+++ Comment utiliser des schémas de Campaign ?

Les schémas sont la base de la structure des données de Campaign. Ils définissent les tables, les champs et les relations au format XML. La compréhension des schémas est essentielle pour la personnalisation, l’intégration et le développement avancé des workflows.

**Ce que les schémas définissent :**

* **Structure des tables** - Tables de base de données et objets d&#39;application correspondants
* **Propriétés du champ** - Types de données, libellés, règles de validation et valeurs par défaut
* **Relations** - Liens entre les tables (jointures) et la cardinalité
* **Index** - Optimisation de la base de données pour les performances des requêtes
* **Contrôle d’accès** - Quels champs les utilisateurs peuvent afficher et modifier

**Utilisation des schémas :**

* **Afficher les schémas :** accès via **[!UICONTROL Administration > Configuration > Schémas de données]** dans la console cliente
* **Étendre les schémas :** créez des schémas d’extension (par exemple, `cus:recipient` étend les `nms:recipient`) pour ajouter des champs personnalisés sans modifier les schémas principaux
* **Créer des schémas personnalisés :** créez des tables entièrement nouvelles pour les données spécifiques à l’entreprise
* **Mettre à jour la base de données :** appliquer des modifications de schéma à l’aide de **[!UICONTROL Outils > Avancé > Mettre à jour la structure de la base de données]**

**Cas d’utilisation courants :**

* Ajout de champs personnalisés à la table des destinataires (identifiant de société, niveau de fidélité, préférences)
* Création de tables personnalisées pour les produits, les magasins ou les transactions
* Définir les relations entre les tables personnalisées et intégrées
* Mise en œuvre de modèles de données spécifiques à l’entreprise

**Important :** ne modifiez jamais directement les schémas prédéfinis. Utilisez toujours des schémas d’extension pour préserver la compatibilité de mise à niveau et la prise en charge d’Adobe.

[Prise en main des schémas](../dev/schemas.md) | [Étendre un schéma](../dev/extend-schema.md)

+++

+++ Comment utiliser une table de destinataires personnalisée ?

Campaign vous permet d’utiliser une table personnalisée au lieu de la table des destinataires intégrée lorsque votre entreprise a besoin d’une structure de données différente pour le ciblage (par exemple, comptes B2B, abonnés, prospects ou contacts externes).

**Pourquoi utiliser une table de destinataires personnalisée**

* Cibler les entreprises ou les entités organisationnelles B2B plutôt que les contacts individuels
* Séparer les données d’abonné de la base de données client principale
* Utiliser une table des clients existante d’un autre système
* Implémenter des architectures multi-marques avec des tables de contact distinctes
* Respecter les exigences spécifiques en matière de gouvernance des données

**Étapes d’implémentation :**

1. Créez votre schéma personnalisé définissant la structure de la table des destinataires
2. Inclure les champs obligatoires (email, clé primaire, indicateurs d&#39;exclusion)
3. Configuration des mappings de ciblage pour lier votre table aux diffusions
4. Mettre à jour les modèles de diffusion pour utiliser le nouveau mapping de ciblage
5. Adapter les workflows et les requêtes pour référencer la table personnalisée

**Considérations principales :**

* Les tables de destinataires personnalisées doivent inclure les champs obligatoires pour les diffusions (e-mail, exclusions, tracking)
* Les workflows et les formulaires doivent être adaptés pour fonctionner avec la structure personnalisée
* Certaines fonctionnalités intégrées peuvent nécessiter une personnalisation
* Les tests sont essentiels avant la migration des campagnes de production

**Bonne pratique :** commencez par étendre la table des destinataires standard avant de considérer une table personnalisée. Les tableaux de destinataires personnalisés ajoutent de la complexité et ne doivent être utilisés que lorsque cela est vraiment nécessaire.

[Table des destinataires personnalisée](../dev/custom-recipient.md) | [Mappings de ciblage](../audiences/target-mappings.md)

+++

+++ Quelles sont les bonnes pratiques pour définir des requêtes dans Campaign ? 

Le requêteur de Campaign est un puissant outil visuel permettant de créer des requêtes de base de données sans connaissances SQL. Sa maîtrise est essentielle pour un ciblage, une segmentation et une analyse des données efficaces.

**Où les requêtes sont utilisées :**

* **Activités de workflow** - Activités de requête, de partage, de mise à jour de données, d’enrichissement
* **Ciblage des diffusions** - Définissez les populations de destinataires pour les campagnes
* **Listes** - Créez des listes de destinataires dynamiques ou statiques
* **Rapports** - Créer des extractions et des analyses de données personnalisées
* **Filtres** - Créer des critères de ciblage réutilisables

**Bonnes pratiques relatives aux requêtes :**

* **Démarrer simplement** - Créez des requêtes de manière incrémentielle, en effectuant des tests à chaque étape.
* **Utiliser les dimensions de filtrage** - Tirer parti des relations entre les tables (destinataires → diffusions → logs de tracking)
* **Optimiser les performances** - Indexez les champs fréquemment interrogés et évitez les champs calculés complexes
* **Utilisation de filtres prédéfinis** - Réutilisez et combinez les filtres existants par souci de cohérence
* **Tester avec de petits échantillons** - Valider la logique de requête avant de l’exécuter sur une base de données complète
* **Documenter les requêtes complexes** - Ajouter des descriptions pour la maintenance et le transfert de connaissances

**Modèles de requête courants :**

* Cibler les destinataires ayant ouvert une diffusion spécifique : filtrer les logs de tracking associés aux destinataires
* Rechercher des contacts inactifs : Requête sur la dernière date de diffusion ou activité de tracking
* Segmenter par comportement : combiner les critères de diffusion, de tracking et de profil
* Exclure les destinataires précédents : utilisez des opérations de visionnage (union, intersection, exclusion)

**Accédez au requêteur générique :** **[!UICONTROL Outils > Requêteur générique]** pour l’exploration de bases de données ad hoc et l’extraction de données en dehors des workflows.

[Requêteur](../start/query-editor.md) | [Activité Requête dans les workflows](https://experienceleague.adobe.com/fr/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=fr){target="_blank"}

+++

+++ Comment importer un package de données ? 

Les packages de données vous permettent d’exporter et d’importer des configurations Campaign (schémas, workflows, typologies, filtres) et des données entre les instances. Cela est essentiel pour déployer des configurations du développement à la production ou pour partager des composants entre les organisations.

**Que peut-on empaqueter**

* **Objets de configuration** - Schémas, workflows, règles de typologie, formulaires, filtres
* **Composants de campagne** - Modèles de diffusion, modèles de campagne, blocs de contenu
* **Paramètres de l’application** - Opérateurs, groupes d’opérateurs, structures de dossiers
* **Données** - Listes de destinataires, adresses de contrôle, fragments de contenu
* **Développements personnalisés** - Code JavaScript, scripts SQL, applications web


**Types de packages :**

* **Package utilisateur** - Configurations personnalisées que vous créez et exportez
* **Package plateforme** - fonctionnalités et mises à jour fournies par Adobe
* **Package de données** - Contient les enregistrements de données réels, pas seulement la structure

**Bonnes pratiques :**

* Exportez toujours des packages à partir de la même version ou d’une version antérieure de Campaign.
* Tester les imports de packages dans l’environnement de développement avant la production
* Contenu du package de document et dépendances
* Utiliser le contrôle de version pour les fichiers XML de package
* Sauvegarde de l’instance avant un import de package majeur

[Utiliser les packages de données](../dev/packages.md)

+++

+++ Où puis-je trouver la liste des API de Campaign v8 ?

Campaign v8 fournit une documentation d’API complète couvrant à la fois les API SOAP (pour les interactions de console cliente) et les API REST (pour les intégrations modernes). La référence de l’API inclut toutes les méthodes, tous les paramètres et tous les formats de réponse disponibles.

**Types d’API Campaign :**

* **API SOAP** - API traditionnelles pour les opérations de la console cliente Campaign, la manipulation de schémas et le contrôle des workflows
* **API REST** - Des API HTTP modernes pour les intégrations de systèmes externes, la gestion des profils et le déclenchement d’événements
* **API JavaScript** - API de script côté serveur pour les activités de workflow et la logique commerciale personnalisée

**Ressources de documentation de l’API :**

* **Référence d’API complète :** documentation complète sur l’API SOAP avec des signatures de méthode, des paramètres et des exemples
* **Guide de l’API REST :** points d’entrée REST modernes pour les profils, les événements et les entités organisationnelles
* **API JavaScript :** fonctions côté serveur disponibles dans les scripts de workflow et les applications web

**Cas d’utilisation courants des API :**

* Intégrer Campaign à des applications CRM, ERP ou personnalisées
* Automatisation des opérations de campagne et de l&#39;exécution des workflows
* Synchronisation des données entre les systèmes en temps réel
* Créer des solutions personnalisées de surveillance et d’alerte
* Créer des interfaces externes pour les données et les opérations de Campaign

**Accès :** [Documentation de l’API Campaign v8](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=fr){target="_blank"}

+++


+++ Comment surveiller les workflows à partir de l’API ?

Les API Campaign vous permettent de contrôler et de surveiller par programmation l’exécution des workflows, en activant des systèmes de surveillance externes, des alertes automatisées et des solutions d’orchestration personnalisées.

**Que faire avec l’API :**

* **Démarrer les workflows** - Déclenchez l’exécution des workflows par programmation.
* **Suspendre/reprendre les workflows** - Contrôler le flux d’exécution des workflows
* **Arrêter les workflows** - Arrêter les workflows en cours d’exécution
* **Statut du workflow de requête** - Vérifiez si les workflows sont en cours d’exécution, en pause ou terminés
* **Récupérer les journaux** - Accédez aux journaux d’exécution des workflows et aux messages d’erreur
* **Surveiller la progression des activités** - Suivre la fin d’une activité de workflow individuelle

**Méthodes d’API :**

* `xtk:workflow#Start` - Démarrer une instance de workflow
* `xtk:workflow#Pause` - Suspendre le workflow en cours d’exécution
* `xtk:workflow#Stop` - Arrêter l’exécution du workflow
* `xtk:workflow#GetState` - Obtention de l’état actuel du workflow
* `xtk:workflow#GetLogs` - Récupération des journaux d’exécution

**Cas d’utilisation courants :**

* Créer des tableaux de bord de surveillance personnalisés affichant l’intégrité des workflows
* Mise en œuvre d’alertes automatisées en cas d’échec ou d’exécution trop long des workflows
* Orchestrer des workflows à partir de planificateurs ou de systèmes d’événements externes
* Création de dépendances de workflow sur plusieurs instances Campaign
* Génération de rapports d’exécution de workflow personnalisés

**Bonne pratique :** combinez la surveillance des API avec le journal d’audit des workflows pour une gouvernance complète des workflows. Utilisez des outils de surveillance externes pour effectuer le suivi des SLA de workflow et des mesures de performances.

[Workflows de contrôle via l’API](../dev/api/controlling-a-workflow.md)

+++

+++ Comment mettre à jour la structure de la base de données ?

Après avoir modifié les schémas Campaign (ajout de champs, création de tables, modification des types de données), vous devez mettre à jour la structure physique de la base de données pour appliquer vos modifications. Cette synchronisation garantit que la base de données correspond à vos définitions de schéma.

**Lorsque des mises à jour de la base de données sont nécessaires :**

* Ajout de nouveaux champs aux schémas existants
* Création de tables personnalisées ou extension de tables intégrées
* Modification des propriétés du champ (type de données, longueur, statut requis)
* Ajouter ou supprimer des liens entre les tables
* Création d’index pour l’optimisation des requêtes


**Considérations importantes :**

* **Sauvegarder d’abord** - Sauvegardez toujours votre base de données avant d’apporter des modifications structurelles
* **Test en développement** - Validation des modifications de schéma dans l’environnement de développement avant la production.
* **Planification des temps d’arrêt** - Les modifications structurelles importantes peuvent nécessiter de brèves périodes de maintenance
* **Pour Managed Cloud Services** - Coordonnez les modifications majeures avec l’assistance Adobe
* **Réversibilité** - Certaines modifications (telles que la suppression de champs) peuvent entraîner une perte de données

**Bonne pratique :** utilisez le contrôle de version des schémas et le suivi des modifications. Documentez toutes les modifications de schéma personnalisé à des fins de maintenance et de dépannage.

[Mettre à jour la structure de la base de données](../dev/update-database-structure.md) | [Étendre le schéma](../dev/extend-schema.md)

+++

+++ Quelles sont les limites de Campaign v8 ?

Campaign v8 introduit des changements architecturaux (en particulier dans les déploiements FFDA) qui apportent des améliorations significatives des performances, mais aussi certaines différences par rapport à Campaign Classic v7. La compréhension de ces éléments permet de planifier les migrations et de définir des attentes appropriées.

**Principales considérations relatives à v8 :**

* **Architecture FFDA** - Les déploiements d’entreprise utilisent la base de données cloud (Snowflake) avec différents modèles d’accès aux données
* **Mises à jour unitaires** - Les mises à jour de données doivent être effectuées dans les workflows, et non via des API ou un accès direct à la base de données
* **Écritures en temps réel** - Optimisé pour les opérations par lots plutôt que pour les mises à jour individuelles haute fréquence
* **Modèle de données** - Certaines personnalisations de schéma nécessitent des approches différentes
* **Accès à une base de données externe** - La configuration FDA (Federated Data Access) diffère de la v7

**Fonctionnalités non disponibles dans les déploiements FFDA :**

* Questionnaires (disponibles dans les déploiements v8 standard)
* Marketing Resource Management (MRM)
* Certaines configurations de connecteur spécifiques

**Considérations relatives à la migration :**

* Le code personnalisé utilisant des écritures de base de données directes nécessite une refactorisation
* Les intégrations d’API peuvent nécessiter une adaptation pour le traitement par lots
* Les workflows doivent suivre les bonnes pratiques FFDA pour les opérations de données
* Les tests sont essentiels pour valider les développements personnalisés

**Important :** ces restrictions évoluent à mesure qu’Adobe continue d’améliorer v8. Consultez la documentation la plus récente pour connaître le statut et la feuille de route actuels.

[Migration de Campaign v7 vers v8](../start/v7-to-v8.md#limitations) | [Architecture FFDA](../architecture/enterprise-deployment.md)

+++

## Confidentialité {#privacy}

Découvrez comment Adobe Campaign vous aide à vous conformer aux réglementations de confidentialité comme le RGPD et le CCPA, et à gérer les demandes des titulaires de données.

+++ Quels sont les concepts clés de la confidentialité dans Campaign ?

Campaign vous aide à vous conformer aux règlements sur la confidentialité (RGPD, CCPA, PDPA, LGPD) par le biais d’outils de gestion des droits des titulaires de données, du consentement et de la conservation des données. Les concepts clés incluent les réglementations de confidentialité, l’identification des données personnelles, les droits des titulaires de données (accès, suppression, portabilité), la gestion du consentement et les politiques de conservation des données.

En tant que contrôleur de données, vous êtes chargé de traiter les demandes des titulaires de données, de tenir à jour les enregistrements de consentement et d’assurer une utilisation transparente des données.

[Gestion de la confidentialité](../start/privacy.md)

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

[Gestion de la confidentialité](../start/privacy.md)

+++

+++ Comment dois-je collecter et gérer le consentement de l’utilisateur ?

Un consentement valide nécessite un accord actif, spécifique, éclairé et révocable. Les utilisateurs doivent prendre des mesures explicites : ne pas cocher de case et ne pas donner leur consentement. Séparer les consentements à différentes fins (dissociation), fournir des explications claires et conserver les enregistrements avec horodatage.

**Bonnes pratiques :** proposez des options de souscription granulaires, actualisez régulièrement le consentement, facilitez l’accès aux centres de préférences et définissez le consentement comme un élément de confiance.

Campaign propose des services d’abonnement, des centres de préférences, des champs de consentement personnalisés avec suivi de l’horodatage et une actualisation du consentement basée sur les workflows.

[Abonnements](../start/subscriptions.md) | [Confidentialité et consentement](../start/privacy.md#consent-retention-roles)

+++

+++ Comment mettre en œuvre la gestion du consentement dans Campaign ?

Campaign fournit des services d’abonnement, des centres de préférences, des indicateurs d’opt-out et des champs de consentement personnalisés pour le suivi du consentement.

**Approche d’implémentation** : étendez le schéma des destinataires pour les champs de consentement (date, type, source), créez des services d’abonnement pour chaque type de consentement, créez des formulaires web de centre de préférences, utilisez des workflows pour appliquer le consentement dans le ciblage et conservez les pistes d’audit.

Consultez le service juridique pour vous assurer que votre implémentation répond aux exigences réglementaires.

[Services d’abonnement](../start/subscriptions.md) | [&#x200B; Gestion de la confidentialité &#x200B;](../start/privacy.md)

+++

+++ Quelles données sont supprimées lorsque je traite une demande de suppression ?

Campaign supprime automatiquement toutes les données liées à un titulaire de données : le profil du destinataire, les logs de diffusion et de tracking, les données personnalisées avec les relations de propriété, l&#39;historique des abonnements et les données de tracking web.

**Fonctionnement :** Campaign supprime toutes les données pour lesquelles le lien vers le destinataire a `integrity="own"` dans la définition de schéma, assurant ainsi une suppression en cascade sur les tables associées.

Vous pouvez personnaliser la portée de la suppression en modifiant l’intégrité des liens dans les schémas, mais consultez d’abord un service juridique. La suppression est permanente et ne peut pas être annulée.

[&#x200B; Gestion de la confidentialité &#x200B;](../start/privacy.md) | [&#x200B; Liens de schéma &#x200B;](../dev/schemas.md)

+++

+++ Les suppressions d’informations personnelles affectent-elles mes rapports de diffusion ?

Non. Les rapports de campagne sont basés sur des mesures agrégées précalculées (total envoyé, ouvertures, clics), et non sur des requêtes actives sur des journaux individuels. La suppression des données de destinataires individuels ne modifie pas les statistiques agrégées historiques.

Les statistiques globales de diffusion et les mesures de performances restent intactes, tandis que les logs de tracking individuels et les détails personnels sont supprimés. Cela vous permet de gérer les analyses marketing tout en respectant les droits des titulaires de données.

[&#x200B; Gestion de la confidentialité &#x200B;](../start/privacy.md) | [Rapports](../reporting/gs-reporting.md)

+++

+++ Comment empêcher la réimportation des données supprimées ?

Vous devez supprimer des données de tous les systèmes sources, et pas seulement de Campaign. Les données proviennent souvent de systèmes externes (CRM, e-commerce, entrepôts de données).

**Actions requises :** identifier toutes les sources de données, les supprimer des systèmes sources, les ajouter aux listes d’exclusion/suppression, mettre à jour les workflows d’importation pour respecter les indicateurs de suppression et documenter le processus.

En tant que contrôleur de données, vous êtes responsable de la suppression complète des données dans l’ensemble de votre écosystème technologique.

[&#x200B; Gestion de la confidentialité &#x200B;](../start/privacy.md) | [Workflows d’import](../config/workflows.md)

+++

+++ Les utilisateurs supprimés peuvent-ils à nouveau s’inscrire ?

Oui. Les titulaires de données peuvent à nouveau donner leur accord après la suppression. Campaign crée un enregistrement de destinataire entièrement nouveau sans lien vers les données supprimées précédentes : le profil commence à zéro.

Le journal d&#39;audit de Campaign enregistre à la fois l&#39;événement de suppression et la création d&#39;un nouveau profil, démontrant la conformité et montrant que le nouveau processus d’opt-in a été librement consenti après la suppression.

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

* **[Page d’accueil de la documentation de Campaign v8](../campaign-home.md)** - Documentation complète du produit
* **[Tutoriels Campaign](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/overview.html?lang=fr){target="_blank"}** - Guides vidéo détaillés et tutoriels pratiques
* **[Nouveautés](whats-new.md)** - Dernières fonctionnalités
* **[Notes de mise à jour](release-notes.md)** - Informations sur les versions actuelle et précédente
* **[Versions et mises à niveau](upgrades.md)** - Découvrez les versions et mises à niveau de Campaign et comment vérifier votre version
* **[Bonnes pratiques](delivery-best-practices.md)** - Approches recommandées pour les tâches courantes

### Ressources techniques

Recherchez une documentation technique détaillée et des ressources pour les développeurs.

* **[API Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=fr){target="_blank"}** - Documentation complète de référence sur les API
* **[Campaign GitHub](https://github.com/AdobeDocs/campaign.fr-FR)** - Contribution à la documentation
* **[Notes techniques](https://experienceleague.adobe.com/fr/docs/campaign/technotes-ac/technotes-home){target="_blank"}** - Articles techniques détaillés
* **[Matrice de compatibilité](compatibility-matrix.md)** - Systèmes et versions pris en charge
* **[FAQ sur les versions et mises à niveau](upgrades.md#upgrades-faq)** - Vérifiez votre version et découvrez les mises à niveau

### Assistance et services

Obtenez de l’aide de l’équipe d’assistance Adobe et gérez votre instance.

* **[Adobe Admin Console](https://adminconsole.adobe.com/){target="_blank"}** - Consigner les cas d&#39;assistance et gérer les utilisateurs
* **[Assistance clientèle Adobe &#x200B;](https://helpx.adobe.com/fr/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}** - Contactez l’équipe d’assistance
* **[Panneau de Contrôle &#x200B;](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=fr){target="_blank"}** - Gérer les paramètres de votre instance Campaign
* **[Statut du système](https://status.adobe.com/){target="_blank"}** - Vérifiez le statut des services Adobe

### Formation et certification

Améliorez vos compétences grâce aux programmes de formation et de certification officiels d’Adobe.

* **[Adobe Digital Learning Services &#x200B;](https://learning.adobe.com/){target="_blank"}** - Cours officiels dispensés par un instructeur et à son propre rythme
* **[Certification Adobe Campaign &#x200B;](https://experienceleague.adobe.com/docs/certification/program/overview.html?lang=fr){target="_blank"}** - Validez votre expertise avec la certification professionnelle
* **[Parcours d’apprentissage Experience League &#x200B;](https://experienceleague.adobe.com/fr?lang=fr#dashboard/learning){target="_blank"}** - parcours d’apprentissage guidés

### Autres ressources utiles

* **[Documentation de Campaign Classic v7 &#x200B;](https://experienceleague.adobe.com/docs/campaign-classic/using/campaign-classic-home.html?lang=fr){target="_blank"}** - Référence pour les utilisateurs de Classic v7
* **[Documentation sur l’interface utilisateur web de Campaign](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/campaign-web-home){target="_blank"}** - Nouveau guide de l’interface web
* **[Bonnes pratiques en matière de délivrabilité](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=fr){target="_blank"}** - Optimisation de la diffusion e-mail
* **[Mises à jour de produits](https://experienceleague.adobe.com/fr/docs/release-notes/experience-cloud/current){target="_blank"}** - Dernières mises à jour de Adobe Experience Cloud

**Dernière mise à jour :** novembre 2025 | **S’applique à :** Campaign v8.6 et versions ultérieures

*Une erreur a été trouvée ou une amélioration doit être suggérée ? [Modifiez cette page sur GitHub](https://github.com/AdobeDocs/campaign.fr-FR/edit/main/help/v8/start/campaign-faq-comprehensive.md)*

