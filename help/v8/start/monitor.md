---
title: Présentation de la surveillance des campagnes
description: Découvrez comment surveiller les diffusions, les workflows et votre instance Campaign
feature: Monitoring
role: User
level: Beginner
exl-id: 2ad585f2-19bc-4391-8a19-9e892dbe01a3
TQID: https://experienceleague.adobe.com/PjU1EFX5x4iB3yRsShGBWoR0k1D2-EI90-ss0FTcexE
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c1579802-ddd4-4214-8a91-97b2066abe11id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 6cf587ecc9cc1e4cf9b3de0d2067e0c4562afe01
workflow-type: tm+mt
source-wordcount: 2206
ht-degree: 6%

---

# Présentation de la surveillance des campagnes {#monitor-campaign}

Adobe Campaign vous offre une visibilité à tous les niveaux, depuis le moment où un message individuel a été diffusé, les raisons de l’échec d’un workflow jusqu’à la capacité de base de données restante de votre instance. Cette page mappe toutes les fonctionnalités de surveillance afin que vous sachiez où chercher lorsque quelque chose nécessite votre attention.

>[!NOTE]
>
>En tant qu’administrateur Campaign, vous pouvez également utiliser le Panneau de Contrôle Campaign](#control-panel) pour surveiller vos instances, gérer les performances et configurer les paramètres avec des fonctionnalités en libre-service.[

>[!TIP]
>
>**Vous ne savez pas par où commencer ?**
>
>- [ Vérification du spécialiste marketing sur une campagne →surveiller vos diffusions](#monitor-deliveries)
>- Résolution des problèmes liés à un workflow → [surveiller les workflows](#monitor-workflows)
>- L’administrateur vérifiant l’intégrité de l’instance → [ Surveiller votre instance ](#monitor-instance)

## Surveiller vos diffusions {#monitor-deliveries}

La surveillance de vos diffusions après leur envoi est une étape clé pour vous assurer que vos campagnes marketing sont efficaces et atteignent vos clients. Après l’envoi d’une diffusion, vous pouvez surveiller son statut et suivre les mesures clés dans le tableau de bord de diffusion. Le tableau de bord permet d’accéder aux logs de diffusion, aux logs d’exclusion, aux logs de tracking et à d’autres fonctionnalités de surveillance pour vous aider à analyser les performances de votre diffusion sur tous les canaux.

>[!NOTE]
>
>**Vous découvrez Campaign ?** Le tableau de bord de la diffusion est votre principal écran quotidien. Ouvrez une diffusion envoyée, cliquez sur l’onglet **Logs** et vous verrez quels destinataires ont reçu le message, lesquels ont été exclus et pourquoi, et qui a cliqué ou ouvert.

**Diffusions e-mail** - Surveillez le statut de diffusion des e-mails, suivez les mesures clés et accédez à des journaux détaillés. En savoir plus sur la [surveillance des diffusions dans l’interface utilisateur de Campaign](https://experienceleague.adobe.com/fr/docs/campaign/campaign-v8/send/monitor/delivery-dashboard), [les statuts de diffusion](https://experienceleague.adobe.com/fr/docs/campaign/campaign-v8/send/monitor/delivery-statuses) et [surveillance des diffusions par e-mail](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/emails/send#email-monitoring).

**Diffusions SMS** - Suivez le statut des diffusions SMS et surveillez les mesures clés dans le tableau de bord des diffusions SMS. En savoir plus sur la [surveillance des SMS](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/sms/sms-monitor).

**Notifications push** - Surveillez les diffusions de notifications push pour vous assurer qu&#39;elles atteignent efficacement les utilisateurs de vos applications mobiles. En savoir plus sur la [surveillance des notifications push](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/push/push#push-test).

**Messages transactionnels** - Pour les messages déclenchés par des événements, surveillez l’état du traitement des événements, l’exécution des messages et l’état de la diffusion. En savoir plus sur la [surveillance des messages transactionnels](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/real-time/event/delivery-execution#monitor-messages).

**Diffusions en échec** - Il est essentiel de comprendre les raisons de l’échec d’une diffusion pour maintenir une base de données propre et garantir de bons taux de délivrabilité. Les diffusions en échec sont classées en trois types. Comprendre la différence vous permet de décider de l’action à entreprendre :

| Type d&#39;échec | Signification | Fonctionnement de Campaign |
| --- | --- | --- |
| **Hard bounce** | L&#39;adresse est définitivement invalide (n&#39;existe pas, domaine inconnu) | Le contact est automatiquement mis en quarantaine : il ne sera pas ciblé dans les prochaines diffusions |
| **Soft bounce** | Un problème temporaire (boîte pleine, serveur temporairement indisponible) | Campaign effectue automatiquement de nouvelles tentatives pendant une période configurée |
| **ignoré** | L&#39;adresse était déjà en quarantaine ou sur une place sur la liste bloquée avant l&#39;envoi | Aucune tentative n’est effectuée, comptabilisée séparément des rebonds |

En savoir plus sur les [diffusions en échec et mises en quarantaine](https://experienceleague.adobe.com/fr/docs/campaign/campaign-v8/send/monitor/delivery-failures).

## Surveillance de la délivrabilité {#monitor-deliverability}

>[!NOTE]
>
>Un message comptabilisé comme « diffusé » signifie qu’il a été accepté par le serveur de réception ; il ne garantit pas l’emplacement de la boîte de réception. La surveillance de la délivrabilité vous indique si l’authentification du domaine d’envoi, la réputation des adresses IP et le contenu des e-mails répondent aux normes des fournisseurs de boîte de réception.

La surveillance de la délivrabilité vous permet de vous assurer que vos messages atteignent les boîtes de réception de vos destinataires et évitent les filtres de spam. Adobe Campaign fournit plusieurs outils intégrés pour surveiller et améliorer la délivrabilité, notamment les rapports de diffusion, l’inbox rendering, les tests SpamAssassin et les statistiques de diffusion. Le respect des bonnes pratiques de délivrabilité, telles que la maintenance d&#39;une liste d&#39;emails propre, la surveillance de la réputation de l&#39;expéditeur et l&#39;authentification des domaines d&#39;envoi, est essentiel pour maintenir de bons taux de délivrabilité.

Découvrez les [outils de surveillance de la délivrabilité](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/deliverability-management/monitoring-deliverability) et [bonnes pratiques en matière de délivrabilité](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/deliverability-management/about-deliverability).

## Surveiller les workflows {#monitor-workflows}

Les workflows sont essentiels pour automatiser vos campagnes marketing et le traitement des données. La surveillance de l’exécution des workflows vous permet d’effectuer les opérations suivantes :

- S’assurer que les workflows sont terminés avec succès
- Identification et résolution des erreurs
- Optimisation des performances des workflows

>[!TIP]
>
>Si un workflow affiche le statut **Échec**, ouvrez-le, cliquez avec le bouton droit sur l’activité rouge, puis sélectionnez **Afficher les journaux**. Le message d’erreur identifie exactement ce qui s’est passé et sur quel enregistrement.

### Fonctionnalités de surveillance des workflows {#workflow-monitoring}

**Surveillez les éléments de workflow suivants :**

**Statut d’exécution du workflow** - Vérifiez si les workflows sont en cours d’exécution, en pause, en échec ou terminés. [En savoir plus sur l’exécution des workflows](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution#_blank)

**Journaux d’exécution des activités** - Accédez aux journaux détaillés de chaque activité de workflow pour résoudre les problèmes et optimiser les performances.

**Carte thermique des workflows** - Aperçu visuel de tous les workflows s’exécutant simultanément sur votre instance. Utilisez-la pour identifier les périodes de charge maximale, repérer les workflows qui consomment des ressources disproportionnées et planifier la planification afin d’éviter les conflits d’exécution. Disponible uniquement pour les administrateurs de Campaign. [En savoir plus sur la carte thermique des workflows](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/monitoring-workflows/heatmap#_blank)

**Historique des workflows** - Suivez toutes les exécutions et modifications de workflows au fil du temps pour comprendre leur comportement et leurs performances.

## Surveiller votre instance {#monitor-instance}

La surveillance des instances permet d’assurer l’intégrité et les performances de votre environnement Adobe Campaign. Pour Campaign v8 Managed Cloud Services, Adobe surveille et gère également l’infrastructure pour votre compte. En savoir plus sur la [surveillance gérée par ](#adobe-cloud-monitoring).

### Journal d’audit {#audit-trail}

L&#39;interface en libre-service du journal d&#39;audit vous permet de surveiller les modifications apportées à votre instance Adobe Campaign. Le journal d&#39;audit capture, en temps réel, une liste complète d&#39;actions et d&#39;événements se produisant dans votre instance.

**Utiliser le journal d’audit pour :**

- **Suivi des modifications des composants** : surveillez ce qui est arrivé à vos workflows, schémas, options et autres composants
- **Identifier les personnes qui ont apporté des modifications** : voir qui a mis à jour un élément spécifique pour la dernière fois et quand
- **Comprendre les actions des utilisateurs** : vérifiez ce que les utilisateurs ont fait dans l’instance à des fins de dépannage ou d’audit
- **Maintenir la conformité** : suivez toutes les modifications apportées à la configuration à des fins de conformité et de sécurité.

Le journal d’audit est accessible via la console cliente Campaign et fournit des informations détaillées sur les actions effectuées par les utilisateurs.

En savoir plus sur le [Journal d’audit](https://experienceleague.adobe.com/fr/docs/campaign/campaign-v8/analytics/audit-trail)

### Suivi des performances {#performance-monitoring}

Campaign v8 fournit plusieurs fonctionnalités de surveillance pour suivre les performances de votre instance et garantir un fonctionnement optimal :

**Surveillance de la base de données** - Surveillez l’utilisation et la capacité de la base de données par Panneau de Contrôle pour assurer une gestion optimale des performances et du stockage. [En savoir plus sur la surveillance des bases de données](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/database-monitoring/database-monitoring#_blank)

**Surveillance des profils actifs** - Effectuez le suivi de l’utilisation des profils actifs par rapport à vos limites contractuelles pour maintenir la conformité et optimiser l’affectation des ressources. [En savoir plus sur les profils actifs](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/active-profiles-monitoring#_blank)

**Surveillance des workflows** - Surveillez le statut d’exécution des workflows pour identifier les workflows de longue durée et vérifier que tous les workflows techniques s’exécutent correctement. [En savoir plus sur les workflows techniques](#technical-workflows)

**Débit de diffusion et latence** - Effectuez le suivi du débit de diffusion (messages envoyés par heure) et de la latence pour les communications transactionnelles par Panneau de Contrôle. [En savoir plus sur la surveillance du débit](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/throughputs-latencies#_blank)

>[!NOTE]
>
>Pour Campaign v8 Managed Cloud Services, l’infrastructure du serveur (CPU, mémoire, disque) est surveillée et gérée par Adobe. En savoir plus sur la [surveillance gérée par ](#adobe-cloud-monitoring).

### Surveillance gérée par Adobe {#adobe-cloud-monitoring}

Adobe Campaign Cloud Services fournit une assistance essentielle pour les besoins exigeants de diffusion de l’expérience client grâce à une infrastructure cloud flexible. Les entreprises peuvent ainsi lancer, surveiller et optimiser les expériences client sans avoir à gérer ni à exploiter elles-mêmes l’infrastructure Campaign.

Adobe surveille vos environnements Campaign Cloud Services pour vous aider à gérer divers problèmes et à minimiser les perturbations en détectant les problèmes techniques et en fournissant des commentaires continus sur les performances et les projets en cours.

**Réponse d’Adobe**

Adobe surveille tous les équipements réseau critiques sur le réseau Campaign 24h/24 et 7j/7 et reçoit des notifications de la part des systèmes de surveillance lorsque des correctifs ou des réaffectations sont nécessaires. Lorsqu’il détecte un problème, le système utilise des mécanismes de redémarrage et de lancement automatiques pour tenter d’y remédier. Si le système n’applique pas de solution autonome, l’ingénierie On-Call d’Adobe intervient pour effectuer le dépannage en fonction des runbooks d’alerte prédéfinis.

>[!NOTE]
>
>Certaines actions de surveillance effectuées par Adobe apparaissent dans les journaux Campaign sous l’utilisateur **campaign-loginmonitor**.

Outre la surveillance interne d’Adobe, vous pouvez accéder aux fonctionnalités de surveillance directement depuis la console cliente Campaign ou le [Panneau de Contrôle Campaign](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/permissions/self-service). Par Panneau de Contrôle, vous pouvez vous abonner à des alertes en temps réel sur vos instances et recevoir des mesures correctives recommandées pour les incidents identifiés (par exemple, l’expiration prochaine des certificats SSL).

**Surveillance de la taxonomie**

Adobe surveille votre environnement sur trois niveaux :

| Niveau | Groupe | Impact commercial potentiel |
| --- | --- | --- |
| **Niveau 1 : infrastructure** | Épuisement de l’espace base de données | Problèmes de performances, notamment impossibilité de se connecter, d’exécuter des diffusions par lots ou d’exécuter des requêtes |
| **Niveau 1 : infrastructure** | Disponibilité de la base de données | Il se peut que les utilisateurs et les services ne puissent pas utiliser le système |
| **Niveau 1 : infrastructure** | Surcharge de la base de données (répartition en rafale) | Problèmes de performances, notamment impossibilité de se connecter, d’exécuter des diffusions par lots ou d’exécuter des requêtes |
| **Niveau 1 : infrastructure** | Épuisement de la séquence de base de données et de l’ID de transaction | Impossible de créer des workflows, des diffusions ou d’envoyer des e-mails par lots |
| **Niveau 1 : infrastructure** | Stockage SFTP | Impossible de mettre à jour ou de récupérer les données sur les serveurs SFTP |
| **Niveau 2 : plateforme et web** | Login | Les utilisateurs ne pourront peut-être pas se connecter ; les activités et workflows planifiés risquent de ne pas s&#39;exécuter |
| **Niveau 2 : plateforme et web** | Verrouillage d’API | Les utilisateurs et utilisatrices ou les services peuvent ne pas être en mesure de s’authentifier ou d’exécuter des opérations |
| **Niveau 2 : plateforme et web** | Web | Impossible de créer de nouvelles connexions à Campaign |
| **Niveau 2 : plateforme et web** | Réseau de centres de données | Problèmes de performances ou indisponibilité complète pour les utilisateurs du centre de données |
| **Niveau 3 : Logiciel** | Tracking de la diffusion | Le traitement des logs de tracking n’est pas disponible |
| **Niveau 3 : Logiciel** | inMail | Aucun commentaire sur les erreurs et les bounces des diffusions par e-mail |
| **Niveau 3 : Logiciel** | Statut du Message Center | Impossible d’envoyer des diffusions transactionnelles |
| **Niveau 3 : Logiciel** | MTA | Impossible d’envoyer les diffusions e-mail planifiées et ad hoc |
| **Niveau 3 : Logiciel** | Statut du serveur de workflow | Impossible d’exécuter les workflows |
| **Niveau 3 : Logiciel** | Disponibilité des API web | Impossible de traiter les requêtes HTTP ou d’exécuter les appels API |
| **Niveau 3 : Logiciel** | Interactions entrantes | Impossible de traiter les interactions entrantes |

>[!NOTE]
>
>Les services cloud Adobe Campaign reposent sur une stratégie multi-cloud et offrent des déploiements sur AWS et Azure. En raison de différences entre les fournisseurs, les fonctionnalités de surveillance diffèrent entre AWS, Azure et les autres déploiements de centres de données. Le tableau ci-dessus s’applique aux clients de Campaign Cloud Services hébergés sur AWS, sauf indication contraire. Notez également qu’Adobe Campaign n’expose actuellement pas toutes les données de surveillance utilisées par l’ingénierie On-Call aux clients.

### Workflows techniques {#technical-workflows}

Les workflows techniques sont des processus essentiels qui s’exécutent en arrière-plan pour gérer votre instance Campaign.

**Vérifiez que les workflows techniques sont les suivants :**

- Exécution selon le calendrier
- Fin réussie sans erreur
- Traitement correct des données

**Workflows techniques clés à surveiller :**

| Workflow | Intérêt | En cas d’échec |
| --- | --- | --- |
| **Effectuer un tracking** | Traite les données de tracking des diffusions email | Cliquer et ouvrir les mesures pour arrêter la mise à jour dans les rapports |
| **Nettoyage** | Supprime les anciennes données et journaux pour maintenir les performances de la base de données | La base de données se développe de manière incontrôlée, ce qui dégrade les requêtes et les performances de diffusion |
| **Mise à jour délivrabilité** | Met à jour les règles de délivrabilité et les modèles de filtre anti-spam | Les règles deviennent obsolètes ; la précision du filtrage peut se dégrader |
| **Nettoyage de la base de données** | Purge les anciens logs de tracking et de diffusion | L’accumulation de journaux ralentit les requêtes et les rapports au fil du temps |

En savoir plus sur les [workflows techniques](https://experienceleague.adobe.com/en/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows#_blank)

### Panneau de contrôle Campaign {#control-panel}

Le Panneau de Contrôle Campaign permet aux administrateurs de surveiller et de gérer des instances Campaign en libre-service.

| Type de surveillance | Fonctionnalités |
| --- | --- |
| **Performances** | Suivre l’utilisation des profils actifs, surveiller l’utilisation et la capacité des bases de données, afficher le statut d’exécution des workflows, surveiller le débit de diffusion et la latence |
| **Infrastructure** | Surveiller la capacité de stockage SFTP, suivre la configuration des sous-domaines, surveiller l’expiration des certificats SSL, gérer les listes autorisées d’adresses IP |
| **Instance** | Afficher la version de build et les packages installés, surveiller la configuration du système, gérer les domaines externes autorisés |

En savoir plus sur la surveillance des performances des Panneaux de Contrôle [](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/permissions/self-service) et [](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/about-performance-monitoring#_blank)

>[!NOTE]
>
>Pour Campaign v8 Managed Cloud Services, Adobe surveille et gère l’infrastructure du serveur, le système d’exploitation et la couche applicative. En savoir plus sur la [surveillance gérée par ](#adobe-cloud-monitoring). Vous pouvez utiliser les fonctionnalités de surveillance décrites sur cette page et dans ce Panneau de Contrôle pour surveiller les performances de votre instance, les workflows et les diffusions.

## Tracking et reporting {#tracking-reporting}

### Tracking des messages {#message-tracking}

Suivez le comportement des destinataires et mesurez l’efficacité de vos campagnes :

- **Ouvertures** : suivez le moment où les destinataires ouvrent vos e-mails
- **Clics** : surveiller les liens sur lesquels cliquent les destinataires
- **Désabonnements** : suivi des demandes d’exclusion
- **Pages miroir vues** : déterminez le nombre de destinataires qui consultent votre e-mail dans un navigateur

En savoir plus sur le [tracking des messages](https://experienceleague.adobe.com/fr/docs/campaign/campaign-v8/analytics/tracking/tracking)

### Rapports sur les diffusions {#delivery-reports}

Adobe Campaign fournit un ensemble complet de rapports pour analyser les performances de vos diffusions :

- **Résumé de diffusion** : présentation des envois, diffusions et échecs
- **Indicateurs de tracking** : ouvertures, clics et taux de clics publicitaires
- **URL et flux de clics** : liens les plus populaires dans vos diffusions
- **Position des clics** : représentation visuelle de l’emplacement où les destinataires ont cliqué dans votre e-mail

En savoir plus sur les [ rapports de diffusion ](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/analytics/reports/ac-reports/delivery-reports)

### Rapports globaux {#global-reports}

Accédez aux rapports globaux pour analyser les performances de toutes les campagnes et diffusions :

- **Débit de diffusion** : messages envoyés au fil du temps
- **Échecs et retours** : analyse des diffusions en échec
- **Activités utilisateur** : s’ouvre, clique et se désabonne dans toutes les campagnes

En savoir plus sur les [ rapports globaux ](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/analytics/reports/ac-reports/global-reports)

## Rubriques connexes {#related-topics}

- [Bonnes pratiques de diffusion](https://experienceleague.adobe.com/fr/docs/campaign/campaign-v8/send/delivery-best-practices)
- [Gestion des quarantaines](https://experienceleague.adobe.com/fr/docs/campaign/campaign-v8/send/monitor/quarantines)
- [Configuration et envoi de diffusions](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/send/validate/configure-and-send)
- [Prise en main des rapports](https://experienceleague.adobe.com/fr/docs/campaign/campaign-v8/analytics/reports/gs-reporting)
