---
product: campaign
title: Surveiller la délivrabilité dans Adobe Campaign
description: Découvrez les outils et les instructions concernant la surveillance de la délivrabilité dans Adobe Campaign.
feature: Deliverability
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: e4caa316-242f-46cd-a20b-a5eee5a0c456
source-git-commit: 11c8c4c51c7901ba0d119323c564a64b940428b7
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 67%

---

# Suivi de votre délivrabilité{#monitoring-deliverability}

Vous trouverez ci-dessous des détails sur les différents outils de surveillance fournis par Adobe Campaign, ainsi que des directives supplémentaires sur l’exploitation des fonctionnalités offertes par Adobe Campaign pour surveiller la délivrabilité de votre plateforme.

## Outils de surveillance {#monitoring-tools}

Adobe Campaign vous donne accès à tous les outils de délivrabilité répertoriés ci-dessous.

* Le [rapport d&#39;Inbox rendering](inbox-rendering.md) vous permet de prévisualiser vos messages sur les principaux clients de messagerie afin d&#39;analyser le contenu et la réputation.

* Rapport **[!UICONTROL Débit de diffusion]**, qui donne une vue d’ensemble du débit global de la plateforme pour une période donnée. Voir à ce propos [cette section](../reporting/global-reports.md#delivery-throughput).
* Chaque diffusion génère un rapport de statistiques de diffusion pour les différents fournisseurs d’accès à internet (FAI). Il présente certaines mesures de réputation et de qualité des données qui peuvent avoir un impact sur votre délivrabilité, notamment les chiffres suivants :
   * **[!UICONTROL Rebonds définitifs]**, qui indiquent la qualité des données. Ce chiffre doit être inférieur à 2 %.
   * **[!UICONTROL Rebonds temporaires]**, qui indiquent la réputation. Cette valeur ne doit pas être supérieure à 10 % pour un fournisseur d’accès à internet donné.

  <!--For more on this, see the [Delivery statistics](../reporting/global-reports.md#delivery-statistics) section.-->

* Plus généralement, le [tableau de bord des diffusions](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html?lang=fr#sending-messages){target="_blank"} donne accès aux éléments suivants :
   * le résumé de la diffusion, qui indique le détail de l’envoi et le nombre de messages à envoyer, traités et envoyés avec succès ;
   * les logs et l&#39;historique des diffusions, qui indiquent la cible exclue et les raisons de l&#39;exclusion ;
   * les logs de tracking, qui affichent des informations de tracking telles que les ouvertures et les clics.

## Instructions de surveillance {#monitoring-guidelines}

Voici quelques directives supplémentaires concernant la supervision de la délivrabilité :

* Vérifiez régulièrement le [débit des diffusions](../reporting/global-reports.md#delivery-throughput) pour l’ensemble de la plateforme afin de contrôler qu’il correspond à la configuration d’origine.
* Vérifiez que les [reprises](delivery-failures.md#retries) sont paramétrées correctement (30 minutes pour la période des reprises et plus de 20 reprises) dans les modèles de diffusion.
* Vérifiez régulièrement que la boîte des [emails rebonds](delivery-failures.md#bounce-mail-qualification) est accessible et que le compte n’arrive pas à expiration.
* Vérifiez chaque débit de diffusion, accessible à partir du [tableau de bord de diffusion](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html?lang=fr#sending-messages){target="_blank"}, pour vous assurer qu&#39;il est cohérent avec la validité du contenu de la diffusion (par exemple, les « ventes flash » doivent être diffusées en minutes, et non en jours). est un outil essentiel pour surveiller les diffusions et les problèmes potentiels rencontrés lors de l’envoi des messages.
* Lors de l’utilisation des [vagues](configure-and-send.md#sending-using-multiple-waves), vérifiez que chaque vague a le temps de se terminer avant le déclenchement de la suivante.
* Vérifiez que le nombre d’erreurs et les [mises en quarantaine](quarantines.md) correspondent aux autres diffusions.
* Consultez attentivement les [logs de diffusion](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/delivery-dashboard.html#delivery-logs-and-history){target="_blank"} pour déterminer le type des erreurs indiquées (listes bloquées, problèmes liés aux DNS, règles anti-spam, etc.).
