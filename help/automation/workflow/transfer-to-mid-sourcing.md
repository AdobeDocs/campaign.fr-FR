---
product: campaign
title: Emission vers Mid-sourcing
description: En savoir plus sur les workflows d’émission vers Mid-sourcing
feature: Workflows
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
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 100%
---

# Émission vers Mid-sourcing{#transfer-to-mid-sourcing}

Les workflows présentés ci-dessous sont installés par défaut avec le module **Émission vers Mid-sourcing**.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Libellé</strong><br /> </td> 
   <td> <strong>Nom interne</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Mid-sourcing (compteurs des diffusions)</span> <br /> </td> 
   <td> <span class="uicontrol">defaultMidSourcingDlv</span> <br /> </td> 
   <td> <p>Ce workflow collecte les informations de comptage pour les diffusions sur le serveur de midsourcing. Les informations de comptage comprennent les indicateurs généraux de diffusion tels que le nombre de diffusions envoyées, etc.</p> <p>Les informations de tracking comme les ouvertures ne sont pas incluses.</p> <p>Par défaut, il se déclenche toutes les dix minutes.</p> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Mid-sourcing (logs de diffusion)</span> <br /> </td> 
   <td> <span class="uicontrol">defaultMidSourcingLog</span> <br /> </td> 
   <td> Ce workflow collecte les logs des diffusions sur le serveur de mid-sourcing. Par défaut, il se déclenche toutes les heures.<br /> </td> 
  </tr> 
 </tbody> 
</table>

