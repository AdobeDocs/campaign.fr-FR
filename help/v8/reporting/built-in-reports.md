---
title: Rapports intégrés d’Adobe Campaign
description: Rapports intégrés
feature: Reporting
role: User
level: Beginner
exl-id: b63e6905-3bd4-4de4-9e7e-7638e5fc1192
source-git-commit: f577ee6d303bab9bb07350b60cf0fa6fc9d3a163
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 100%

---

# Rapports intégrés d’Adobe Campaign {#ootb-reports}

Cette page fournit la liste des rapports intégrés d’Adobe Campaign, leur contenu et leur contexte. Toute une gamme de rapports intégrés est comprise dans Adobe Campaign. Vous pouvez y accéder à partir de la console cliente ou d’un navigateur Internet.

Les types de rapports disponibles sont les suivants :

* Rapports concernant l’ensemble de la plateforme. [En savoir plus](global-reports.md).
* Rapports de diffusion. [En savoir plus](delivery-reports.md).

Vous pouvez accéder aux rapports intégrés à partir de la page d’accueil de Campaign, du tableau de bord des rapports dédié ou de la liste des diffusions. La façon dont le rapport s’affiche dans l’interface utilisateur dépend de son contexte.

Une liste des principaux rapports est disponible sur la page d’accueil et permet d’accéder rapidement aux données de diffusion. Cette liste peut être modifiée en fonction de vos besoins. Vous pouvez également apprendre à ajouter vos propres rapports à l’onglet **[!UICONTROL Rapports.]**

Pour plus d’informations sur ces configurations personnalisées, consultez la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/configuring-access-to-the-report.html?lang=fr).


## Accès aux rapports intégrés {#access-ootb-reports}

Pour accéder aux rapports natifs de Campaign :

1. Sélectionnez l&#39;onglet **[!UICONTROL Rapports]** de l&#39;interface Adobe Campaign.

   ![](assets/reporting-access-from-home.png)

1. Utilisez les champs de recherche pour filtrer les rapports affichés.

1. Cliquez ensuite sur le rapport souhaité pour l&#39;afficher.

   ![](assets/edit-a-report.png)

1. Cliquez sur le lien **[!UICONTROL Retour]** situé en haut de l&#39;écran pour revenir à la liste des rapports.

   ![](assets/back-button.png)

Les rapports spécifiques à une opération ou à une diffusion sont accessibles à partir de leur tableau de bord respectif.

![](assets/reporting-on-delivery.png)

Le principe est le même pour les listes, les services, les offres, etc., comme dans l&#39;exemple ci-dessous :

![](assets/reporting-on-offer.png)


## Rapports sur les diffusions {#reports-on-deliveries}

Les rapports intégrés fournis par Adobe Campaign figurent dans le tableau ci-après.

