---
solution: Campaign v8
product: Adobe Campaign
title: Prise en main des fonctionnalités de tracking et de surveillance
description: Prise en main des fonctionnalités de tracking et de surveillance
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
exl-id: 95ed0369-7215-496b-8e11-fe264c436488,e7931de5-83ce-431d-ae81-83793d257550
source-git-commit: ab7e458db5ad5696d144c17f6e89e4437a476d11
workflow-type: tm+mt
source-wordcount: '870'
ht-degree: 81%

---

# Suivi et surveillance des messages{#gs-ac-reports}

## Fonctionnalités de tracking dans Campaign

Les fonctionnalités de tracking de Campaign effectuent le suivi des messages envoyés et vous aident à analyser le comportement des destinataires : ouverture, clics sur les liens, abonnements/désabonnement, etc. Vous pouvez accéder aux journaux, rapports et mesures dédiés, demander la base de données pour examiner les données collectées et bien plus encore.

[!DNL :arrow_upper_right:]  Voir à ce sujet la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/editing-a-profile.html?lang=fr#tracking-tab).

Le tableau de bord des diffusions est un outil essentiel pour surveiller les diffusions et les erreurs éventuelles rencontrées lors de l’envoi des messages.

[!DNL :arrow_upper_right:] Voir à ce propos la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html?lang=fr#sending-messages).

Les principales fonctionnalités de tracking disponibles dans Campaign sont répertoriées ci-dessous.

### Tracking des messages {#message-tracking}

<img src="assets/do-not-localize/icon-message-tracking.svg" width="60px">

**Liens trackés**

Vous pouvez suivre la réception des messages et l’activation des liens insérés dans le contenu des messages pour mieux comprendre le comportement des destinataires.

[!DNL :arrow_upper_right:] [En savoir plus dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html?lang=fr#sending-messages)

**Tracking des URL**

Les options de tracking peuvent être paramétrées en activant ou en désactivant les URL trackées.

[!DNL :arrow_upper_right:] [En savoir plus dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/personalizing-url-tracking.html?lang=fr#sending-messages)


**Personnalisation des liens trackés**

Les fonctionnalités de tracking de Campaign vous permettent d’ajouter des liens dans les e-mails, qui peuvent être personnalisés et qui prennent en charge le tracking.

[!DNL :arrow_upper_right:] [En savoir plus dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/tracking-personalized-links/tracking-personalized-links.html?lang=fr#sending-messages)

**Logs de tracking**

Le workflow technique de **Tracking** récupère les données de tracking une fois que la diffusion a été envoyée et que le tracking a été activé. Ces données figurent dans l’onglet Tracking de votre diffusion.

[!DNL :arrow_upper_right:] [En savoir plus dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/accessing-the-tracking-logs.html?lang=fr#sending-messages)

**Test du tracking**

Avant d’envoyer vos messages avec votre tracking, vous pouvez tester ce dernier sur votre page miroir, vos logs d’e-mail et vos liens.

[!DNL :arrow_upper_right:] [En savoir plus dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/testing-tracking.html?lang=fr#sending-messages)

### Tracking des applications web {#web-application-tracking}

<img src="assets/do-not-localize/icon-web-app.svg" width="60px">

**Tracking d’une application web**

Vous pouvez également tracker et mesurer les visites sur les pages d’application web avec des balises de tracking. Cette fonctionnalité peut être utilisée pour tous les types d’application web, tels que les formulaires et les questionnaires en ligne.

[!DNL :arrow_upper_right:] [En savoir plus dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/tracking-a-web-application.html?lang=fr#designing-content)

**Désinscription (opt-out) du tracking des applications web**

La désinscription du tracking des applications web vous permet d’arrêter le tracking des comportements web des utilisateurs finaux qui se désinscrivent du tracking comportemental. Vous pouvez inclure la possibilité d’afficher une bannière dans des applications web ou des landing pages pour permettre aux utilisateurs de se désinscrire.

[!DNL :arrow_upper_right:] [En savoir plus dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/web-application-tracking-opt-out.html?lang=fr#designing-content)

### Rapports de tracking {#tracking-reports}

<img src="assets/do-not-localize/icon_monitor.svg" width="60px">

**Statistiques de tracking**

Ce rapport fournit des statistiques sur les ouvertures, les clics et les transactions et vous permet de suivre l’impact marketing de la diffusion.

[!DNL :arrow_upper_right:] [En savoir plus dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/about-message-tracking.html?lang=fr#tracking-reports)

**URL et flux de clics**

Ce rapport présente la liste des pages visitées suite au lancement d’une diffusion.

[!DNL :arrow_upper_right:] [En savoir plus dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/delivery-reports.html?lang=fr#urls-and-click-streams)

**Personnes et destinataires**

À l’aide de cet exemple, comprenez mieux la différence de tracking entre une ou plusieurs personnes et un destinataire dans Adobe Campaign.

[!DNL :arrow_upper_right:] [En savoir plus dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/person-people-recipients.html?lang=fr#reporting)

**Indicateurs de tracking**

Ce rapport combine les indicateurs clés pour le tracking du comportement des destinataires à la réception de la diffusion, tels que les taux d’ouverture, de clics publicitaires et les flux de clics.

[!DNL :arrow_upper_right:] [En savoir plus dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/delivery-reports.html?lang=fr#reporting)

**Calcul des indicateurs**

Les différents tableaux contiennent la liste des indicateurs utilisés dans les différents rapports et leur formule de calcul en fonction du type de diffusion.

[!DNL :arrow_upper_right:] [En savoir plus dans la documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/reports-on-deliveries/indicator-calculation.html?lang=fr#reporting)

## Instructions de surveillance

Adobe Campaign vous propose un ensemble de fonctionnalités permettant de surveiller vos processus et votre environnement.

### Surveillance de vos diffusions

La surveillance de vos diffusions après leur envoi est une étape clé pour vous assurer que vos campagnes marketing sont efficaces et atteignent vos clients.

[!DNL :arrow_upper_right:] En savoir plus sur les informations que vous pouvez surveiller après l&#39;envoi d&#39;une diffusion, comprendre comment les échecs de diffusion et les mises en quarantaine sont gérés dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-delivery-monitoring.html?lang=fr#sending-messages)

### Surveillance de vos workflows

[!DNL :arrow_upper_right:] Découvrez comment surveiller l’exécution des workflows dans la documentation de   [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html?lang=fr#automating-with-workflows)

### Surveillance de votre instance

[!DNL :arrow_upper_right:] Des instructions relatives à la surveillance des instances sont disponibles dans la documentation de  [Campaign Classic v7.](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/introduction/monitoring-guidelines.html?lang=fr#monitoring-campaign-classic)

Utilisez l’interface en libre-service du journal d’audit pour surveiller les modifications apportées à votre instance. Le journal d’audit capture, en temps réel, une liste complète d’actions et d’événements se produisant dans votre instance Adobe Campaign. Vous pouvez accéder à un historique des données pour répondre à des questions telles que : ce qui est arrivé à vos workflows et qui les a mis à jour en dernier, ou ce que vos utilisateurs ont fait dans l’instance.

[!DNL :arrow_upper_right:] En savoir plus sur le Suivi dans la documentation de   [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/audit-trail.html?lang=fr#accessing-audit-trail)
