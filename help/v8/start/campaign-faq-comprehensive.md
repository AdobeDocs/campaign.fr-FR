---
title: Questions fréquentes sur Campaign v8
description: Obtenez des réponses aux questions courantes d’Adobe Campaign v8 sur l’installation, la configuration, la messagerie, les workflows, etc
feature: Overview
role: User
level: Beginner
keywords: FAQ, Campaign v8, questions, réponses, aide, support, dépannage
hide: true
hidefromtoc: true
source-git-commit: 09911f7112a89b2cc5235b71bbcaa963ae739aed
workflow-type: tm+mt
source-wordcount: '9728'
ht-degree: 28%

---

# Questions fréquentes {#faq}

Obtenez des réponses rapides aux questions les plus courantes sur Adobe Campaign v8. Que vous débutiez ou que vous recherchiez une aide de configuration avancée, vous trouverez des réponses organisées par sujet ci-dessous.

**Vous découvrez Campaign ?** par [questions générales](#general) et [concepts clés](#key-concepts).\
**Besoin d’aide technique ?** vérifier [développeurs](#developers) et [paramètres de Campaign](#settings).\
**Vous ne trouvez pas la réponse ?** Visitez notre [Forums communautaires](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community?profile.language=fr){target="_blank"} ou [contactez l’assistance](#get-help).

>[!TIP]
>
>Utilisez Ctrl+F (Cmd+F sur Mac) pour rechercher des mots-clés spécifiques sur cette page. Cliquez sur une question pour développer la réponse.


## Questions générales {#general}

Obtenez des réponses aux questions les plus fréquentes sur Adobe Campaign v8, y compris sur la connexion, la mise à niveau et l’assistance.

+++ Comment se connecter à Campaign v8 ?

Vous devez télécharger et installer la console cliente Campaign pour vous connecter à Adobe Campaign.

[Pour en savoir plus, cliquez ici](connect.md).

À compter de la version 8.6 de Campaign, vous avez accès à l’**interface utilisateur web de Campaign**, disponible via l’environnement Adobe Experience Cloud central. Experience Cloud est une famille intégrée d’applications, de produits et de services de marketing numérique d’Adobe.

Découvrez comment vous connecter à Adobe Experience Cloud et accéder à l’interface d’Adobe Campaign Web [dans cette page](campaign-ui.md#ac-web-ui).

Pour en savoir plus, consultez la [documentation sur l’interface d’utilisation d’Adobe Campaign Web](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/campaign-web-home){target="_blank"}.

>[!TIP]
>
>**Résolution des problèmes de connexion :**
>
>* Vérification de l’exactitude de vos informations d’identification Adobe ID
>* Vérifiez que la version de la console cliente correspond à celle du serveur.
>* Vérifier les paramètres de connectivité réseau et de pare-feu
>* Effacer le cache de la console cliente en cas de problème
>* Contactez votre administrateur pour vérifier vos autorisations utilisateur

**Rubriques connexes :**

* [Installer la console cliente](connect.md)
* [Interface utilisateur de Campaign](campaign-ui.md)
* [Autorisations utilisateur](gs-permissions.md)

+++

+++ Campaign v8 peut-il être installé dans un environnement on-premise ou hybride ?

Campaign v8 n’est disponible que dans Managed Cloud Services, entièrement hébergé par Adobe.

+++

+++ Comment effectuer une mise à niveau de Campaign vers la dernière version ?

Adobe Campaign fait l’objet de mises à jour régulières. Des versions mineures sont publiées chaque année avec de nouvelles fonctionnalités, des améliorations et des correctifs. En outre, nous publions périodiquement des builds avec des correctifs cumulatifs uniquement.

Cette fréquence régulière de mise à jour a pour but de vous fournir les dernières fonctionnalités et améliorations. Vous bénéficiez ainsi d&#39;un environnement sécurisé et d&#39;une expérience optimale avec notre produit. C’est la raison pour laquelle nous pensons qu’il est important que vous exécutiez la version la plus récente d’Adobe Campaign.

>[!NOTE]
>
>En tant qu’utilisateur Managed Cloud Services, votre instance est mise à niveau par Adobe avec de nouvelles versions.

+++

+++ Comment améliorer la délivrabilité des e-mails ?

La délivrabilité des e-mails, composant essentiel de la réussite du programme marketing de chaque expéditeur, est caractérisée par des critères et des règles en constante évolution. Pour naviguer efficacement dans ce monde numérique, il est nécessaire d&#39;affiner régulièrement votre stratégie d&#39;e-mail, en tenant compte des principales tendances de délivrabilité, afin d&#39;atteindre au mieux vos audiences.

Consultez ce guide pour découvrir [bonnes pratiques en matière de délivrabilité](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=fr){target="_blank"}

Découvrir comment implémenter la délivrabilité dans Campaign [dans ce guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html?lang=fr){target="_blank"}

>[!TIP]
>
>**Principaux conseils en matière de délivrabilité :**
>
>* Tenez à jour une liste d’adresses électroniques nettoyée et supprimez régulièrement les abonnés inactifs
>* Utiliser le double opt-in pour s&#39;assurer que les destinataires engagés
>* Surveiller la réputation de votre expéditeur et de votre adresse IP
>* Authentifier vos e-mails avec SPF, DKIM et DMARC
>* Respecter immédiatement les demandes de désabonnement
>* Tester vos e-mails avant l’envoi à des audiences importantes

**Rubriques connexes :**

* [À propos de la délivrabilité](../send/about-deliverability.md)
* [Contrôler le contenu du message](../send/control-message-content.md)
* [Surveillance de la délivrabilité](../send/monitoring-deliverability.md)
* [SpamAssassin](../send/spamassassin.md)

+++

+++ Comment puis-je m’assurer que ma diffusion est envoyée sans erreur ?

Adobe Campaign contient un ensemble de tableaux de bord et d’outils qui permettent de surveiller vos diffusions E-mail.

[Consultez la documentation Campaign Classic v7 pour découvrir](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=fr){target="_blank"} comment vous assurer que vos messages sont bien envoyés, surveiller l’exécution et entreprendre une action en cas d’erreur.

+++

+++ Est-il possible de surveiller l’exécution des workflows ?

Découvrez comment surveiller l’exécution des workflows Campaign sur [cette page](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution){target="_blank"}.

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

Vérifiez les [numéros de version et de build](connect.md#ac-version) depuis le menu **Aide > A propos...** de la console cliente de Campaign.

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
* [Bonnes pratiques de diffusion ](delivery-best-practices.md) - Recommandations pour réussir
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

Découvrez les principales différences entre Campaign v8 et les versions précédentes (Classic v7 et Standard), notamment l’architecture, le déploiement, les chemins de migration et les modifications de fonctionnalités.

+++ Quelles sont les principales différences entre Campaign v8 et les versions précédentes ?

Campaign v8 est une refonte complète d’Adobe Campaign, conçue pour une architecture moderne native cloud, qui apporte des améliorations significatives par rapport à Campaign Classic v7 et à Campaign Standard :

**Modèle de déploiement :**

* **v8:** Managed Cloud Services uniquement : entièrement hébergé et géré par Adobe
* **v7/Standard :** options On-premise, hybrides ou hébergées disponibles
* **Avantage :** zéro gestion de l’infrastructure, mise à l’échelle automatique, sécurité de niveau entreprise

**Architecture et performances :**

* Architecture Full FDA (FFDA) améliorée **v8:** avec la base de données PostgreSQL
* **v8:** Optimisé pour la gestion de millions de profils et l’envoi de gros volumes
* **v8:** Amélioration significative des performances des requêtes et de la vitesse de traitement des données
* **Bénéfice :** de meilleures performances pour les opérations à grande échelle et les campagnes complexes

**Interface utilisateur :**

* **v8:** Nouvelle interface utilisateur web de Campaign avec la console cliente
* **v8:** Conception moderne et réactive avec une expérience utilisateur améliorée
* **v8:** Workflows simplifiés de création et de gestion de campagnes
* **Avantage :** intégration plus rapide, exécution plus facile des campagnes, meilleure accessibilité

**Mises à niveau et maintenance :**

* **v8:** Mises à niveau automatiques gérées par Adobe - Toujours sur la dernière version stable
* **v7 :** planification et exécution manuelles de la mise à niveau requises
* **Avantage :** charge de maintenance réduite, accès immédiat aux nouvelles fonctionnalités, pas de temps d’arrêt

**API et intégration :**

* API REST **v8:** modernes avec des performances et une fiabilité améliorées
* Intégration transparente de **v8:** avec les solutions Adobe Experience Cloud
* **Avantage :** intégrations plus faciles, meilleure interopérabilité, pratiques de développement modernes

[En savoir plus sur les fonctionnalités clés de Campaign v8](whats-new.md)

**Rubriques connexes :**

* [De Campaign Classic v7 à v8](v7-to-v8.md)
* [De Campaign Standard à v8](acs-to-v8.md)
* [Architecture de Campaign v8](../architecture/architecture.md)
* [Mécanismes de sécurisation et limitations](ac-guardrails.md)

+++

+++ Dois-je migrer de Campaign Classic v7 ou Campaign Standard vers v8 ?

**Campaign v8 est idéal pour les organisations qui ont besoin de :**

* **Campagnes à volume élevé** - Envoyez des millions de messages avec des performances et une fiabilité améliorées
* **Évolutivité d’entreprise** - Développez votre base de données et vos campagnes sans souci de performances
* **Interface utilisateur web moderne** - Interface utilisateur web intuitive et réactive de Campaign pour accélérer la création de campagnes et améliorer l’expérience utilisateur
* **Avantages natifs du cloud** - Tirez parti des mises à jour automatiques, de l’infrastructure gérée et d’une évolutivité élastique
* **Prise en charge à long terme** - Campaign v8 est une plateforme stratégique d’Adobe avec une prise en charge étendue. Les versions précédentes atteindront la fin de la prise en charge dans les années à venir
* **Réduction des frais généraux informatiques** - Élimination de la gestion de l’infrastructure et planification des mises à niveau

**Quand envisager une migration :**

* Votre instance Campaign actuelle gère d’importants volumes de données (des millions de profils)
* Vous rencontrez des problèmes de performances avec les workflows ou le ciblage complexes
* Vous voulez réduire les coûts de gestion et d&#39;entretien de l&#39;infrastructure
* Vous avez besoin d’une intégration transparente à d’autres solutions Adobe Experience Cloud
* De toute façon, vous prévoyez une mise à niveau ou une actualisation majeure de l’infrastructure
* **Vous souhaitez une technologie à l’épreuve du temps** - Campaign Classic v7 et Campaign Standard arriveront en fin de prise en charge, ce qui fera de v8 la solution stratégique à long terme
* **Votre équipe a besoin d’une interface moderne** - La nouvelle interface utilisateur web de Campaign offre une expérience plus intuitive et accessible aux marketeurs

**Considérations relatives à la migration :**

* La migration automatisée n’est pas encore disponible - Adobe fournit une assistance et des conseils en matière de migration
* v8 est Managed Cloud Service uniquement (aucun déploiement on-premise ou hybride)
* Certaines implémentations techniques peuvent différer de la v7. Consultez la [ matrice de compatibilité ](compatibility-matrix.md)
* La migration et le test des données nécessitent une planification et des ressources

**Étapes suivantes :**
Contactez votre représentant Adobe pour :

* Évaluation de la préparation et du calendrier de votre migration
* Comprendre les avantages spécifiques à votre cas d’utilisation
* Planifier la stratégie de migration et l’allocation des ressources
* Accéder aux outils et au support de migration

**Rubriques connexes :**

* [De Campaign Classic v7 vers v8](v7-to-v8.md) - Guide détaillé de comparaison et de migration pour les utilisateurs de la v7
* [De Campaign Standard vers v8](acs-to-v8.md) - Chemin de migration pour les utilisateurs standard
* [Matrice des fonctionnalités de Campaign v8](../start/compatibility-matrix.md)

+++

+++ Quelles sont les fonctionnalités de Campaign Classic v7 différentes ou non disponibles dans v8 ?

Campaign v8 offre la plupart des fonctionnalités de Campaign Classic v7 avec des améliorations, mais certaines fonctionnalités ont été modifiées en raison de l’architecture native au cloud :

**Non disponible dans v8:**

* **Déploiements On-premise et hybrides** - v8 est Managed Cloud Services uniquement
* **Accès direct à la base de données** - Utilisez plutôt les API et les outils fournis
* **Infrastructure gérée par le client** - Adobe gère l’ensemble de l’infrastructure

**Différentes implémentations dans v8:**

* **Workflows techniques** - Certains optimisés pour l’architecture cloud peuvent fonctionner différemment
* **Structure de la base de données** - L’architecture FFDA améliorée peut nécessiter des adaptations de schéma
* **Intégrations personnalisées** - Peut nécessiter des mises à jour pour l’architecture cloud
* **Personnalisations de bas niveau** - Certaines nécessitent des approches différentes dans l’environnement géré

**amélioré ou remplacé dans v8:**

* **Mises à niveau de build** - Désormais automatique (géré par Adobe) au lieu d’être manuel
* **Réglage des performances** - Géré par l’optimisation de l’infrastructure Adobe
* **Correctifs de sécurité** - Appliqués automatiquement par Adobe
* **Sauvegarde et récupération** - Géré par Adobe dans le cadre du service


**Important :** la plupart des fonctionnalités marketing et opérationnelles sont disponibles et améliorées dans v8. Les fonctionnalités techniques et au niveau de l’infrastructure sont gérées par Adobe dans l’environnement cloud.

[Consultez la matrice de compatibilité complète](compatibility-matrix.md) pour plus d’informations.

**Rubriques connexes :**

* [Mécanismes de sécurisation](ac-guardrails.md)
* [guide de transition de v7 vers v8](v7-to-v8.md)

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

>[!TIP]
>
>Utilisez des workflows pour les listes nécessitant des mises à jour régulières et une création manuelle pour la segmentation ponctuelle.

[Créer des audiences](../audiences/create-audiences.md) | [Activité de mise à jour de liste](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/list-update.html){target="_blank"}

+++

+++ Comment dédupliquer une population avant d&#39;envoyer un message ?

Utilisez l&#39;activité **[!UICONTROL Déduplication]** dans un workflow pour supprimer les destinataires en double avant la diffusion. Placez-le entre vos activités **[!UICONTROL Requête]** et **[!UICONTROL Diffusion]**, puis choisissez vos critères de déduplication (généralement l&#39;adresse e-mail ou l&#39;identifiant du destinataire) et l&#39;enregistrement à conserver.

>[!TIP]
>
>Effectuez toujours une déduplication avant l’envoi afin de vous assurer que chaque personne ne reçoit votre message qu’une seule fois.

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

[Activité d’exclusion](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/exclusion.html){target="_blank"}

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

[Guide de conception des emails](../send/email.md) | [ Bonnes pratiques de diffusion ](delivery-best-practices.md)

+++

+++ Qu’est-ce qu&#39;un modèle de diffusion ? 

Un modèle de diffusion est une diffusion préconfigurée qui enregistre tous les paramètres et paramètres en vue de les réutiliser dans plusieurs campagnes. Les modèles comprennent les règles de la cible, la conception du contenu, la personnalisation, les paramètres techniques (expéditeur, destinataire) et les règles de typologie. Créez-en une et réutilisez-la pour maintenir la cohérence et accélérer la création de campagnes.

[Création de modèles de diffusion](../send/create-templates.md)

+++

+++ Est-il possible d&#39;importer facilement du contenu HTML existant pour créer un email dans Campaign ? 

Oui. Importez du contenu HTML par copier/coller direct dans l’éditeur de contenu, par chargement de fichier à partir de votre ordinateur ou par chargement à partir d’une URL. Assurez-vous que votre HTML utilise du code compatible avec les e-mails (HTML 4.0/XHTML) avec le CSS intégré et hébergez les images sur un serveur public. Campaign ajoute automatiquement la personnalisation et le tracking aux HTML importées.

>[!TIP]
>
>Pour une expérience de conception d’e-mail optimale, utilisez le **Designer d’e-mail** dans l’interface utilisateur web de Campaign, qui offre des fonctionnalités modernes de glisser-déposer et des modèles réactifs intégrés, plutôt que d’importer des données HTML brutes.

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

Guide de [Personalization](../send/personalize.md) | [ Champs de personnalisation ](../send/personalization-fields.md) | [Contenu conditionnel](../send/conditions.md)

+++

+++ Puis-je envoyer des messages multilingues ? 

Oui. Campaign v8 offre des fonctionnalités multilingues. L’approche la plus simple est celle de l’**interface utilisateur web de Campaign**. L’interface utilisateur web offre une diffusion multilingue native avec des variantes de langue : ajoutez des variantes de langue à votre diffusion et Campaign envoie automatiquement la version appropriée en fonction de la langue préférée du destinataire. Disponible pour les e-mails, notifications push, SMS et messages transactionnels.

Fonctionnalités clés : duplication automatique du contenu, envoi automatique basé sur la langue, basculement de la langue par défaut et gestion facile des variantes.

La console cliente prend également en charge le contenu multilingue à l’aide de contenu et de workflows conditionnels, mais nécessite une configuration plus manuelle.

[Diffusions multilingues (interface utilisateur web)](https://experienceleague.adobe.com/en/docs/campaign-web/v8/msg/multilingual){target="_blank"} | [Contenu conditionnel (console cliente)](../send/conditions.md)

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

>[!NOTE]
>
>L’assistant AI est disponible exclusivement dans l’interface utilisateur web de Campaign et ne prend actuellement en charge que l’anglais. Les utilisateurs ont besoin des autorisations appropriées et doivent accepter un contrat d’utilisation.

[Présentation de l’assistant AI](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-gs){target="_blank"} | [Cas d’utilisation de l’assistant AI](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/generative-uc){target="_blank"} | [Alignement des marques](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/ai-assistant/ai-assistant/brands-score){target="_blank"}

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

[ Guide des adresses de contrôle ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/action-activities/delivery-control.html){target="_blank"}

+++

+++ Comment configurer un processus de validation avant l&#39;envoi des messages ?

Campaign fournit des workflows de validation pour s’assurer que les messages répondent aux normes de qualité avant envoi. Configurez les validations du contenu, de la cible, de l’extraction (publipostage direct) et du budget au niveau de la campagne ou de la diffusion.

**Configuration:**

Créez des groupes d’opérateurs dans **[!UICONTROL Administration > Gestion des accès > Groupes d’opérateurs]**, puis affectez des groupes de validation dans les propriétés de la campagne ou de la diffusion. Campaign envoie des e-mails de notification aux réviseurs qui peuvent approuver, rejeter ou demander des modifications.

**Pour les diffusions autonomes (hors campagne) :**

Utilisez les **BAT comme processus d’approbation**. Envoyez des BAT à votre groupe d’approbation pour validation et envoyez toujours un nouveau BAT après avoir apporté des modifications pour vous assurer que les parties prenantes examinent la dernière version.

[ Validation de la diffusion ](../send/preview-and-proof.md) | [Validations de campagne](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=fr){target="_blank"}

+++

+++ Qu&#39;est-ce qu&#39;une règle de typologie ?

Les règles de typologie sont une logique commerciale automatisée appliquée lors de l’analyse de la diffusion pour valider et optimiser l’envoi des messages. Ils assurent la conformité aux politiques marketing, protègent la délivrabilité et évitent la fatigue des clients.

**Principaux types de règle :**

* placer sur la liste bloquée **Règles de filtrage** - Exclure les destinataires (inscrits, désabonnés, mis en quarantaine)
* **Règles de pression** - Contrôlez la fréquence des messages pour éviter de surcharger les destinataires
* **Règles de capacité** - Limite le volume de messages pour les limites de capacité de traitement ou de FAI.
* **Règles de contrôle** - Vérifier la validité du message (objet, lien de désabonnement, format de l’expéditeur)

Les règles sont regroupées en typologies et appliquées lors de l&#39;analyse de la diffusion. Campaign peut exclure des destinataires, bloquer la diffusion ou générer des avertissements en fonction des règles.

[ Guide des règles de typologie ](https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=fr){target="_blank"}

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


>[!TIP]
>
>Utilisez l’interface utilisateur web de Campaign pour accélérer la création d’e-mails et la rendre plus intuitive avec des outils de conception modernes. Utilisez la console cliente pour des campagnes complexes de ciblage ou basées sur des workflows avancés.

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

[ Guide de suivi des liens ](../start/tracking.md) | [Bonnes pratiques de tracking](../send/send.md)

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

>[!TIP]
>
>Surveillez régulièrement votre liste de quarantaine. L&#39;augmentation des taux de quarantaine signale souvent des problèmes de qualité des données qui nécessitent une attention particulière avant d&#39;affecter la réputation de l&#39;expéditeur.

[ Guide de gestion des quarantaines ](../send/quarantines.md) | [Gestion des bounces](../send/delivery-failures.md)

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

* [ Guide des bonnes pratiques relatives aux workflows ](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/workflow-best-practices.html?lang=fr){target="_blank"}
* [Création d’un workflow](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/build-a-workflow.html?lang=fr){target="_blank"}
* [Surveiller les workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=fr){target="_blank"}

+++

## Paramètres de la campagne {#settings}

Configurez votre instance Campaign avec les paramètres, intégrations et configurations appropriés pour optimiser vos opérations marketing.

+++ Puis-je changer la langue de l&#39;interface de Campaign ? 

La langue de la campagne est sélectionnée lors de la création de l’instance. Vous ne pouvez pas le modifier par la suite. Pour plus d’informations, consultez [cette section](../start/connect.md).

L’interface utilisateur d’Adobe Campaign est disponible dans plusieurs langues : anglais, français, allemand, japonais, etc. Notez que la console cliente et le serveur doivent être définis avec la même langue. Chaque instance Campaign ne peut s’exécuter que dans une seule langue.

Pour l&#39;anglais, lors de l&#39;installation de Campaign, vous pouvez sélectionner l&#39;anglais (États-Unis) ou l&#39;anglais (Royaume-Uni) : ils diffèrent selon les formats de date et d&#39;heure.

+++

+++ Puis-je utiliser Campaign v8 avec d’autres solutions Adobe ?

Vous pouvez combiner les fonctionnalités de diffusion et de gestion de campagnes avancées d&#39;Adobe Campaign avec un ensemble de solutions conçues pour vous aider à personnaliser l&#39;expérience de vos utilisateurs.

[Découvrez comment travailler avec d’autres solutions Adobe](../connect/integration.md) et [comment configurer IMS dans Campaign](../start/connect.md).

+++

+++ Comment configurer les fonctionnalités de tracking sur mon instance Campaign ? 

En tant qu’utilisateur expérimenté, vous pouvez configurer les fonctionnalités de tracking sur votre instance Campaign.

[En savoir plus](../start/tracking.md).

+++

+++ Comment configurer la délivrabilité des emails ? 

Outre le [Guide des bonnes pratiques en matière de délivrabilité d&#39;Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=fr){target="_blank"}, consultez les recommandations techniques en matière de délivrabilité pour comprendre comment configurer votre instance afin d&#39;optimiser les fonctionnalités de diffusion de Campaign.

[En savoir plus](../send/about-deliverability.md).

+++

+++ Comment mettre en place la validation du contenu ? 

Grâce à Campaign, vous pouvez mettre en place des processus de validation des principales étapes d’une campagne marketing, dans un mode collaboratif. Pour chaque opération, vous pouvez valider la cible de diffusion, le contenu et les coûts. Les opérateurs Adobe Campaign en charge de la validation peuvent être avertis par e-mail et peuvent accepter ou refuser la validation depuis la console ou via une connexion web.

[En savoir plus](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=fr){target="_blank"} et découvrez les étapes permettant d’implémenter la validation du contenu de vos diffusions dans Campaign.

+++

+++ Comment accéder aux données stockées dans une base de données externe ? 

Adobe Campaign propose l&#39;option Federated Data (FDA) Access afin d&#39;exploiter des informations stockées dans une ou plusieurs bases de données externes : vous pouvez accéder à des données externes sans modifier la structure des données d&#39;Adobe Campaign.

[En savoir plus](../connect/fda.md).

+++

+++ À quelles bases de données externes est-il possible de connecter Campaign ? 

Les bases de données externes compatibles avec Campaign via FDA (Federated Data Access) sont répertoriées dans la [matrice de compatibilité](compatibility-matrix.md).

+++

+++ Adobe Campaign peut-il s’intégrer aux systèmes CRM ?

Adobe Campaign propose différents connecteurs CRM pour relier votre plateforme Adobe Campaign à vos systèmes tiers. Ces connecteurs CRM permettent par exemple de synchroniser les contacts, les comptes, les commandes, les achats, etc. Ils facilitent l’intégration de votre application à vos différentes applications tierces et métiers.

Ces connecteurs permettent une intégration rapide et facile des données : Adobe Campaign fournit un assistant dédié à la collecte et à la sélection des tableaux disponibles dans le CRM. Cela garantit une synchronisation bidirectionnelle et permet de s&#39;assurer que les données sont à jour en tout temps, et ce, sur l&#39;ensemble des systèmes.

[En savoir plus](../connect/crm.md) sur la synchronisation de votre outil CRM avec Adobe Campaign.

+++

+++ Comment effacer le cache de la console cliente ?

Si vous rencontrez des problèmes, tels que la restitution incorrecte des nouveaux logos ou l’exportation incorrecte des données, vous devrez peut-être vider le cache de la console cliente.

Déconnectez-vous et fermez la console cliente. Accédez à l’emplacement suivant en fonction de votre système d’exploitation :

* Windows : `C:\Users\<Username>\AppData\Roaming\Neolane\NL_5\`
* MAC : `~/Library/Application Support/Neolane/NL_5/`

Supprimez les fichiers de configuration XML (en conservant les `nlclient_cnx.xml`), puis reconnectez-vous à la console cliente.

+++

+++ Puis-je configurer les paramètres de l’interface utilisateur ?

Oui, en tant qu’administrateur, vous pouvez personnaliser les paramètres de l’interface utilisateur de Campaign pour vos utilisateurs. [En savoir plus](../config/ui-settings.md).

+++

+++ Puis-je créer des champs et des tableaux personnalisés ?

Oui, Campaign v8 vous permet d’étendre le modèle de données avec des champs et des tables personnalisés. Découvrez comment [étendre les schémas](../dev/extend-schema.md).

+++

## Rapports {#reporting}

Obtenez des informations sur les fonctionnalités de reporting de Campaign, y compris les rapports intégrés, les rapports personnalisés et les outils d’analyse de données tels que les cubes.

+++ Comment créer de nouveaux rapports ?

En complément des rapports intégrés, Adobe Campaign permet de générer des rapports dans différents contextes et de répondre à des besoins variés.

Adobe Campaign n&#39;est pas un outil spécialisé dans le reporting : les rapports créés dans Adobe Campaign permettent principalement de visualiser des données agrégées.

[En savoir plus](../reporting/gs-reporting.md) sur les fonctionnalités de reporting de Campaign.

+++

+++ Comment concevoir et partager des rapports statistiques sur les populations ?

Adobe Campaign [rapports d’analyse descriptive](../reporting/built-in-reports.md) vous permet de concevoir et de partager des rapports statistiques sur vos populations.

[En savoir plus](../reporting/built-in-reports.md).

+++

+++ Comment concevoir des rapports avancés sur mes données ?

Avec Campaign v8, vous pouvez [créer des rapports avancés](../reporting/custom-reports.md). En tant qu’utilisateur expert, vous serez en mesure de créer, mettre à jour et distribuer des rapports personnalisés sur vos données.

Vous pouvez également utiliser l’interface utilisateur web de Campaign pour créer des rapports et des tableaux de bord. [En savoir plus](https://experienceleague.adobe.com/en/docs/campaign-web/v8/reports/gs-reports){target="_blank"}.

+++

+++ Qu&#39;est-ce qu&#39;un cube et comment créer ce type de rapport ?

Vous pouvez ainsi d&#39;étendre les capacités d&#39;exploration et d&#39;analyse des données de la base, tout en simplifiant le paramétrage des rapports et tableaux pour les utilisateurs finaux : ils n&#39;ont plus qu&#39;à sélectionner un cube existant, entièrement paramétré, lors de la création de leur rapport ou tableau pour en exploiter les calculs, mesures et statistiques.

Une fois créés et paramétrés, les cubes sont utilisés dans les boîtes de requête des rapports et les applications Web. Ils peuvent être exploités et manipulés au sein de tableaux croisés dynamiques.

Découvrez comment [explorer vos données](../reporting/gs-cubes.md) avec des cubes.

+++

+++ Est-il possible de créer un rapport à partir des réponses à un questionnaire en ligne ?

Campaign v8 ne dispose pas d’une fonctionnalité d’enquête intégrée. Vous pouvez utiliser Adobe Experience Manager ou d’autres solutions web pour créer des questionnaires.

Cependant, vous pouvez utiliser les fonctionnalités de création de rapports pour analyser toutes les données collectées et créer des rapports personnalisés.

+++

+++ Comment puis-je partager l&#39;accès à mon rapport dans l&#39;interface de Campaign ? 

Vous pouvez définir dans quel contexte votre rapport sera affiché dans l&#39;interface utilisateur d&#39;Adobe Campaign. Pour plus d&#39;informations sur les rapports, voir [cette section](../reporting/custom-reports.md).

+++

+++ Puis-je exporter des rapports dans différents formats ?

Oui, vous pouvez exporter des rapports Campaign dans différents formats tels qu’Excel, PDF ou CSV. [En savoir plus](../reporting/custom-reports.md).

+++

## Développeurs {#developers}

Accédez aux informations techniques destinées aux développeurs, notamment les détails du modèle de données, les schémas, les API et les fonctionnalités de personnalisation.

+++ Quel est le modèle de données de Campaign ? 

Le modèle de données conceptuel de la base de données Adobe Campaign se compose d’un ensemble de tables intégrées et de leur interaction. La structure physique et logique des données véhiculées dans l’application est décrite en XML. Il obéit à une grammaire spécifique à Adobe Campaign, appelée schéma.

[En savoir plus sur le modèle de données de Campaign](../dev/datamodel.md).

[Cette page répertorie les bonnes pratiques](../dev/datamodel-best-practices.md).

+++

+++ Comment utiliser des schémas de Campaign ?

Dans Adobe Campaign, les schémas de données permettent de :

* définir la façon dont les objets de l&#39;application sont liés à des tables de la base de données ;
* définir des liens entre les différents objets de l&#39;application ;
* définir et décrire les champs individuels inclus dans chaque objet.

[Commencez avec des tables et des schémas](../dev/schemas.md) pour comprendre comment utiliser le schéma de données, étendre et personnaliser Campaign pour répondre à vos besoins.

+++

+++ Comment utiliser une table de destinataires personnalisée ?

Vous pouvez créer et implémenter une table des destinataires non intégrée dans Campaign pour envoyer vos messages.

[En savoir plus](../dev/custom-recipient.md)

+++

+++ Quelles sont les bonnes pratiques pour définir des requêtes dans Campaign ? 

Le requêteur Adobe Campaign est un outil puissant permettant d&#39;explorer les données et de créer des segments.

L&#39;outil de requêtage est présent à de nombreux niveaux de la plateforme Adobe Campaign : pour créer une population cible, segmenter les clients, extraire et filtrer des logs de tracking, construire des filtres, etc.

Vous pouvez interroger la base de données Campaign grâce au requêteur générique. Il est accessible depuis le menu **Outils > Requêteur générique...**. Il permet d&#39;extraire des informations stockées dans une base de données, les organiser, les regrouper, les trier, etc. Par exemple, l&#39;utilisateur peut récupérer les destinataires ayant cliqué plus de &#39;n&#39; fois dans le lien d&#39;une newsletter et sur une période donnée. Il pourra organiser la collecte, le tri et l’affichage des résultats selon vos besoins.

[En savoir plus](../start/query-editor.md). Vous pouvez également consulter le [guide d’automatisation de Campaign](https://experienceleague.adobe.com/fr/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html?lang=fr){target="_blank"}.

+++

+++ Comment importer un package de données ? 

Adobe Campaign vous permet d&#39;exporter ou d&#39;importer la configuration et les données de la plateforme grâce à un système de packages. Les packages de données permettent l&#39;affichage des entités de la base de données Adobe Campaign à l&#39;aide de fichiers au format XML. Chaque entité contenue dans un package est représentée avec l&#39;ensemble de ses données.

Le principe des packages de données consiste à exporter un paramétrage de données puis l&#39;intégrer dans un autre système Adobe Campaign.

[En savoir plus](../dev/packages.md) sur l’utilisation des packages de données pour importer et exporter des configurations Campaign.

+++

+++ Où puis-je trouver la liste des API de Campaign v8 ?

Toutes les API de Campaign, y compris leur description complète, sont disponibles dans cette [documentation dédiée](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=fr){target="_blank"}.

+++

+++ Qu’est-ce que l’API REST Campaign ?

Campaign v8 propose un ensemble d’API REST qui permettent de créer des intégrations pour Adobe Campaign et de construire votre propre écosystème en interfaçant Adobe Campaign avec l’ensemble des technologies que vous utilisez.

[En savoir plus](../dev/api/get-started-apis.md).

+++

+++ Comment surveiller les workflows à partir de l’API ?

Découvrez comment surveiller les workflows à l&#39;aide des API Campaign dans [cette page dédiée](../dev/api/controlling-a-workflow.md).

+++

+++ Comment mettre à jour la structure de la base de données ?

Si vous modifiez les schémas de données de Campaign, vous devez mettre à jour la structure de la base de données. Découvrez comment dans [cette section](../dev/update-database-structure.md).

+++

+++ Quelles sont les limites de Campaign v8 ?

Campaign v8 s’accompagne de certaines limitations par rapport à Campaign Classic v7, présentées en détail dans [cette page](../start/v7-to-v8.md#limitations).

+++

## Confidentialité {#privacy}

Découvrez comment Adobe Campaign vous aide à vous conformer aux réglementations de confidentialité comme le RGPD et le CCPA, et à gérer les demandes des titulaires de données.

+++ Quels sont les termes clés de la protection des données personnelles ?

Les éléments répertoriés ci-dessous renvoient aux termes et concepts clés relatifs à la protection des informations personnelles et au consentement dans Adobe Campaign :

* [Règlements relatifs à la gestion de la confidentialité](../start/privacy.md#privacy-regulations)
* [Données personnelles et personnes concernées](../start/privacy.md#personal-data)
* [Droit d’accès et droit à l’oubli](../start/privacy.md#right-access-forgotten)
* [Consentement, conservation des données et rôles](../start/privacy.md#consent-retention-roles)

+++

+++ Que suggère Adobe Campaign pour se conformer aux dernières réglementations en matière de protection des données personnelles ?

Adobe ne fournit pas de conseils juridiques. Nous vous recommandons donc de vous rapprocher de votre propre service juridique pour vous assurer qu’il prend toutes les mesures nécessaires pour le respect du RGPD, de l’ACPCP, de PDPA, du LGPD ou de toute autre disposition réglementaire applicable.

**Préparation aux demandes d’accès et de suppression des données**

* Identifiez un processus pour recevoir les demandes formulées par les titulaires des données et y répondre, en désignant notamment un point de contact en charge de la protection des données.

* Examinez les différents types de données client stockées dans Adobe Campaign et définissez des identifiants uniques (il en faudra certainement plusieurs).

* Définissez des règles et procédures d’authentification et de validation pour la confirmation de l’identité des titulaires des données.

* Assurez-vous que la réponse adressée au titulaire de données est parfaitement compréhensible.

**Obtention du consentement**

* Établissez régulièrement la liste de tous les points de contact utilisés pour la capture des données afin de garantir votre conformité avec le RGPD (tenez compte de la langue, du mécanisme d’obtention du consentement et des logs de consentements, par exemple).

* Vérifiez que tous les emails marketing comprennent un lien de désabonnement.

* Évaluez la stratégie globale du marketing email pour définir des mises en œuvre propres à chaque zone géographique.

**Compréhension des données**

* Passez en revue toutes les sources de capture et d’import des données transitant par Adobe Campaign, et documentez les champs utilisés dans le cadre de vos actions marketing.

* Supprimez tout attribut de données non utilisé de votre base de données Adobe Campaign.

* Utilisez les données disponibles dans Adobe Campaign aux fins pour lesquelles elles ont été collectées, et offrez aux destinataires une expérience plus personnalisée.

* Passez en revue les autorisations d’accès aux données et mettez-les à jour pour que les utilisateurs d’Adobe Campaign puissent exploiter uniquement les données nécessaires à l’exécution de leurs campagnes, sans accéder aux autres données.

* Vérifiez que chaque utilisateur d’Adobe Campaign dispose des droits d’accès nécessaires pour exécuter ses tâches, mais qu’il ne dispose d’aucun autre droit pour effectuer d’autres tâches.

+++

+++ Comment les contrôleurs de données peuvent-ils obtenir le consentement avec un minimum d’impact sur l’engagement client ?

Dans les cas où le consentement est nécessaire pour certaines activités de commercialisation, le consentement du consommateur doit être actif (l’absence de réponse ne peut valoir consentement, pas d’utilisation de cases pré-cochées). Le consentement ne doit pas non plus être groupé, ni être conditionné à l’offre de services.

Certains consentements doivent même parfois être réactualisés pour que les données puissent continuer à être utilisées.

Les spécialistes marketing devraient considérer ces exigences de consentement améliorées comme un véritable indicateur d’engagement et de loyauté envers la marque, ainsi que de la satisfaction et de la confiance des clientes et clients.

+++

+++ Comment les contrôleurs de données peuvent-ils gérer le consentement dans Adobe Campaign ?

Adobe Campaign offre déjà des capacités de gestion du consentement à plus de niveaux que la plupart des spécialistes marketing ne tirent parti des champs de données personnalisés ou d’un ou plusieurs services.

Il est conseillé aux spécialistes marketing de consulter leur service juridique pour savoir comment procéder, puis tirer parti des capacités déjà intégrées à Adobe Campaign.

Par exemple, il est possible d’étendre le modèle de données dans Adobe Campaign pour suivre non seulement si les personnes ont choisi de s’inscrire, mais aussi l’horodatage de l’opt-in et un type d’indicateur qui capture la portée précise du consentement.

+++

+++ Quelles données les contrôleurs de données peuvent-ils supprimer dans Adobe Campaign en réponse à une requête d’un client (titulaire des données) ?

Toutes les données associées au titulaire de données seront supprimées, y compris les tables d’usine et personnalisées.

Techniquement, toutes les données liées au titulaire de données avec `integrity="own"` seront supprimées.

En tant que contrôleur de données, vous avez la possibilité de personnaliser cela en modifiant l’intégrité des liens définis dans les schémas de données (par exemple, si vous avez une justification commerciale pour ne pas supprimer certaines données).

+++

+++ Quel est l’impact de la suppression des logs de tracking et de diffusion sur les rapports ?

Dans Adobe Campaign, les rapports reposent sur des indicateurs calculés grâce aux données agrégées issues des logs de diffusion et de tracking. Par conséquent, la suppression de ces logs ne doit pas avoir d’incidence sur les mesures affichées dans les rapports.

+++

+++ Dois-je garder à l’esprit la possibilité de réimporter les données ultérieurement ?

Dans Adobe Campaign, les enregistrements sont souvent chargés à partir d’une source de données externe.

Lorsque vous recevez une demande de suppression, vous devez vérifier, en tant que contrôleur de données, que vous supprimez de tous vos systèmes toutes les données nécessaires concernant le titulaire de données.

+++

+++ Est-ce qu’un ou une titulaire de données, dont les données ont été effacées d’Adobe Campaign, peut à nouveau donner son opt-in plus tard ?

Il est possible pour un titulaire de données de donner à nouveau son accord ou d’être ajouté en tant que nouveau destinataire après l’effacement de ses données d’Adobe Campaign.

Vous pouvez utiliser le journal d’audit qui détaille la date de suppression précédente et la date de création du nouveau destinataire.

+++

## Vous avez encore besoin d&#39;aide ? {#get-help}

Vous ne trouvez pas ce que vous recherchez ? Voici des ressources supplémentaires pour vous aider à réussir avec Adobe Campaign v8.

### Soutien de la communauté

Communiquez avec d’autres utilisateurs de Campaign et des experts d’Adobe pour partager vos connaissances et obtenir des réponses.

* **[Communauté Adobe Campaign ](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-classic/ct-p/adobe-campaign-classic-community?profile.language=fr){target="_blank"}** - Posez des questions, partagez des solutions et communiquez avec la communauté Campaign
* **[Forums Experience League ](https://experienceleaguecommunities.adobe.com/){target="_blank"}** - Parcourez les discussions sur tous les produits Adobe
* **[Heures de bureau de la communauté Campaign](https://experienceleague.adobe.com/){target="_blank"}** - Participez à des sessions en direct avec des experts d’Adobe

### Documentation et apprentissage

Accédez à des guides, tutoriels et supports de formation complets.

* **[Page d’accueil de la documentation de Campaign v8](../campaign-home.md)** - Documentation complète du produit
* **[Tutoriels Campaign](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/overview.html?lang=fr){target="_blank"}** - Guides vidéo détaillés et tutoriels pratiques
* **[Nouveautés](whats-new.md)** - Dernières fonctionnalités
* **[Notes de mise à jour](release-notes.md)** - Informations sur les versions actuelle et précédente
* **[Bonnes pratiques](delivery-best-practices.md)** - Approches recommandées pour les tâches courantes

### Ressources techniques

Recherchez une documentation technique détaillée et des ressources pour les développeurs.

* **[API Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=fr){target="_blank"}** - Documentation complète de référence sur les API
* **[Campaign GitHub](https://github.com/AdobeDocs/campaign.en)** - Contribution à la documentation
* **[Notes techniques](https://experienceleague.adobe.com/fr/docs/campaign/technotes-ac/technotes-home){target="_blank"}** - Articles techniques détaillés
* **[Matrice de compatibilité](compatibility-matrix.md)** - Systèmes et versions pris en charge

### Assistance et services

Obtenez de l’aide de l’équipe d’assistance Adobe et gérez votre instance.

* **[Adobe Admin Console](https://adminconsole.adobe.com/){target="_blank"}** - Consigner les cas d&#39;assistance et gérer les utilisateurs
* **[Assistance clientèle Adobe ](https://helpx.adobe.com/fr/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}** - Contactez l’équipe d’assistance
* **[Panneau de Contrôle ](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=fr){target="_blank"}** - Gérer les paramètres de votre instance Campaign
* **[Statut du système](https://status.adobe.com/){target="_blank"}** - Vérifiez le statut des services Adobe

### Formation et certification

Améliorez vos compétences grâce aux programmes de formation et de certification officiels d’Adobe.

* **[Adobe Digital Learning Services ](https://learning.adobe.com/){target="_blank"}** - Cours officiels dispensés par un instructeur et à son propre rythme
* **[Certification Adobe Campaign ](https://experienceleague.adobe.com/docs/certification/program/overview.html){target="_blank"}** - Validez votre expertise avec la certification professionnelle
* **[Parcours d’apprentissage Experience League ](https://experienceleague.adobe.com/?lang=fr#dashboard/learning){target="_blank"}** - parcours d’apprentissage guidés

### Autres ressources utiles

* **[Documentation de Campaign Classic v7 ](https://experienceleague.adobe.com/docs/campaign-classic/using/campaign-classic-home.html?lang=fr){target="_blank"}** - Référence pour les utilisateurs de Classic v7
* **[Documentation sur l’interface utilisateur web de Campaign](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/campaign-web-home){target="_blank"}** - Nouveau guide de l’interface web
* **[Bonnes pratiques en matière de délivrabilité](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=fr){target="_blank"}** - Optimisation de la diffusion e-mail
* **[Mises à jour de produits](https://experienceleague.adobe.com/en/docs/release-notes/experience-cloud/current){target="_blank"}** - Dernières mises à jour de Adobe Experience Cloud

**Dernière mise à jour :** novembre 2025 | **S’applique à :** Campaign v8.6 et versions ultérieures

*Une erreur a été trouvée ou une amélioration doit être suggérée ? [Modifiez cette page sur GitHub](https://github.com/AdobeDocs/campaign.en/edit/main/help/v8/start/campaign-faq-comprehensive.md)*

