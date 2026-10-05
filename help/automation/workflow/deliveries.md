---
product: campaign
title: Diffusions
description: En savoir plus sur les workflows de diffusions par défaut
feature: Workflows
role: User, Admin
version: Campaign v8, Campaign Classic v7
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 89%
---

# Diffusions{#deliveries}



Les workflows présentés ci-dessous sont installés par défaut avec le module **Diffusions**.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Libellé</strong><br /> </td> 
   <td> <strong>Nom interne</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Agrégats du reporting</span> <br /> </td> 
   <td> <span class="uicontrol">reportingAggregates</span> <br /> </td> 
   <td> Ce workflow met à jour les agrégats utilisés dans les rapports. Par défaut, il se déclenche tous les jours à 2H00.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Facturation</span> <br /> </td> 
   <td> <span class="uicontrol">billing</span> <br /> </td> 
   <td> Ce workflow transmet par email le rapport d'activité du système à l'opérateur 'billing'. Par défaut, il se déclenche tous les 25 du mois.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Gestion des alias</span> <br /> </td> 
   <td> <span class="uicontrol">aliasCleansing</span> <br /> </td> 
   <td> Ce workflow réalise l’uniformisation des valeurs des énumérations. Par défaut, il se déclenche tous les jours à 3h00.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Mise à jour pour la délivrabilité</span> <br /> </td> 
   <td> <span class="uicontrol">deliverabilityUpdate</span> <br /> </td> 
   <td> Ce workflow vous permet de créer la liste des règles de qualification des e-mails rejetés, ainsi que la liste des domaines et des MX dans la plateforme. Ce workflow ne fonctionne que si le port HTTPS est ouvert. Ces listes ne sont pas mises à jour tant que le module Délivrabilité n'est pas installé.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Nettoyage de la base de données</span> <br /> </td> 
   <td> <span class="uicontrol">cleanup</span> <br /> </td> 
   <td> <p>Ce workflow est le workflow de maintenance de la base de données : il procède aux différents calculs des statistiques et traitements, et supprime les données obsolètes de la base de données selon le paramétrage défini dans l'assistant de déploiement. Par défaut, il se déclenche tous les jours à 4H00.</p></td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Nettoyage des workflows en pause</span> <br /> </td> 
   <td> <span class="uicontrol">cleanupPausedWorkflows</span> <br /> </td> 
   <td> <p>Ce workflow analyse les workflows en pause dont le niveau de priorité est défini sur normal et déclenche des avertissements et des notifications lorsqu’ils sont en pause depuis trop longtemps. Au bout d’un mois, les workflows techniques en pause sont arrêtés de manière inconditionnelle. Par défaut, il se déclenche chaque lundi à 5 h 00.</p> <p>Pour plus d'informations, voir Gérer les workflows en pause</a>.</p></td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Notification des offres</span> <br /> </td> 
   <td> <span class="uicontrol">offerMgt</span> <br /> </td> 
   <td> Toutes les heures, ce workflow déploie les offres validées sur l'environnement en ligne, ainsi que toutes les catégories contenues dans le catalogue d'offres.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Prévisionnel</span> <br /> </td> 
   <td> <span class="uicontrol">forecasting</span> <br /> </td> 
   <td> Ce workflow effectue l’analyse des diffusions enregistrées dans le calendrier prévisionnel (création des logs prévisionnels). Par défaut, il se déclenche tous les jours à 1h00.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Tracking</span> <br /> </td> 
   <td> <span class="uicontrol">tracking</span> <br /> </td> 
   <td> Ce workflow effectue la récupération et la consolidation des informations de tracking. Il assure également le recalcul des statistiques de tracking et de diffusion, notamment celles utilisées par les workflows d’archivage de Message Center. Par défaut, il est déclenché une fois par heure. <br /> </td> 
  </tr> 
 </tbody> 
</table>

