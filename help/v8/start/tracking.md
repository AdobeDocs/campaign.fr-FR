---
solution: Campaign Classic
product: campaign
title: Prise en main des fonctionnalités de suivi et de surveillance
description: Prise en main des fonctionnalités de suivi et de surveillance
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
exl-id: 95ed0369-7215-496b-8e11-fe264c436488,e7931de5-83ce-431d-ae81-83793d257550
translation-type: tm+mt
source-git-commit: 2fd86324b34b7a7d1e1cb36d1073b5adc24ebda7
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 36%

---

# Suivi et surveillance des messages{#gs-ac-reports}

## Fonctionnalités de suivi dans Campaign

Les fonctionnalités de suivi Campaign permettent de suivre les messages envoyés et vous aident à analyser le comportement des destinataires : ouverture, clics sur des liens, abonnements/désinscription, etc. Vous pouvez accéder aux journaux, rapports et mesures dédiés, requête de la base de données pour examiner les données collectées, etc.

:flèche_supérieur_droite :  Pour en savoir plus sur ce sujet, consultez la [documentation Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=en#tracking-tab).

Le tableau de bord de diffusion est un outil clé pour surveiller vos diffusions et les problèmes potentiels lors de l&#39;envoi de messages.

:flèche_supérieur_droite : Pour en savoir plus sur ce sujet, consultez la [documentation Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html?lang=en#sending-messages).

Les principales fonctionnalités de suivi disponibles dans Campaign sont énumérées ci-dessous.

### Tracking des messages {#message-tracking}

<img src="assets/do-not-localize/icon-message-tracking.svg" width="60px">

**Liens trackés**

Vous pouvez tracker la réception des messages et l’activation des liens insérés dans le contenu du message pour mieux comprendre le comportement des destinataires.

:flèche_supérieur_droite : [En savoir plus dans la documentation Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html?lang=en#sending-messages)

**Tracking des URL**

Les options de tracking peuvent être paramétrées en activant ou en désactivant les URL trackées.

:flèche_supérieur_droite : [En savoir plus dans la documentation Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/personalizing-url-tracking.html?lang=en#sending-messages)


**Personnalisation des liens trackés**

Les fonctionnalités de tracking de Campaign vous permettent d’ajouter des liens dans les emails qui peuvent être personnalisés et qui prennent en charge le tracking.

:flèche_supérieur_droite : [En savoir plus dans la documentation Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/tracking-personalized-links/tracking-personalized-links.html?lang=en#sending-messages)

**Logs de tracking**

Le processus technique **Suivi** récupère les données de suivi une fois la diffusion envoyée et le suivi activé. Ces données figurent dans l’onglet Tracking de votre diffusion.

:flèche_supérieur_droite : [En savoir plus dans la documentation Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/accessing-the-tracking-logs.html?lang=en#sending-messages)

**Tester le tracking**

Avant d’envoyer vos messages avec votre tracking, vous pouvez tester ce dernier sur votre page miroir, vos logs d&#39;email et vos liens.

:flèche_supérieur_droite : [En savoir plus dans la documentation Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/testing-tracking.html?lang=en#sending-messages)

### Tracking des applications web {#web-application-tracking}

<img src="assets/do-not-localize/icon-web-app.svg" width="60px">

**Tracking d’une application web**

Vous pouvez également tracker et mesurer les visites sur les pages d’application web avec des balises de tracking. Cette fonctionnalité peut être utilisée pour tous les types d’application web, tels que les formulaires et les questionnaires en ligne.

:flèche_supérieur_droite : [En savoir plus dans la documentation Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/tracking-a-web-application.html?lang=en#designing-content)

**Désinscription (opt-out) du tracking des applications web**

La désinscription du tracking des applications web vous permet d’arrêter le tracking des comportements web des utilisateurs finaux qui se désinscrivent du tracking comportemental. Vous pouvez inclure la possibilité d’afficher une bannière dans des applications web ou des landing pages pour permettre aux utilisateurs de se désinscrire.

:flèche_supérieur_droite : [En savoir plus dans la documentation Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/web-application-tracking-opt-out.html?lang=en#designing-content)

### Rapports de tracking {#tracking-reports}

<img src="assets/do-not-localize/icon_monitor.svg" width="60px">

**Statistiques de tracking**

Ce rapport fournit des statistiques sur les ouvertures, les clics et les transactions et vous permet de suivre l&#39;impact marketing de la diffusion.

:flèche_supérieur_droite : [En savoir plus dans la documentation Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/about-message-tracking.html?lang=en#tracking-reports)

**URL et flux de clics (URLs and click streams)**

Ce rapport présente le palmarès des pages visitées suite au lancement d&#39;une diffusion.

:flèche_supérieur_droite : [En savoir plus dans la documentation Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/delivery-reports.html?lang=en#urls-and-click-streams)

**Personnes et destinataires**

Comprenez la différence de tracking entre une personne/plusieurs personnes et un destinataire dans Adobe Campaign avec cet exemple.

:flèche_supérieur_droite : [En savoir plus dans la documentation Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/person-people-recipients.html?lang=en#reporting)

**Indicateurs de tracking**

Ce rapport combine les indicateurs clés pour le tracking du comportement des destinataires à la réception de la diffusion, tels que les taux d&#39;ouverture, de clics publicitaires et de flux de clics.

:flèche_supérieur_droite : [En savoir plus dans la documentation Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/delivery-reports.html?lang=en#reporting)

**Calcul des indicateurs**

Les différents tableaux contiennent la liste des indicateurs utilisés dans les différents rapports et leur formule de calcul en fonction du type de diffusion.

:flèche_supérieur_droite : [En savoir plus dans la documentation Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/indicator-calculation.html?lang=en#reporting)

## Directives de supervision

Adobe Campaign offre un ensemble de fonctionnalités permettant de surveiller vos processus et votre environnement.

### Surveiller vos diffusions

La surveillance de vos diffusions après leur envoi est une étape clé pour vous assurer que vos campagnes marketing sont efficaces et atteignent vos clients.

:flèche_supérieur_droite : En savoir plus sur les informations que vous pouvez surveiller après l’envoi d’une diffusion, comprendre comment les échecs de diffusion et les quarantaines sont gérés dans [la documentation Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=en#sending-messages)

### Surveiller vos workflows

:flèche_supérieur_droite : Découvrez comment surveiller l&#39;exécution du processus dans [la documentation du Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html?lang=en#automating-with-workflows)

### Surveiller votre instance

:flèche_supérieur_droite : Les instructions de surveillance des instances sont disponibles dans la [documentation Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/introduction/monitoring-guidelines.html?lang=en#monitoring-campaign-classic)

Utilisez l’interface en libre-service de la piste d’audit pour surveiller les modifications apportées à votre instance. La piste d’audit capture, en temps réel, une liste complète d’actions et de événements survenant dans votre instance Adobe Campaign. Vous pouvez accéder à un historique des données pour répondre à des questions telles que : ce qui est arrivé à vos workflows et qui les a mis à jour en dernier ou ce que vos utilisateurs ont fait dans l’instance.

:flèche_supérieur_droite : Pour en savoir plus sur la piste d’audit, consultez la [documentation Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/audit-trail.html?lang=en#accessing-audit-trail).
