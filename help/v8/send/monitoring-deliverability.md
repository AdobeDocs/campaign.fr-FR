---
product: campaign
title: Surveiller la délivrabilité dans Adobe Campaign
description: Découvrez les outils et les instructions concernant la surveillance de la délivrabilité dans Adobe Campaign.
feature: Deliverability
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: e4caa316-242f-46cd-a20b-a5eee5a0c456
source-git-commit: 3dd4f6041ef193a0d7ea74a0b2c06183861c2797
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 56%

---

# Suivi de votre délivrabilité{#monitoring-deliverability}

Vous trouverez ci-dessous des détails sur les différents outils de surveillance fournis par Adobe Campaign, ainsi que des directives supplémentaires sur l’exploitation des fonctionnalités offertes par Adobe Campaign pour surveiller la délivrabilité de votre plateforme.

## Outils de surveillance {#monitoring-tools}

Adobe Campaign vous donne accès aux outils de délivrabilité répertoriés ci-dessous.

### Rendu de la boîte de réception {#inbox-rendering-tool}

Le [rapport d&#39;Inbox rendering](inbox-rendering.md) vous permet de prévisualiser vos messages sur les principaux clients de messagerie afin d&#39;analyser le contenu et la réputation.

### Débit des diffusions {#throughput-reports}

Rapport **[!UICONTROL Débit de diffusion]**, qui donne une vue d’ensemble du débit global de la plateforme pour une période donnée. Voir à ce propos [cette section](../reporting/global-reports.md#delivery-throughput).

### Statistiques de domaine {#broadcast-statistics}

Chaque diffusion génère un rapport de statistiques de diffusion pour les différents fournisseurs d’accès à internet (FAI). Il présente certaines mesures de réputation et de qualité des données qui peuvent avoir un impact sur votre délivrabilité, notamment les chiffres suivants :

**[!UICONTROL Rebonds définitifs]**, qui indiquent la qualité des données. Ce chiffre doit être inférieur à 2 %.

**[!UICONTROL Rebonds temporaires]**, qui indiquent la réputation. Cette valeur ne doit pas être supérieure à 10 % pour un fournisseur d’accès à internet donné.

<!--For more on this, see the [Delivery statistics](../reporting/global-reports.md#delivery-statistics) section.-->

### Tableau de bord de la diffusion {#delivery-dashboard-monitoring}

Plus généralement, le [tableau de bord des diffusions](delivery-dashboard.md) donne accès aux éléments suivants :

La synthèse de la diffusion, qui affiche le détail de l’envoi et le nombre de messages à envoyer, traités et envoyés avec succès.

Les logs et l’historique de diffusion, qui indiquent la cible exclue et pourquoi.

Les logs de tracking, qui affichent des informations de tracking telles que les ouvertures et les clics.

### Test de SpamAssassin {#spam-testing}

Utilisez [SpamAssassin](spamassassin.md) pour tester le contenu de votre email et lui attribuer une note, afin de déterminer si un message risque d&#39;être considéré comme indésirable par les outils anti-spams utilisés à sa réception.

### Panneau de contrôle {#control-panel-monitoring}

>[!NOTE]
>
>Le Panneau de Contrôle est disponible pour les utilisateurs de Campaign v8 Managed Cloud Services. En savoir plus sur le [Panneau de contrôle](../config/self-service.md).

Le Panneau de Contrôle [de Campaign](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=fr){target="_blank"} fournit des fonctionnalités de surveillance de la délivrabilité, notamment la gestion des sous-domaines et des certificats, la surveillance des profils actifs, ainsi que les mesures de débit et de latence des diffusions.

## Instructions de surveillance {#monitoring-guidelines}

Voici quelques directives supplémentaires concernant la supervision de la délivrabilité :

### Surveillance du débit de Platform

Vérifiez régulièrement le [débit des diffusions](../reporting/global-reports.md#delivery-throughput) pour l’ensemble de la plateforme afin de contrôler qu’il correspond à la configuration d’origine.

### Reprise de la configuration

Vérifiez que les [reprises](delivery-failures.md#retries) sont paramétrées correctement (30 minutes pour la période des reprises et plus de 20 reprises) dans les modèles de diffusion.

### Vérification des boîtes de réception de rebond

Vérifiez régulièrement que la boîte des [emails rebonds](delivery-failures.md#bounce-mail-qualification) est accessible et que le compte n’arrive pas à expiration.

### Contrôles des performances de diffusion

Vérifiez chaque débit de diffusion, accessible à partir du [tableau de bord de diffusion](delivery-dashboard.md), pour vous assurer qu’il correspond à la validité du contenu de la diffusion (par exemple, les ventes Flash doivent être diffusées en quelques minutes et non en plusieurs jours).

### Validation du minutage des vagues

Lors de l’utilisation des [vagues](configure-and-send.md#sending-using-multiple-waves), vérifiez que chaque vague a le temps de se terminer avant le déclenchement de la suivante.

### Surveillance des quarantaines

Vérifiez que le nombre d’erreurs et les nouvelles [mises en quarantaine](quarantines.md) correspondent aux autres diffusions.

### Analyse des logs de diffusion

Consultez attentivement les [logs de diffusion](delivery-dashboard.md#delivery-logs-and-history) pour déterminer le type des erreurs indiquées (listes bloquées, problèmes liés aux DNS, règles anti-spam, etc.).

## Rubriques connexes

[Guide des bonnes pratiques relatives à la délivrabilité d&#39;Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=fr){target="_blank"} fournit des conseils complets sur la stratégie, la définition, les mesures et les bonnes pratiques en matière de délivrabilité.

[Qu&#39;est-ce que la délivrabilité &#x200B;](about-deliverability.md) présente les concepts clés de la délivrabilité et comment améliorer votre taux de délivrabilité dans Campaign.

[Échecs et retours de diffusion](delivery-failures.md) décrit les différents types d’échecs de diffusion, la manière dont Campaign les gère et inclut des conseils de dépannage pour les problèmes courants.

[Gestion des quarantaines](quarantines.md) explique comment Campaign gère les adresses en quarantaine pour protéger votre réputation d’envoi.

[Contrôler le contenu du message](control-message-content.md) fournit des conseils sur la manière de s’assurer que votre contenu est optimisé pour la délivrabilité.
