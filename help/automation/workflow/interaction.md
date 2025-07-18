---
product: campaign
title: Interaction
description: Interaction
feature: Workflows, Interaction
role: User, Admin
version: Campaign v8, Campaign Classic v7
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: ht
source-wordcount: '131'
ht-degree: 100%

---


# Interaction{#interaction}

Les workflows présentés ci-dessous sont installés par défaut avec le module complémentaire **Moteur d’offres (Interaction)**.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Libellé</strong><br /> </td> 
   <td> <strong>Nom interne</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Calcul de l'agrégat full (cube propositionrcp)</span> <br /> </td> 
   <td> <span class="uicontrol">agg_nmspropositionrcp_full</span> <br /> </td> 
   <td> Ce workflow met à jour l'agrégat <strong>Complet (full)</strong> du cube <strong>Proposition d'offre</strong>. Par défaut, il se déclenche tous les jours à 6H00. Cet agrégat capture les dimensions suivantes : Canal, Diffusion, Offre marketing et Date.<br /> Le cube <strong>Proposition d’offre</strong> est ensuite utilisé pour générer des rapports basés sur des offres.<br /> </td> 
  </tr> 
   <tr> 
   <td> <span class="uicontrol">Calcul de l'agrégat full (cube propositionrcp) du MessageCenter</span> <br /> </td> 
   <td> <span class="uicontrol">agg_messageCenter_full</span> <br /> </td> 
   <td> Ce workflow met à jour l’agrégat complet<strong>(Full)</strong> du cube <strong>Message Center</strong>. Il est déclenché tous les jours à 3h du matin par défaut. Cet agrégat capture les dimensions suivantes : Canal, Date, Statut et Type d'événement.<br /> Le cube <strong>Message Center</strong> est ensuite utilisé pour générer des rapports basés sur des événements. <br /> </td> 
   <td> <br /> </td> 
  </tr> 
 </tbody> 
</table>

En savoir plus sur les cubes et les agrégats dans [cette section](../../v8/reporting/gs-cubes.md).

