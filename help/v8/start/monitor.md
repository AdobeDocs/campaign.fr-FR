---
title: Présentation de la surveillance des campagnes
description: Découvrez comment surveiller les diffusions, les workflows et votre instance Campaign
feature: Monitoring
role: User
level: Beginner
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '1066'
ht-degree: 4%

---

# Présentation de la surveillance des campagnes {#monitor-campaign}

Adobe Campaign offre un ensemble complet de fonctionnalités permettant de surveiller vos processus, diffusions et environnements afin d’assurer des performances optimales et de résoudre les problèmes de manière proactive.

>[!NOTE]
>
>En tant qu’administrateur Campaign, vous pouvez également utiliser le [Panneau de Contrôle Campaign](#control-panel) pour surveiller vos instances, gérer les performances et configurer les paramètres avec des fonctionnalités en libre-service.

## Surveillance de vos diffusions {#monitor-deliveries}

La surveillance de vos diffusions après leur envoi est une étape clé pour vous assurer que vos campagnes marketing sont efficaces et atteignent vos clients. Après l’envoi d’une diffusion, vous pouvez surveiller son statut et suivre les mesures clés dans le tableau de bord de diffusion. Le tableau de bord permet d’accéder aux logs de diffusion, aux logs d’exclusion, aux logs de tracking et à d’autres fonctionnalités de surveillance pour vous aider à analyser les performances de votre diffusion sur tous les canaux.

**Diffusions e-mail** - Surveillez le statut de diffusion des e-mails, suivez les mesures clés et accédez à des journaux détaillés. En savoir plus sur la [surveillance des diffusions dans l’interface utilisateur de Campaign](../send/delivery-dashboard.md), [les statuts de diffusion](../send/delivery-statuses.md) et [surveillance des diffusions par e-mail](../send/send.md#email-monitoring).

**Diffusions SMS** - Suivez le statut des diffusions SMS et surveillez les mesures clés dans le tableau de bord des diffusions SMS. En savoir plus sur la [surveillance des SMS](../send/sms/sms-monitor.md).

**Notifications push** - Surveillez les diffusions de notifications push pour vous assurer qu&#39;elles atteignent efficacement les utilisateurs de vos applications mobiles. En savoir plus sur la [surveillance des notifications push](../send/push.md#push-test).

**Messages transactionnels** - Pour les messages déclenchés par des événements, surveillez l’état du traitement des événements, l’exécution des messages et l’état de la diffusion. En savoir plus sur la [surveillance des messages transactionnels](../send/delivery-execution.md#monitor-messages).

**Diffusions en échec** - Il est essentiel de comprendre les raisons de l’échec d’une diffusion pour maintenir une base de données propre et garantir de bons taux de délivrabilité. Les échecs de diffusion sont classés en erreurs hard, erreurs soft et messages ignorés. En savoir plus sur les [diffusions en échec et mises en quarantaine](../send/delivery-failures.md).

## Surveillance de la délivrabilité {#monitor-deliverability}

La surveillance de la délivrabilité vous permet de vous assurer que vos messages atteignent les boîtes de réception de vos destinataires et évitent les filtres de spam. Adobe Campaign fournit plusieurs outils intégrés pour surveiller et améliorer la délivrabilité, notamment les rapports de diffusion, l’inbox rendering, les tests SpamAssassin et les statistiques de diffusion. Le respect des bonnes pratiques de délivrabilité, telles que la maintenance d&#39;une liste d&#39;emails propre, la surveillance de la réputation de l&#39;expéditeur et l&#39;authentification des domaines d&#39;envoi, est essentiel pour maintenir de bons taux de délivrabilité.

Découvrez les [outils de surveillance de la délivrabilité](../send/monitoring-deliverability.md) et [bonnes pratiques en matière de délivrabilité](../send/about-deliverability.md).

## Surveiller les workflows {#monitor-workflows}

Les workflows sont essentiels pour automatiser vos campagnes marketing et le traitement des données. La surveillance de l’exécution des workflows vous permet d’effectuer les opérations suivantes :

* S’assurer que les workflows sont terminés avec succès
* Identification et résolution des erreurs
* Optimisation des performances des workflows

### Fonctionnalités de surveillance des workflows {#workflow-monitoring}

**Surveillez les éléments de workflow suivants :**

**Statut d’exécution du workflow** - Vérifiez si les workflows sont en cours d’exécution, en pause, en échec ou terminés. [En savoir plus sur l’exécution des workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/monitor-workflow-execution.html?lang=fr){target="_blank"}

**Journaux d’exécution des activités** - Accédez aux journaux détaillés de chaque activité de workflow pour résoudre les problèmes et optimiser les performances.

**Carte thermique des workflows** - Visualisez les modèles d’exécution des workflows, identifiez les goulets d’étranglement et surveillez les workflows simultanés. La Carte thermique des workflows est disponible pour les administrateurs et administratrices de Campaign. [En savoir plus sur la carte thermique des workflows](https://experienceleague.adobe.com/docs/campaign/automation/workflows/monitoring-workflows/heatmap.html?lang=fr){target="_blank"}

**Historique des workflows** - Suivez toutes les exécutions et modifications de workflows au fil du temps pour comprendre leur comportement et leurs performances.

## Surveiller votre instance {#monitor-instance}

La surveillance des instances permet d’assurer l’intégrité et les performances de votre environnement Adobe Campaign.

### Journal d’audit {#audit-trail}

L&#39;interface en libre-service du journal d&#39;audit vous permet de surveiller les modifications apportées à votre instance Adobe Campaign. Le journal d&#39;audit capture, en temps réel, une liste complète d&#39;actions et d&#39;événements se produisant dans votre instance.

**Utiliser le journal d’audit pour :**

* **Suivi des modifications des composants** : surveillez ce qui est arrivé à vos workflows, schémas, options et autres composants
* **Identifier les personnes qui ont apporté des modifications** : voir qui a mis à jour un élément spécifique pour la dernière fois et quand
* **Comprendre les actions des utilisateurs** : vérifiez ce que les utilisateurs ont fait dans l’instance à des fins de dépannage ou d’audit
* **Maintenir la conformité** : suivez toutes les modifications apportées à la configuration à des fins de conformité et de sécurité.

Le journal d’audit est accessible via la console cliente Campaign et fournit des informations détaillées sur les actions effectuées par les utilisateurs.

En savoir plus sur le [Journal d’audit](../reporting/audit-trail.md)

### Suivi des performances {#performance-monitoring}

Campaign v8 fournit plusieurs fonctionnalités de surveillance pour suivre les performances de votre instance et garantir un fonctionnement optimal :

**Surveillance de la base de données** - Surveillez l’utilisation et la capacité de la base de données par Panneau de Contrôle pour assurer une gestion optimale des performances et du stockage. [En savoir plus sur la surveillance des bases de données](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/database-monitoring.html){target="_blank"}

**Surveillance des profils actifs** - Effectuez le suivi de l’utilisation des profils actifs par rapport à vos limites contractuelles pour maintenir la conformité et optimiser l’affectation des ressources. [En savoir plus sur les profils actifs](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=fr){target="_blank"}

**Surveillance des workflows** - Surveillez le statut d’exécution des workflows pour identifier les workflows de longue durée et vérifier que tous les workflows techniques s’exécutent correctement. [En savoir plus sur les workflows techniques](#technical-workflows)

**Débit de diffusion et latence** - Effectuez le suivi du débit de diffusion (messages envoyés par heure) et de la latence pour les communications transactionnelles par Panneau de Contrôle. [En savoir plus sur la surveillance du débit](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/throughputs-latencies.html){target="_blank"}

>[!NOTE]
>
>Pour Campaign v8 Managed Cloud Services, l’infrastructure du serveur (CPU, mémoire, disque) est surveillée et gérée par Adobe.

### Workflows techniques {#technical-workflows}

Les workflows techniques sont des processus essentiels qui s’exécutent en arrière-plan pour gérer votre instance Campaign.

**Vérifiez que les workflows techniques sont les suivants :**

* Exécution selon le calendrier
* Fin réussie sans erreur
* Traitement correct des données

**Workflows techniques clés à surveiller :**

| Workflow | Intérêt |
|----------|---------|
| **Effectuer un tracking** | Traite les données de tracking des diffusions email |
| **Nettoyage** | Supprime les anciennes données et journaux pour maintenir les performances de la base de données |
| **Mise à jour délivrabilité** | Met à jour les règles de délivrabilité et les modèles de filtre anti-spam |
| **Nettoyage de la base de données** | Purge les anciens logs de tracking et de diffusion |

En savoir plus sur les [workflows techniques](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html?lang=fr){target="_blank"}

### Panneau de contrôle Campaign {#control-panel}

Le Panneau de Contrôle Campaign permet aux administrateurs de surveiller et de gérer des instances Campaign en libre-service.

| Type de surveillance | Fonctionnalités |
|-----------------|--------------|
| **Performances** | Suivre l’utilisation des profils actifs, surveiller l’utilisation et la capacité des bases de données, afficher le statut d’exécution des workflows, surveiller le débit de diffusion et la latence |
| **Infrastructure** | Surveiller la capacité de stockage SFTP, suivre la configuration des sous-domaines, surveiller l’expiration des certificats SSL, gérer les listes autorisées d’adresses IP |
| **Instance** | Afficher la version de build et les packages installés, surveiller la configuration du système, gérer les domaines externes autorisés |

En savoir plus sur la surveillance des performances des Panneau de Contrôle Panneaux de Contrôle [&#128279;](../config/self-service.md) et [&#128279;](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/about-performance-monitoring.html?lang=fr){target="_blank"}

>[!NOTE]
>
>Pour Campaign v8 Managed Cloud Services, Adobe surveille et gère l’infrastructure du serveur, le système d’exploitation et la couche applicative. Vous pouvez utiliser les fonctionnalités de surveillance décrites sur cette page et dans ce Panneau de Contrôle pour surveiller les performances de votre instance, les workflows et les diffusions.

## Tracking et reporting {#tracking-reporting}

### Tracking des messages {#message-tracking}

Suivez le comportement des destinataires et mesurez l’efficacité de vos campagnes :

* **Ouvertures** : suivez le moment où les destinataires ouvrent vos e-mails
* **Clics** : surveiller les liens sur lesquels cliquent les destinataires
* **Désabonnements** : suivi des demandes d’exclusion
* **Pages miroir vues** : déterminez le nombre de destinataires qui consultent votre e-mail dans un navigateur

En savoir plus sur le [tracking des messages](../send/tracking.md)

### Rapports de diffusion {#delivery-reports}

Adobe Campaign fournit un ensemble complet de rapports pour analyser les performances de vos diffusions :

* **Résumé de diffusion** : présentation des envois, diffusions et échecs
* **Indicateurs de tracking** : ouvertures, clics et taux de clics publicitaires
* **URL et flux de clics** : liens les plus populaires dans vos diffusions
* **Position des clics** : représentation visuelle de l’emplacement où les destinataires ont cliqué dans votre e-mail

En savoir plus sur les [&#x200B; rapports de diffusion &#x200B;](../reporting/delivery-reports.md)

### Rapports globaux {#global-reports}

Accédez aux rapports globaux pour analyser les performances de toutes les campagnes et diffusions :

* **Débit de diffusion** : messages envoyés au fil du temps
* **Échecs et retours** : analyse des diffusions en échec
* **Activités utilisateur** : s’ouvre, clique et se désabonne dans toutes les campagnes

En savoir plus sur les [&#x200B; rapports globaux &#x200B;](../reporting/global-reports.md)

## Rubriques connexes {#related-topics}

* [Bonnes pratiques de diffusion](delivery-best-practices.md)
* [Gestion des quarantaines](../send/quarantines.md)
* [Configuration et envoi de diffusions](../send/configure-and-send.md)
* [Commencer avec les rapports](../reporting/gs-reporting.md)

