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
source-git-commit: e8438b85eec144e83b2660f9d66444c1a01863ab
workflow-type: tm+mt
source-wordcount: 2101
ht-degree: 6%

---

# Présentation de la surveillance des campagnes {#monitor-campaign}

Adobe Campaign vous offre une visibilité à tous les niveaux, depuis le moment où un message individuel a été diffusé, les raisons de l’échec d’un workflow jusqu’à la capacité de base de données restante de votre instance. Cette page mappe toutes les fonctionnalités de surveillance afin que vous sachiez où chercher lorsque quelque chose nécessite votre attention. En tant qu’administrateur Campaign, vous pouvez également utiliser le Panneau de Contrôle Campaign](#control-panel) pour surveiller vos instances, gérer les performances et configurer les paramètres avec des fonctionnalités en libre-service.[

>[!TIP]
>
>**Vous ne savez pas par où commencer ?**
>
>- [ Vérification du spécialiste marketing sur une campagne →surveiller vos diffusions](#monitor-deliveries)
>- Résolution des problèmes liés à un workflow → [surveiller les workflows](#monitor-workflows)
>- L’administrateur vérifiant l’intégrité de l’instance → [ Surveiller votre instance ](#monitor-instance)

## Surveiller vos diffusions {#monitor-deliveries}

La surveillance de vos diffusions après leur envoi est une étape clé pour vous assurer que vos campagnes marketing sont efficaces et atteignent vos clientèle. Après l’envoi d’une diffusion, vous pouvez suivre sa progression et diagnostiquer les problèmes depuis le tableau de bord de diffusion. Le tableau de bord vous donne accès aux logs de diffusion, aux logs d’exclusion, aux logs de tracking et à d’autres données pour chaque canal que vous utilisez.

>[!NOTE]
>
>**Vous découvrez Campaign ?** Le tableau de bord de la diffusion est votre principal écran quotidien. Ouvrez une diffusion envoyée, cliquez sur l’onglet **Logs** et vous verrez quels destinataires ont reçu le message, lesquels ont été exclus et pourquoi, et qui a cliqué ou ouvert.

**Diffusions e-mail** — Surveillez le statut de diffusion des e-mails, suivez les mesures clés et accédez à des journaux détaillés. En savoir plus sur la [surveillance des diffusions dans l’interface utilisateur de Campaign](../send/delivery-dashboard.md), [les statuts de diffusion](../send/delivery-statuses.md) et [surveillance des diffusions par e-mail](../send/send.md#email-monitoring).

**Diffusions SMS** — Suivez le statut des diffusions SMS et surveillez les mesures clés dans le tableau de bord des diffusions SMS. En savoir plus sur la [surveillance des SMS](../send/sms/sms-monitor.md).

**Notifications push** — Surveillez les diffusions de notifications push pour vous assurer qu&#39;elles atteignent efficacement les utilisateurs de vos applications mobiles. En savoir plus sur la [surveillance des notifications push](../send/push.md#push-test).

**Messages transactionnels** — Pour les messages déclenchés par des événements, surveillez le statut du traitement des événements, la profondeur de la file d&#39;attente et les résultats de l&#39;exécution. En savoir plus sur la [surveillance des messages transactionnels](../send/delivery-execution.md#monitor-messages).

**Diffusions en échec** — Il est essentiel de comprendre les raisons de l&#39;échec d&#39;une diffusion pour maintenir une base de données propre et assurer de bons taux de délivrabilité. Les diffusions en échec sont classées en trois types. Comprendre la différence vous permet de décider de l’action à entreprendre :

| Type d&#39;échec | Signification | Fonctionnement de Campaign |
| --- | --- | --- |
| **Hard bounce** | L&#39;adresse est définitivement invalide (n&#39;existe pas, domaine inconnu) | Le contact est automatiquement mis en quarantaine : il ne sera pas ciblé dans les prochaines diffusions |
| **Soft bounce** | Un problème temporaire (boîte pleine, serveur temporairement indisponible) | Campaign effectue automatiquement de nouvelles tentatives pendant une période configurée |
| **ignoré** | L&#39;adresse était déjà en quarantaine ou sur une place sur la liste bloquée avant l&#39;envoi | Aucune tentative n’est effectuée, comptabilisée séparément des rebonds |

En savoir plus sur les [diffusions en échec et mises en quarantaine](../send/delivery-failures.md).

## Surveillance de la délivrabilité {#monitor-deliverability}

La délivrabilité est la mesure dans laquelle vos messages atteignent les boîtes de réception des destinataires, par opposition à un filtrage visant à détecter le spam ou le rejet. Adobe Campaign fournit plusieurs outils intégrés pour vous aider à comprendre et à améliorer les taux d’emplacement de votre boîte de réception.

>[!NOTE]
>
>Un message comptabilisé comme « diffusé » signifie qu’il a été accepté par le serveur de réception ; il ne garantit pas l’emplacement de la boîte de réception. La surveillance de la délivrabilité vous indique si l’authentification du domaine d’envoi, la réputation des adresses IP et le contenu des e-mails répondent aux normes des fournisseurs de boîte de réception.

Adobe Campaign fournit les outils de délivrabilité intégrés suivants :

- **Rapports de diffusion** — Rapports intégrés indiquant le volume d&#39;envoi, les taux de rebond et les désabonnements au fil du temps.
- **Inbox rendering** — Prévisualisez l’apparence de votre e-mail sur les principaux clients (Gmail, Outlook, Apple Mail) avant ou après l’envoi.
- **Test SpamAssassin** — Évaluez le contenu de votre e-mail par rapport aux règles courantes de filtrage des courriers indésirables afin de détecter les problèmes avant la diffusion.
- **Statistiques de diffusion** — Agrégez les données de diffusion sur vos volumes d&#39;envoi et la réputation des adresses IP.

Le respect des bonnes pratiques en matière de délivrabilité, telles que la maintenance d&#39;une liste d&#39;emails propre, la surveillance de la réputation de l&#39;expéditeur et l&#39;authentification des domaines d&#39;envoi, est essentiel pour maintenir de bons taux de délivrabilité.

Découvrez les [outils de surveillance de la délivrabilité](../send/monitoring-deliverability.md) et [bonnes pratiques en matière de délivrabilité](../send/about-deliverability.md).

## Surveiller les workflows {#monitor-workflows}

Les workflows sont le moteur de vos automatisations marketing et du traitement des données. Leur surveillance permet de s’assurer que les activités planifiées se terminent comme prévu et que les erreurs sont détectées avant qu’elles n’affectent les diffusions ou la qualité des données.

>[!TIP]
>
>Si un workflow affiche le statut **Échec**, ouvrez-le, cliquez avec le bouton droit sur l’activité rouge, puis sélectionnez **Afficher les journaux**. Le message d’erreur identifie exactement ce qui s’est passé et sur quel enregistrement.

### Fonctionnalités de surveillance des workflows {#workflow-monitoring}

**Surveillez les éléments de workflow suivants :**

**Statut d&#39;exécution du workflow** — Vérifiez si les workflows sont en cours d&#39;exécution, en pause, en échec ou terminés. Repérez en un coup d’œil les workflows bloqués ou de longue durée. [En savoir plus sur l’exécution des workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=fr){target="_blank"}

**Journaux d’exécution d’activité** — Accédez aux journaux par activité pour comprendre ce qui s’est passé à chaque étape — utile pour résoudre les problèmes liés aux transitions ayant échoué ou aux sorties de données inattendues.

**Carte thermique des workflows** — Aperçu visuel de tous les workflows s’exécutant simultanément sur votre instance. Utilisez-la pour identifier les périodes de charge maximale, repérer les workflows qui consomment des ressources disproportionnées et planifier la planification afin d’éviter les conflits d’exécution. Disponible uniquement pour les administrateurs de Campaign. [En savoir plus sur la carte thermique des workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/heatmap.html?lang=fr){target="_blank"}

**Historique des workflows** — Suivez toutes les exécutions et modifications de workflows au fil du temps pour comprendre le comportement des workflows et les modèles de performances.

## Surveiller votre instance {#monitor-instance}

La surveillance des instances couvre l’intégrité de votre environnement Campaign, à savoir la capacité de la base de données, l’utilisation des profils, le débit et l’infrastructure. Pour Campaign v8 Managed Cloud Services, Adobe surveille et gère l’infrastructure sous-jacente en votre nom, mais vous conservez une visibilité totale via la console cliente et le Panneau de Contrôle. En savoir plus sur la [surveillance gérée par ](#adobe-cloud-monitoring).

### Journal d’audit {#audit-trail}

L&#39;interface en libre-service du journal d&#39;audit vous permet de surveiller chaque modification significative apportée à votre instance Adobe Campaign. Le journal d&#39;audit capture, en temps réel, une liste complète d&#39;actions et d&#39;événements se produisant dans votre instance.

**Utiliser le journal d’audit pour :**

- **Suivi des modifications apportées aux composants** — Surveillez ce qui est arrivé à vos workflows, schémas, options et autres composants
- **Identifier qui a apporté une modification** — Voir quel utilisateur a modifié un élément pour la dernière fois et à quelle heure
- **Dépannage des comportements inattendus** — Effectuez le suivi des actions des utilisateurs pour déterminer quand et comment un problème a été introduit
- **Prise en charge de la conformité et des audits** — Conservez un enregistrement complet et infalsifiable de toutes les modifications de configuration

Le journal d’audit est accessible via la console cliente Campaign et fournit des informations détaillées sur les actions effectuées par les utilisateurs.

En savoir plus sur le [Journal d’audit](../reporting/audit-trail.md)

### Suivi des performances {#performance-monitoring}

Campaign v8 fournit plusieurs fonctionnalités de surveillance pour suivre les performances de votre instance et garantir un fonctionnement optimal :

**Surveillance de la base de données** — Surveillez l&#39;utilisation et la capacité de la base de données par Panneau de Contrôle pour assurer une gestion optimale des performances et du stockage. [En savoir plus sur la surveillance des bases de données](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/database-monitoring.html){target="_blank"}

**Surveillance des profils actifs** — Effectuez le suivi de l’utilisation des profils actifs par rapport à vos limites contractuelles afin de maintenir la conformité et d’optimiser l’affectation des ressources. [En savoir plus sur les profils actifs](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=fr){target="_blank"}

**Surveillance des workflows** — Surveillez le statut d&#39;exécution des workflows pour identifier les workflows de longue durée et vérifier que tous les workflows techniques s&#39;exécutent correctement. [En savoir plus sur les workflows techniques](#technical-workflows)

**Débit de diffusion et latence** — Effectuez le suivi du débit de diffusion (messages envoyés par heure) et de la latence pour les communications transactionnelles par Panneau de Contrôle. [En savoir plus sur la surveillance du débit](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/throughputs-latencies.html){target="_blank"}

>[!NOTE]
>
>Pour Campaign v8 Managed Cloud Services, l’infrastructure du serveur (CPU, mémoire, disque) est surveillée et gérée par Adobe. Les fonctionnalités de surveillance décrites sur cette page et dans le Panneau de Contrôle sont complémentaires : elles vous donnent une visibilité sur vos données et votre configuration sans avoir besoin d’accéder à l’infrastructure. Certaines actions entreprises par Adobe apparaissent dans vos logs Campaign sous l’utilisateur **campaign-loginmonitor**. En savoir plus sur la [surveillance gérée par ](#adobe-cloud-monitoring).

### Surveillance gérée par Adobe {#adobe-cloud-monitoring}

Adobe Campaign Cloud Services fournit une assistance essentielle pour les besoins exigeants de diffusion de l’expérience client grâce à une infrastructure cloud flexible. Cela permet aux entreprises de lancer, de surveiller et d’optimiser les expériences client sans avoir à gérer ni à exploiter elles-mêmes l’infrastructure Campaign.

Adobe surveille vos environnements Campaign Cloud Services 24h/24 et 7j/7 afin de détecter les problèmes techniques et de minimiser les perturbations. Lorsqu’il détecte un problème, le système utilise des mécanismes de redémarrage et de lancement automatiques pour tenter d’y remédier. Si le système n’applique pas de solution autonome, l’ingénierie On-Call d’Adobe intervient en fonction des runbooks d’alerte prédéfinis.

>[!TIP]
>
>Vous pouvez vous abonner aux alertes d’instance en temps réel via le Panneau de Contrôle Campaign](#control-panel) et recevoir les étapes de résolution recommandées pour les problèmes détectés (par exemple, les certificats SSL arrivant à expiration).[

**Surveillance des niveaux**

Adobe surveille votre environnement sur trois niveaux. Les problèmes de niveau 1 ont l’impact le plus important et reçoivent la réponse la plus rapide :

| Niveau | Groupe | Ce que vous pourriez ressentir |
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
>Adobe Campaign Cloud Services repose sur une stratégie cloud multiple avec des déploiements sur AWS et Azure. Les fonctionnalités de surveillance diffèrent entre AWS, Azure et les autres déploiements de datacenter. Le tableau ci-dessus s’applique aux clients de Campaign Cloud Services hébergés sur AWS, sauf indication contraire. Actuellement, Adobe Campaign n’expose pas aux clients toutes les données de surveillance utilisées par l’ingénierie On-Call.

### Workflows techniques {#technical-workflows}

Les workflows techniques s’exécutent silencieusement en arrière-plan pour gérer votre instance Campaign. Ils ne sont pas créés par les utilisateurs et utilisatrices, mais sont fournis avec le produit. Si un workflow technique échoue, cela peut avoir une incidence directe sur les diffusions et la qualité des données.

Vérifiez que chaque workflow technique s’exécute selon le calendrier prévu, sans erreur et en traitant les données correctement.

| Workflow | Intérêt | En cas d’échec |
| --- | --- | --- |
| **Effectuer un tracking** | Traite les données de tracking des diffusions email | Cliquer et ouvrir les mesures pour arrêter la mise à jour dans les rapports |
| **Nettoyage** | Supprime les anciennes données et journaux pour maintenir les performances de la base de données | La base de données se développe de manière incontrôlée, ce qui dégrade les requêtes et les performances de diffusion |
| **Mise à jour délivrabilité** | Met à jour les règles de délivrabilité et les modèles de filtre anti-spam | Les règles deviennent obsolètes ; la précision du filtrage peut se dégrader |
| **Nettoyage de la base de données** | Purge les anciens logs de tracking et de diffusion | L’accumulation de journaux ralentit les requêtes et les rapports au fil du temps |

En savoir plus sur les [workflows techniques](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html?lang=fr){target="_blank"}

### Panneau de contrôle Campaign {#control-panel}

Le Panneau de Contrôle Campaign permet aux administrateurs de surveiller et de gérer des instances Campaign en libre-service, sans avoir besoin de ticket d’assistance.

| Type de surveillance | Fonctionnalités |
| --- | --- |
| **Performances** | Utilisation des profils actifs par rapport à la limite du contrat, utilisation et capacité de la base de données, statut d’exécution du workflow, débit de diffusion et latence |
| **Infrastructure** | Capacité de stockage SFTP, configuration de sous-domaines, alertes d’expiration des certificats SSL, listes autorisées d’adresses IP |
| **Instance** | Version de build et packages installés, présentation de la configuration du système, domaines externes autorisés |

En savoir plus sur la surveillance des performances des Panneaux de Contrôle [](../config/self-service.md) et [](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/about-performance-monitoring.html?lang=fr){target="_blank"}

>[!NOTE]
>
>Pour Campaign v8 Managed Cloud Services, Adobe surveille et gère l’infrastructure du serveur, le système d’exploitation et la couche applicative. Les fonctions de surveillance décrites sur cette page et ce Panneau de Contrôle sont complémentaires : elles vous donnent une visibilité sur vos données et votre configuration sans avoir besoin d’accéder à l’infrastructure.

## Tracking et reporting {#tracking-reporting}

### Tracking des messages {#message-tracking}

Le tracking enregistre la manière dont les destinataires interagissent avec vos messages après diffusion. Tous les événements suivis sont stockés dans les logs de tracking et sont affichés dans les rapports de diffusion.

- **Ouvertures** — Enregistré lors du chargement du pixel de tracking (e-mail uniquement)
- **Clics** — Enregistré pour chaque lien suivi dans le message
- **Désabonnements** — Demandes d&#39;opt-out via le lien de désabonnement
- **Pages miroir vues** — Destinataires ayant consulté l’e-mail dans un navigateur

En savoir plus sur le [tracking des messages](../send/tracking.md)

### Rapports sur les diffusions {#delivery-reports}

Adobe Campaign fournit un ensemble complet de rapports pour analyser les performances de vos diffusions :

- **Résumé de diffusion** — Présentation des envois, diffusions et échecs d&#39;une diffusion unique
- **Indicateurs de tracking** — Ouvertures, clics et taux de clics publicitaires avec tendance dans le temps
- **URL et flux de clics** — Classement de la plupart des liens cliqués, avec décomptes et pourcentages
- **Position des clics** — Superposition visuelle indiquant l’emplacement où les destinataires ont cliqué dans le corps de l’e-mail

En savoir plus sur les [ rapports de diffusion ](../reporting/delivery-reports.md)

### Rapports globaux {#global-reports}

Accédez aux rapports globaux pour analyser les performances de toutes les campagnes et diffusions :

- **Débit des diffusions** — Messages envoyés par heure pour toutes les diffusions sur une période donnée
- **Échecs et retours** — Répartition des diffusions en échec par type d&#39;échec et par raison
- **Activités utilisateur** — Ouvertures, clics et désabonnements agrégés sur toutes les campagnes

En savoir plus sur les [ rapports globaux ](../reporting/global-reports.md)

## Rubriques connexes {#related-topics}

- [Bonnes pratiques de diffusion](delivery-best-practices.md)
- [Gestion des quarantaines](../send/quarantines.md)
- [Configuration et envoi de diffusions](../send/configure-and-send.md)
- [Prise en main des rapports](../reporting/gs-reporting.md)
