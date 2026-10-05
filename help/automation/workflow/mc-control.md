---
product: campaign
title: Message Center (Pilotage)
description: Message Center (Pilotage)
feature: Workflows
role: User
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
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 100%
---

# Message Center (Pilotage){#message-center-control}

Le workflow présenté ci-dessous est planifié pour s’exécuter toutes les heures. Il est installé par défaut avec le module **Message Center - Contrôle**.


<table> 
 <tbody> 
  <tr> 
   <td> <strong>Libellé</strong><br /> </td> 
   <td> <strong>Nom interne</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Message Center &lt;external_account_name&gt;<br /> </td> 
   <td> mcSynch_&lt;external_account_name&gt;<br /> </td> 
   <td> Ce workflow :<br /> 
    <ul> 
     <li> <p>récupère la liste des événements traités par la ou les opérations,</p> </li> 
     <li> <p>se synchronise avec la table NmsBroadLogMsg afin de récupérer les qualifications des messages de diffusion,</p> </li> 
     <li> <p>récupère les logs de diffusion d'événements dès que la synchronisation avec la table NmsBroadLogMsg est terminée,</p> </li> 
     <li> <p>se synchronise avec la table NmsTrackingUrl afin de récupérer le tracking des URL de diffusion,</p> </li> 
     <li> <p>récupère les URL de tracking des événements dès que la synchronisation avec la table NmsTrackingUrl est terminée,</p> </li> 
     <li> <p>permet de récupérer toutes les adresses email mises en quarantaine toutes les trois heures après l'envoi d'une diffusion.</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