Pour plus d&#39;informations sur le contenu de ces rapports, consultez [cette section](delivery-reports.md).

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Libellé et nom interne</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
   <td> <strong>Schéma</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Activités utilisateurs (recipientActivity)<br /> </td> 
   <td> Répartition des ouvertures, clics et transactions des destinataires par tranche horaire.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Débit de diffusion (throughput)<br /> </td> 
   <td> Graphes de débit de diffusion, en messages/heure et Bits/s.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Echecs et retours (errors)<br /> </td> 
   <td> Ventilation des échecs et retours, par cause et domaine de messagerie.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Indicateurs de tracking (deliveryFeedback)<br /> </td> 
   <td> Synthèse des indicateurs-clés pour le tracking du comportement des destinataires.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Indicateurs de tracking (mobileAppDeliveryFeedback)<br /> </td> 
   <td> Indicateurs de tracking d'une diffusion sur application mobile.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Navigateurs (browserStatistics)<br /> </td> 
   <td> Statistiques sur les navigateurs utilisés par les destinataires ayant cliqué dans les messages.<br /> </td> 
   <td> xtk:none<br /> </td> 
  </tr> 
  <tr> 
   <td> Partage vers les réseaux sociaux (deliveryForward)<br /> </td> 
   <td> Statistiques des partages et d'ouvertures.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Position des clics (hoturls)<br /> </td> 
   <td> Affiche le message et les taux de clics en surimpression.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Rapport des hypothèses (deliveryHypothesis)<br /> </td> 
   <td> Affiche la synthèse des mesures sur les hypothèses de diffusion.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Statistiques de diffusion (statisticsPerDelivery)<br /> </td> 
   <td> Statistiques (messages traités, messages délivrés, erreurs hard, erreurs soft, ouvertures, clics, désinscriptions) par domaine de l'email.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Statistiques des activités de partage (forwardActivities)<br /> </td> 
   <td> Analyse des partages, ouvertures et abonnements par périodes de temps.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Statistiques de tracking (trackingStatistics)<br /> </td> 
   <td> Statistiques sur les taux d'ouvertures, clics et transactions dans le temps.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Synthèse des diffusions (deliverySending)<br /> </td> 
   <td> Synthèse des indicateurs de la diffusion : cible, exclusions et envois.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Synthèse des diffusions (deliveryStatistics)<br /> </td> 
   <td> Tableau de synthèse des diffusions sélectionnées : cibles, exclusions et envois.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Systèmes d'exploitation (osStatistics)<br /> </td> 
   <td> Statistiques sur les systèmes d'exploitation utilisés par les destinataires ayant cliqué dans un message.<br /> </td> 
   <td> xtk:none<br /> </td> 
  </tr> 
  <tr> 
   <td> Taux de réactivité (deliveryFeedbackSocial)<br /> </td> 
   <td> Taux de réactivité d'une diffusion et répartition des réactions.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> URL et flux de clics (topUrlDelivery)<br /> </td> 
   <td> URL les plus réactives et flux de clics associés.<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Rapports sur les opérations {#reports-on-campaigns}

Les rapports sur les campagnes portent sur les données du tableau **nms:operation**.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Libellé et nom interne</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Activités utilisateurs (operationRecipientActivity)<br /> </td> 
   <td> Répartition des ouvertures, clics et transactions des destinataires par tranche horaire. Dépend de Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> Débit de diffusion (operationThroughput)<br /> </td> 
   <td> Graphes de débit de diffusion, en mails/heure et Mbits/s. Dépend de Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dépenses de l'opération (budgetOperationExpenses)<br /> </td> 
   <td> Affiche en détail les dépenses rattachées à l'opération. Dépend de Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> Echecs et retours (operationErrors)<br /> </td> 
   <td> Ventilation des échecs et retours, par cause et domaine de messagerie. Dépend de Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> Exploration des lignes de coût (budgetExplorerOperation)<br /> </td> 
   <td> Analyse descriptive d'exploration des lignes de coûts. Dépend de MRM.<br /> </td> 
  </tr> 
  <tr> 
   <td> Indicateurs de tracking (operationFeedback)<br /> </td> 
   <td> Synthèse des indicateurs-clés de tracking : ouvertures, clics et transactions. Dépend de Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> Partage vers les réseaux sociaux (operationForward)<br /> </td> 
   <td> Statistiques des partages et d'ouvertures. Dépend de Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rapport des hypothèses (operationHypothesis)<br /> </td> 
   <td> Affiche la synthèse des mesures sur les hypothèses des diffusions de l'opération. Dépend de Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> Statistiques des activités de partage (forwardActivityOpt)<br /> </td> 
   <td> Analyse des partages, ouvertures et abonnements par périodes de temps. Dépend de Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> Synthèse des diffusions (operationStatistics)<br /> </td> 
   <td> Tableau de synthèse des diffusions de l'opération : cibles, exclusions et envois.<br /> </td> 
  </tr> 
  <tr> 
   <td> URL et flux de clics (operationTopUrlDelivery)<br /> </td> 
   <td> URL les plus réactives et flux de clics associés. Dépend de Campaign.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Rapports sur les services {#reports-on-services}

Les rapports sur les services portent sur les données du tableau **nms:service**.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Libellé et nom interne</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Acquisitions des fans (socialAcquisitionsByWebapp)<br /> </td> 
   <td> Quelles sont les applications web à l'origine des acquisitions de prospects ? Dépend du composant additionnel Social Marketing.<br /> </td> 
  </tr> 
  <tr> 
   <td> Répartition des abonnements (mobileAppDistribution)<br /> </td> 
   <td> Répartition des abonnements actifs par application mobile. Dépend du composant additionnel Mobile app channel.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tracking des abonnements (subscriptionsProgress)<br /> </td> 
   <td> Evolution des inscriptions aux services d'information<br /> </td> 
  </tr> 
  <tr> 
   <td> Taux de réactivité (socialReactionRate)<br /> </td> 
   <td> Quels sont les taux de réactivité obtenus par les dernières diffusions ? Dépend du composant additionnel Social Marketing.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taux de réactivité (mobileAppReactivityRate)<br /> </td> 
   <td> Taux de réactivité des dernières diffusions. Dépend du composant additionnel Canal des applications mobiles.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Rapports sur les budgets {#budget-reports}

Les rapports intégrés fournis par Adobe Campaign figurent dans le tableau ci-après.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Libellé et nom interne</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
   <td> <strong>Schéma</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Coûts liés au(x) programme(s) (budgetProgramCost)<br /> </td> 
   <td> Répartition des coûts du programme.<br /> </td> 
   <td> nms:program<br /> </td> 
  </tr> 
  <tr> 
   <td> Evolution du budget (budgetEvolution)<br /> </td> 
   <td> Evolution des coûts du budget, répartis par niveau d'engagement.<br /> </td> 
   <td> nms:budget<br /> </td> 
  </tr> 
  <tr> 
   <td> Evolution cumulée du budget (budgetCumulativeEvolution)<br /> </td> 
   <td> Evolution des coûts cumulés du budget, répartis par niveau d'engagement<br />. </td> 
   <td> nms:budget<br /> </td> 
  </tr> 
  <tr> 
   <td> Exploration des lignes de coût (budgetExplorerBudget)<br /> </td> 
   <td> Analyse descriptive d'exploration des lignes de coûts.<br /> </td> 
   <td> nms:budget<br /> </td> 
  </tr> 
  <tr> 
   <td> Exploration des lignes de coût (budgetExplorer)<br /> </td> 
   <td> Analyse descriptive d'exploration des lignes de coûts.<br /> </td> 
   <td> nms:costLine<br /> </td> 
  </tr> 
  <tr> 
   <td> Exploration des lignes de coût (budgetExplorerPlan)<br /> </td> 
   <td> Analyse descriptive d'exploration des lignes de coûts.<br /> </td> 
   <td> nms:plan<br /> </td> 
  </tr> 
  <tr> 
   <td> Exploration des lignes de coût (budgetExplorerProgram)<br /> </td> 
   <td> Analyse descriptive d'exploration des lignes de coûts.<br /> </td> 
   <td> nms:program<br /> </td> 
  </tr> 
  <tr> 
   <td> Synthèse du/des budget(s) (budget)<br /> </td> 
   <td> Etat instantané des coûts principaux, des catégories de dépenses et des budgets.<br /> </td> 
   <td> nms:budget<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Rapports sur les simulations {#reports-on-simulations}

Les rapports sur les simulations portent sur les données du tableau **nms:simulation**.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Libellé et nom interne</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Détail des exclusions de la simulation (dlvSimuLossesDetail)<br /> </td> 
   <td> Tableau détaillé de toutes les causes d'exclusion.<br /> </td> 
  </tr> 
  <tr> 
   <td> Répartition des offres par rang (offerSimulationRanking)<br /> </td> 
   <td> Répartition des offres de la simulation, par rang d'apparition.<br /> </td> 
  </tr> 
  <tr> 
   <td> Résumé de la simulation (dlvSimuLossesSummary)<br /> </td> 
   <td> Résumé des volumes et des exclusions de la simulation.<br /> </td> 
  </tr> 
  <tr> 
   <td> Statistiques de recouvrement (dlvSimuOverlapping)<br /> </td> 
   <td> Volumes de recouvrement des cibles des diffusions.<br /> </td> 
  </tr> 
  <tr> 
   <td> Synthèse des exclusions dues à la simulation (dlvSimuLossesSimu)<br /> </td> 
   <td> Tableau des exclusions dûes à la simulation.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Rapports sur les applications Web {#reports-on-web-applications}

Les rapports sur les applications Web portent sur les données du tableau **nms:WebApp**.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Libellé et nom interne</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Documentation (surveyDictionary)<br /> </td> 
   <td> Description de la structure du questionnaire. Dépend du composant additionnel Survey Manager.<br /> </td> 
  </tr> 
  <tr> 
   <td> Général (surveyProperties)<br /> </td> 
   <td> Propriétés du questionnaire<br /> </td> 
  </tr> 
  <tr> 
   <td> Répartition des réponses (surveyDistribution)<br /> </td> 
   <td> Répartition des réponses aux questions.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Autres rapports d&#39;usine {#other-ootb-reports}

Les rapports suivants sont également fournis natifs. Pour plus d&#39;informations, reportez-vous au document relatif à la fonctionnalité à laquelle ils sont associés.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Libellé et nom interne</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
   <td> <strong>Schéma</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Analyse des offres (offerAnalysis)<br /> </td> 
   <td> Analyse des offres par date et canal. Dépend du composant additionnel Interaction.<br /> </td> 
   <td> nms:offer<br /> </td> 
  </tr> 
  <tr> 
   <td> Efficacité du remarketing (remarketingEffect)<br /> </td> 
   <td> Mesure de l'efficacité du remarketing<br /> </td> 
   <td> nms:webEvent<br /> </td> 
  </tr> 
  <tr> 
   <td> Historique des acquisitions de prospects sociaux (socialVisitorStatistics)<br /> </td> 
   <td> Historique des acquisitions des prospects Twitter et Facebook. Dépend du composant additionnel Social Marketing.<br /> </td> 
   <td> nms:visitor<br /> </td> 
  </tr> 
  <tr> 
   <td> Tracking des propositions récentes (recentPropositions)<br /> </td> 
   <td> Tracking en temps réel des propositions<br /> </td> 
   <td> nms:propositionRcp<br /> </td> 
  </tr> 
 </tbody> 
</table>
