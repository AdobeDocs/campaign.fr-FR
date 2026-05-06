---
title: Rapports globaux d’Adobe Campaign
description: Découvrez comment accéder aux rapports globaux et les utiliser.
feature: Reporting, Monitoring
role: User, Developer
exl-id: 6e3409d8-86bd-44ba-a40d-10287f53a960
source-git-commit: a5436f7e1f1e4ad86157dfd8943d51bf852b747c
workflow-type: tm+mt
source-wordcount: '1914'
ht-degree: 78%

---

# Rapports globaux {#global-reports}

Ces rapports concernent l’activité des données dans l’ensemble de la base de données. Pour afficher le tableau de bord des rapports, accédez à l’onglet **[!UICONTROL Rapports]**.

![](assets/reports-tab.png)

Pour afficher les rapports, cliquez sur leur nom. Les rapports disponibles par défaut sont les suivants :

![](assets/report-global-list.png)

>[!NOTE]
>
>Cette section présente uniquement les rapports liés aux diffusions.

* **[!UICONTROL Débit de diffusion]** : voir [Débit des diffusions](#delivery-throughput).
* **[!UICONTROL Navigateurs]** : voir [Navigateurs](#browsers).
* **[!UICONTROL Partage vers les réseaux sociaux]** : voir [Partage vers les réseaux sociaux](#sharing-to-social-networks).
* **[!UICONTROL Statistiques des activités de partage]** : voir [Statistiques des activités de partage](#statistics-on-sharing-activities).
* **[!UICONTROL Systèmes d’exploitation]** : voir [Systèmes d’exploitation](#operating-systems).
* **[!UICONTROL URL et flux de clics]** : voir [URL et flux de clics](delivery-reports.md#urls-and-click-streams).
* **[!UICONTROL Indicateurs de tracking]** : voir [Indicateurs de tracking](delivery-reports.md#tracking-indicators).
* **[!UICONTROL Non-délivrables et rebonds]** : voir [Non-délivrables et rebonds](#non-deliverables-and-bounces).
* **[!UICONTROL Activités utilisateurs et utilisatrices]** : voir [Activités utilisateurs et utilisatrices](#user-activities).
* **[!UICONTROL Suivi des abonnements]** : voir [Suivi des abonnements](#subscription-tracking).
* **[!UICONTROL Synthèse des diffusions]** : voir [Synthèse des diffusions](delivery-reports.md#delivery-summary).
* **[!UICONTROL Statistiques de diffusion]** : voir [Statistiques de diffusion](#delivery-statistics).
* **[!UICONTROL Répartition des ouvertures]** : voir [Répartition des ouvertures](#breakdown-of-opens).

## Débit des diffusions {#delivery-throughput}

Ce rapport contient des informations sur le débit de diffusion de l&#39;ensemble de la plateforme sur une période donnée. Pour mesurer la vitesse à laquelle les messages sont diffusés, les critères sont le nombre de messages envoyés par heure et la taille des messages (en bits par seconde). Dans l’exemple ci-dessous, le premier graphique indique les diffusions réussies en bleu et le nombre de diffusions erronées en orange.

![](assets/report-toolbar.png)

Vous pouvez paramétrer l&#39;affichage des valeurs en sélectionnant le périmètre de la vue : 1 heure, 3 heures, 24 heures, etc. Cliquez sur **[!UICONTROL Actualiser]** pour confirmer votre sélection.

>[!NOTE]
>
>Vous pouvez également surveiller le nombre de diffusions envoyées par heure dans le [Panneau de contrôle](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/sftp-storage-management.html?lang=fr){target="_blank"}.
>
>Le Panneau de contrôle est accessible à tous les utilisateurs administrateurs. Les étapes permettant d&#39;octroyer un accès administrateur à un utilisateur sont présentées sur [cette page](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=fr#discover-control-panel){target="_blank"}.
>

## Activités utilisateurs {#user-activities}

Ce rapport présente la répartition des ouvertures, clics et transactions, par demi-heure, par heure ou par jour, sous la forme d&#39;un graphique.

Les options disponibles sont les suivantes :

* **[!UICONTROL Ouvertures]** : Nombre total de messages ouverts. Les e-mails au format texte ne sont pas pris en compte. [En savoir plus](metrics-calculation.md#tracking-opens-).
* **[!UICONTROL Clics]** : nombre total de clics sur les liens dans les diffusions. Les clics sur les liens de désinscription et sur les pages miroir ne sont pas pris en compte.
<!--
* **[!UICONTROL Transactions]**: Total number of transactions after a message is received. In order for a transaction to be taken into account, a transaction type webtracking tag must be inserted into the matching web page. Webtracking configuration is presented in [this section](../../configuration/using/about-web-tracking.md).
-->

## Non-délivrables et rebonds {#non-deliverables-and-bounces}

Ce rapport présente la répartition des non-délivrables et la répartition des rebonds par domaine Internet.

Le **[!UICONTROL Nombre de messages traités]** représente le nombre total de messages traités par le serveur de diffusion. Cette valeur est inférieure au nombre de messages à diffuser lorsque certaines diffusions ont été arrêtées ou mises en pause (avant d’être traitées par le serveur).

**[!UICONTROL Répartition des erreurs par type]**

>[!NOTE]
>
>Les erreurs présentées dans ce rapport déclenchent le processus de mise en quarantaine. Pour plus d’informations sur la gestion de la quarantaine, consultez [Gestion de la quarantaine](../send/quarantines.md).

La première partie de ce rapport présente la répartition des non-délivrables sous la forme d’un tableau de valeurs et d’un graphique.

A chaque type d&#39;erreur, est associé :

* le nombre de messages en erreur de ce type,
* le pourcentage du nombre de messages en erreur de ce type par rapport au nombre total de messages en erreur,
* le pourcentage du nombre de messages en erreur de ce type par rapport au nombre total de messages traités.

Les indicateurs utilisés sont les suivants :

* **[!UICONTROL Utilisateur inconnu]** : type d&#39;erreur générée lors de l&#39;envoi d&#39;une diffusion indiquant que l&#39;adresse e-mail est invalide.
* **[!UICONTROL Domaine invalide]** : type d&#39;erreur générée lors de l&#39;envoi d&#39;une diffusion indiquant que le domaine de l&#39;adresse e-mail est erroné ou n&#39;existe plus.
* **[!UICONTROL Boîte pleine]** : type d’erreur générée, après cinq tentatives d’envoi d’une diffusion, indiquant que la boîte de messagerie de la personne destinataire contient trop de messages.
* **[!UICONTROL Compte désactivé]** : type d’erreur générée lors de l’envoi d’une diffusion indiquant que l’adresse n’existe plus.
* **[!UICONTROL Refusé]** : type d’erreur générée lorsqu’une adresse est refusée par le FAI (Fournisseur d’accès Internet) suite, par exemple, à l’application d’une règle de sécurité (logiciel anti-spams).
* **[!UICONTROL Inatteignable]** : type d’erreur survenue dans la chaîne de distribution du message : incident sur le relais SMTP, domaine temporairement inatteignable, etc.
* **[!UICONTROL Non connecté]** : type d’erreur indiquant que le téléphone portable de la personne destinataire est éteint ou n’est pas connecté au réseau au moment de l’envoi du message.

  >[!NOTE]
  >
  >Cet indicateur ne porte que sur les diffusions sur les [canaux mobiles](../send/send.md).

  Vous pouvez ouvrir chaque ligne du tableau de valeurs en cliquant sur le symbole `[+]`. Pour chaque type d’erreur, vous pouvez afficher la répartition des messages d’erreur par domaine.

**[!UICONTROL Répartition des erreurs par domaine]**

La seconde partie de ce rapport présente la répartition des erreurs par domaine Internet sous la forme d&#39;un tableau de valeurs et d&#39;un graphique.

A chaque nom de domaine, est associé :

* le nombre de messages en erreur sur ce domaine,
* le pourcentage du nombre de messages en erreur sur ce domaine par rapport au nombre total de messages traités sur ce domaine.
* le pourcentage du nombre de messages en erreur sur ce domaine par rapport au nombre total de messages en erreur,

Vous pouvez ouvrir chaque ligne du tableau de valeurs en cliquant sur le symbole [+]. Pour chaque type de domaine, vous pouvez afficher la répartition des messages d’erreur par type d’erreur.

![](assets/errors-report-details.png)

>[!NOTE]
>
>Les noms de domaine affichés dans ce rapport sont définis au niveau des cubes. Pour modifier ces valeurs, modifiez le cube des **[!UICONTROL Journaux de diffusion (broadlogrcp)]**. Pour plus d’informations, consultez [cette section](gs-cubes.md). La catégorie **[!UICONTROL Autres]** inclut les noms de domaine qui n’appartiennent pas à une classe spécifique.

## Navigateurs {#browsers}

Ce rapport présente la répartition entre les navigateurs internet utilisés par les destinataires des diffusions, pour la période sélectionnée.

>[!NOTE]
>
>Les valeurs affichées dans ce rapport sont des estimations. En effet, les destinataires des diffusions ne sont pas tous pris en compte. Seuls les destinataires ayant cliqué dans une diffusion sont comptabilisés.

**Statistiques globales**

Les statistiques globales d&#39;utilisation des navigateurs sont présentées sous la forme d&#39;un tableau de valeurs et d&#39;un graphique.

![](assets/browser-report.png)

Les indicateurs utilisés sont les suivants :

* **[!UICONTROL Visiteurs et visiteuses]** : nombre total de personnes destinataires ciblées, par navigateur Internet, ayant cliqué au moins une fois dans une même diffusion.
* **[!UICONTROL Pages vues]** : nombre total de clics sur les liens des diffusions, par navigateur Internet, dans l’ensemble des diffusions.
* **[!UICONTROL Taux d’utilisation]** : ce taux représente la répartition des visiteurs et des visiteuses, par navigateur Internet, par rapport au nombre total de visiteurs et de visiteuses.

**Statistiques par navigateur**

Dans le tableau de valeurs des statistiques globales, vous pouvez cliquer sur le nom de chaque navigateur afin de visualiser les statistiques d&#39;utilisation correspondantes.

![](assets/browser-report-info.png)

Les statistiques sont présentées sous la forme d&#39;une courbe, d&#39;un graphique et d&#39;un tableau de valeurs.

La courbe **[!UICONTROL Historique]** représente le taux de fréquentation quotidienne de ce navigateur. Le taux est le ratio du nombre de visiteurs par jour (sur ce navigateur) par rapport au nombre de visiteurs mesuré le jour avec le taux de fréquentation le plus élevé.

Le graphique **[!UICONTROL Répartition par version]** représente la répartition des visiteurs, par version, par rapport au nombre total de visiteurs sur ce navigateur.

Le tableau de valeurs utilise les indicateurs suivants :

* **[!UICONTROL Taux global]** : ce taux représente la répartition des visiteurs et des visiteuses, par version, par rapport au nombre total de visiteurs et de visiteuses sur l’ensemble des navigateurs.
* **[!UICONTROL Taux relatif]** : ce taux représente la répartition des visiteurs et des visiteuses, par version, par rapport au nombre total de visiteurs et de visiteuses sur ce navigateur.


<!--
### Sharing to social networks {#sharing-to-social-networks}

Viral marketing lets delivery recipients share information with their contact network: they can add a link to their profile (Facebook, Twitter, etc.) or send a message to a friend. Each share and each access to shared information is tracked within the delivery. For more information on viral marketing, refer to [this section](../../delivery/using/viral-and-social-marketing.md).

This report shows the breakdown of shared and opened messages per social network (Facebook, Twitter, etc.) and/or per email.

![](assets/s_ncs_user_social_report.png)

**[!UICONTROL Email delivery statistics]**

In the email delivery statistics, two values are displayed:

* **[!UICONTROL Number of messages to be delivered]**: Total number of messages processed during delivery analysis.
* **[!UICONTROL Number of successful deliveries]**: Number of messages processed successfully.

**[!UICONTROL Sharing activities and mail open statistics]**

The central table shows the statistics on email shares and opens.

In the **[!UICONTROL Shares]** column, we have the following indicators:

* **[!UICONTROL No. of sharing activities]**: Total number of messages shared on each social network. This value equals the total number of clicks on the icon of the matching **[!UICONTROL Links for sharing to social networks]** personalization block.
* **[!UICONTROL Breakdown]**: This rate represents the breakdown of shares per social network, in relation to the total number of shares.
* **[!UICONTROL Sharing rate]**: This rate represents the breakdown of shares per social network, in relation to the number of messages to be delivered.

In the **[!UICONTROL Opens]** column, we have the following indicators:

* **[!UICONTROL No. of opens]**: Total number of messages opened by people whom the message was forwarded to (via the **[!UICONTROL Links for sharing to social networks]** personalization block). This value equals the number of times the mirror page was displayed. Opens by delivery recipients are not taken into account.
* **[!UICONTROL Breakdown]**: This rate represents the breakdown of opens per social network, in relation to the total number of opens.
* **[!UICONTROL Rate of opens]**: This rate represents the breakdown of opens per social network, in relation to the total number of shares.

**[!UICONTROL Breakdown of sharing activities and opens]**

This section includes two charts which represent the breakdown of sharing activities and opens per social network.


## Statistics on sharing activities {#statistics-on-sharing-activities}

This report shows the evolution of shares to social media in time.

For more information on viral marketing, refer to [this section](../../delivery/using/viral-and-social-marketing.md).

Statistics are presented in the form of a table of values and a chart.

The following indicators are used:

* **[!UICONTROL New contacts]**: Number of new subscriptions following the reception of a message shared via email. This value matches the number of people who received a message shared via email, clicked the **[!UICONTROL Subscription link]** and filled in the subscription form.
* **[!UICONTROL Opens]**: Total number of messages opened by people whom the message was transferred to (via the **[!UICONTROL Link for sharing to social networks]** personalization block). This value equals the number of times the mirror page was displayed. Opens by delivery recipients are not taken into account.
* **[!UICONTROL Sharing activities]**: Total number of messages shared via social networks. This value matches the total number of clicks on the icon of the **[!UICONTROL Links for sharing to social networks]** personalization block.
-->

## Systèmes d’exploitation {#operating-systems}

Ce rapport présente la répartition entre les systèmes d&#39;exploitation utilisés par les destinataires des diffusions, pour la période sélectionnée.

>[!NOTE]
>
>Les valeurs affichées dans ce rapport sont des estimations. En effet, les destinataires des diffusions ne sont pas tous pris en compte. Seuls les destinataires ayant cliqué dans une diffusion sont comptabilisés.

**Statistiques globales**

Les statistiques globales d&#39;utilisation des systèmes d&#39;exploitation sont présentées sous la forme d&#39;un tableau de valeurs et d&#39;un graphique.

![](assets/os-report.png)

Les indicateurs utilisés sont les suivants :

* **[!UICONTROL Visiteurs et visiteuses]** : moyenne par jour du nombre total de personnes destinataires ciblées, par système d’exploitation, ayant cliqué au moins une fois dans une même diffusion.
* **[!UICONTROL Pages vues]** : moyenne par jour du nombre total de clics sur les liens des diffusions, par système d’exploitation, pour l’ensemble des diffusions.
* **[!UICONTROL Taux d’utilisation]** : ce taux représente la répartition des visiteurs et des visiteuses, par système d’exploitation, par rapport au nombre total de visiteurs et de visiteuses.

**Statistiques par système d&#39;exploitation**

Dans le tableau de valeurs des statistiques globales, vous pouvez cliquer sur le nom de chaque système d&#39;exploitation afin de visualiser les statistiques d&#39;utilisation correspondantes.

![](assets/os-report-details.png)

Les statistiques sont présentées sous la forme d&#39;une courbe, d&#39;un graphique et d&#39;un tableau de valeurs.

La courbe **[!UICONTROL Historique]** représente le taux d&#39;utilisation de ce système d&#39;exploitation par jour. Ce taux est le ratio du nombre de visiteurs par jour (sur ces systèmes d’exploitation) par rapport au nombre de visiteurs mesuré le jour avec la plus grande affluence.

Le graphique **[!UICONTROL Répartition par version]** représente la répartition des visiteurs, par version, par rapport au nombre total de visiteurs sur ce système d&#39;exploitation.

Le tableau de valeurs utilise les indicateurs suivants :

* **[!UICONTROL Taux global]** : ce taux représente la répartition des visiteurs et des visiteuses, par version, par rapport au nombre total de visiteurs et de visiteuses sur l’ensemble des systèmes d’exploitation.
* **[!UICONTROL Taux relatif]** : ce taux représente la répartition des visiteurs et des visiteuses, par version, par rapport au nombre total de visiteurs et de visiteuses sur ce système d’exploitation.

## Tracking des abonnements {#subscription-tracking}

Ce rapport permet de suivre les abonnements aux services d’information. Il affiche les abonnements et les désabonnements.

![](assets/service-report.png)

Il peut être affiché pour un abonnement en cliquant sur le nœud **[!UICONTROL Profils et cibles > Services et abonnements]** de la page d’accueil ou de l’explorateur. Sélectionnez l’abonnement souhaité, puis cliquez sur l’onglet **[!UICONTROL Rapports]**. Le rapport **[!UICONTROL Suivi des abonnements]** est disponible par défaut. Il vous permet de visualiser les tendances d’abonnement et de désinscription, ainsi que le taux de fidélité sur une période. Vous pouvez paramétrer la représentation de ces données dans la liste déroulante. Cliquez sur **[!UICONTROL Actualiser]** pour valider la configuration sélectionnée.

Voir à ce propos [cette page](../start/subscriptions.md).

Le **[!UICONTROL Nombre d&#39;inscrits à ce jour]** représente le nombre total d&#39;abonnés à ce jour.

**[!UICONTROL Evolution globale des inscriptions]**

Le tableau de valeurs utilise les indicateurs suivants :

* **[!UICONTROL Personnes inscrites]** : nombre total de personnes abonnés sur la période correspondante.
* **[!UICONTROL Abonnements]** : nombre d’abonnements sur la période correspondante.
* **[!UICONTROL Désabonnements]** : nombre de désabonnements sur la période correspondante.
* **[!UICONTROL Evolution]** : Nombre de désabonnements soustrait au nombre d&#39;abonnements. Le taux est calculé par rapport au nombre total d&#39;abonnés.
* **[!UICONTROL Fidélité]** : taux de fidélité des personnes abonnées sur la période correspondante.

**[!UICONTROL Courbes d&#39;évolution des inscriptions]**

Ce graphique représente l&#39;évolution dans le temps des inscriptions et désinscriptions, sur la période sélectionnée.

## Statistiques de diffusion {#delivery-statistics}

Ce rapport présente la répartition, par domaine Internet, des messages traités et envoyés, des rebonds définitifs et temporaires, des ouvertures, des clics et des désinscriptions.

![](assets/broadcast-report.png)

Les indicateurs utilisés sont les suivants :

* **[!UICONTROL E-mails traités]** : nombre total de messages traités par le serveur de diffusion.
* **[!UICONTROL Diffusés]** : pourcentage du nombre de messages traités avec succès, par rapport au nombre total de messages traités.
* **[!UICONTROL Rebonds définitifs]** : pourcentage du nombre de rebonds définitifs, par rapport au nombre total de messages traités.
* **[!UICONTROL E-mails rejetés temporairement]** : pourcentage du nombre d’e-mails rejetés temporairement, par rapport au nombre total de messages traités.

  >[!NOTE]
  >
  >Pour plus d’informations sur les rebonds définitifs et temporaires, consultez [cette page](../send/quarantines.md).

* **[!UICONTROL Ouvertures]** : pourcentage du nombre de personnes destinataires ciblées distinctes ayant ouvert au moins une fois un même message, par rapport au nombre de messages traités avec succès.
* **[!UICONTROL Clics]** : pourcentage du nombre de personnes distinctes ayant cliqué au moins une fois dans une même diffusion, par rapport au nombre de messages traités avec succès.
* **[!UICONTROL Désabonnements]** : pourcentage du nombre de clics effectués sur un lien de désabonnement, par rapport au nombre de messages traités avec succès.

## Répartition des ouvertures {#breakdown-of-opens}

Ce rapport présente la répartition des ouvertures par système d’exploitation, par appareil et par navigateur pour la période concernée. Deux graphiques sont utilisés pour chaque catégorie. Le premier affiche les statistiques d’ouverture sur un ordinateur et des appareils mobiles. Le second affiche des statistiques relatives uniquement aux ouvertures sur les appareils mobiles.

Le nombre d’ouvertures correspond au nombre total de messages ouverts. Les emails au format texte ne sont pas comptabilisés. Pour plus d’informations sur le tracking des ouvertures, consultez [cette section](metrics-calculation.md#tracking-opens-).

![](assets/user-agent-report.png)

>[!NOTE]
>
>Les noms des navigateurs et des systèmes d&#39;exploitation font partie des informations envoyées par l&#39;agent utilisateur du navigateur vers lequel le message a été ouvert. Adobe Campaign détermine le type d&#39;appareil en utilisant ses informations sur l&#39;appareil.
