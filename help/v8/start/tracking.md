---
title: Prise en main des fonctionnalités de tracking et de surveillance
description: Prise en main des fonctionnalités de tracking et de surveillance
feature: Overview
role: Data Engineer
level: Beginner
source-git-commit: 76269d65246010af60fda84b388a7c74269e236f
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 100%

---

# Suivi et surveillance des messages{#gs-ac-reports}

## Fonctionnalités de tracking dans Campaign

Les fonctionnalités de tracking de Campaign effectuent le suivi des messages envoyés et vous aident à analyser le comportement des destinataires : ouverture, clics sur les liens, abonnements/désabonnement, etc. Vous pouvez accéder aux journaux, rapports et mesures dédiés, demander la base de données pour examiner les données collectées et bien plus encore.

Pour en savoir plus à ce sujet, consultez la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=fr#tracking-tab){target=&quot;_blank&quot;}.

Le tableau de bord des diffusions est un outil essentiel pour surveiller les diffusions et les erreurs éventuelles rencontrées lors de l&#39;envoi des messages.

Pour en savoir plus à ce sujet consultez la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html?lang=fr#sending-messages){target=&quot;_blank&quot;}.

Les principales fonctionnalités de tracking disponibles dans Campaign sont répertoriées ci-dessous.

### Tracking des messages {#message-tracking}

<img src="assets/do-not-localize/icon-message-tracking.svg" width="60px">

**Liens trackés**

Vous pouvez suivre la réception des messages et l&#39;activation des liens insérés dans le contenu des messages pour mieux comprendre le comportement des destinataires.

[Apprenez-en davantage dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html?lang=fr#sending-messages){target=&quot;_blank&quot;}

**Tracking des URL**

Les options de tracking peuvent être paramétrées en activant ou en désactivant les URL trackées.

[Apprenez-en davantage dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/personalizing-url-tracking.html?lang=fr#sending-messages){target=&quot;_blank&quot;}


**Personnalisation des liens trackés**

Les fonctionnalités de tracking de Campaign vous permettent d&#39;ajouter des liens dans les e-mails, qui peuvent être personnalisés et qui prennent en charge le tracking.

[Apprenez-en davantage dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/tracking-personalized-links/tracking-personalized-links.html?lang=fr#sending-messages){target=&quot;_blank&quot;}

**Logs de tracking**

Le workflow technique de **Tracking** récupère les données de tracking une fois que la diffusion a été envoyée et que le tracking a été activé. Ces données figurent dans l&#39;onglet Tracking de votre diffusion.

[Apprenez-en davantage dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/accessing-the-tracking-logs.html?lang=fr#sending-messages){target=&quot;_blank&quot;}

**Test du tracking**

Avant d&#39;envoyer vos messages avec votre tracking, vous pouvez tester ce dernier sur votre page miroir, vos logs d&#39;e-mail et vos liens.

[Apprenez-en davantage dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/testing-tracking.html?lang=fr#sending-messages){target=&quot;_blank&quot;}

### Tracking des applications web {#web-application-tracking}

<img src="assets/do-not-localize/icon-web-app.svg" width="60px">

**Tracking d&#39;une application web**

Vous pouvez également tracker et mesurer les visites sur les pages d&#39;application web avec des balises de tracking. Cette fonctionnalité peut être utilisée pour tous les types d&#39;application web, tels que les formulaires et les questionnaires en ligne.

[Apprenez-en davantage dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/tracking-a-web-application.html?lang=fr#designing-content){target=&quot;_blank&quot;}

**Désinscription (opt-out) du tracking des applications web**

La désinscription du tracking des applications web vous permet d&#39;arrêter le tracking des comportements web des utilisateurs finaux qui se désinscrivent du tracking comportemental. Vous pouvez inclure la possibilité d&#39;afficher une bannière dans des applications web ou des landing pages pour permettre aux utilisateurs de se désinscrire.

[Apprenez-en davantage dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/web-application-tracking-opt-out.html?lang=fr#designing-content){target=&quot;_blank&quot;}

### Rapports de tracking {#tracking-reports}

<img src="assets/do-not-localize/icon_monitor.svg" width="60px">

**Statistiques de tracking**

Ce rapport fournit des statistiques sur les ouvertures, les clics et les transactions et vous permet de suivre l&#39;impact marketing de la diffusion.

[Apprenez-en davantage dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/about-message-tracking.html?lang=fr#tracking-reports){target=&quot;_blank&quot;}

**URL et flux de clics**

Ce rapport présente la liste des pages visitées suite au lancement d&#39;une diffusion.

[Apprenez-en davantage dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/delivery-reports.html?lang=fr#urls-and-click-streams){target=&quot;_blank&quot;}

**Personnes et destinataires**

À l&#39;aide de cet exemple, comprenez mieux la différence de tracking entre une ou plusieurs personnes et un destinataire dans Adobe Campaign.

[Apprenez-en davantage dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/person-people-recipients.html?lang=fr#reporting){target=&quot;_blank&quot;}

**Indicateurs de tracking**

Ce rapport combine les indicateurs clés pour le tracking du comportement des destinataires à la réception de la diffusion, tels que les taux d&#39;ouverture, de clics publicitaires et les flux de clics.

[Apprenez-en davantage dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/delivery-reports.html?lang=fr#reporting){target=&quot;_blank&quot;}

**Calcul des indicateurs**

Les différents tableaux contiennent la liste des indicateurs utilisés dans les différents rapports et leur formule de calcul en fonction du type de diffusion.

[Apprenez-en davantage dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/indicator-calculation.html?lang=fr#reporting){target=&quot;_blank&quot;}

## Instructions de surveillance

Adobe Campaign vous propose un ensemble de fonctionnalités permettant de surveiller vos processus et votre environnement.

### Surveillance de vos diffusions

La surveillance de vos diffusions après leur envoi est une étape clé pour vous assurer que vos campagnes marketing sont efficaces et atteignent vos clients.

Pour en savoir plus sur les informations que vous pouvez surveiller après l&#39;envoi d&#39;une diffusion et comprendre la gestion des diffusions en échec et des quarantaines, consultez la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=fr#sending-messages){target=&quot;_blank&quot;}

### Surveillance de vos workflows

Découvrez comment surveiller vos diffusions dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html?lang=fr#automating-with-workflows){target=&quot;_blank&quot;}

### Surveillance de votre instance

Les instructions de surveillance des instances sont disponibles dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/introduction/monitoring-guidelines.html?lang=fr#monitoring-campaign-classic){target=&quot;_blank&quot;}

Utilisez l&#39;interface en libre-service du journal d&#39;audit pour surveiller les modifications apportées à votre instance. Le journal d&#39;audit capture, en temps réel, une liste complète d&#39;actions et d&#39;événements se produisant dans votre instance Adobe Campaign. Vous pouvez accéder à un historique des données pour répondre à des questions telles que : ce qui est arrivé à vos workflows et qui les a mis à jour en dernier, ou ce que vos utilisateurs ont fait dans l&#39;instance.

En savoir plus sur le journal d’audit dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/audit-trail.html?lang=fr#accessing-audit-trail){target=&quot;_blank&quot;}
