---
product: campaign
title: Workflows relatifs au règlement sur la protection des informations personnelles
description: En savoir plus sur les workflows relatifs au règlement sur la protection des informations personnelles
role: User
version: Campaign v8, Campaign Classic v7
feature: Workflows, Privacy
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
  - id: a7760dfc-5c44-4d77-bb68-c50b1e265c93
    internal-label: Security and privacy
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: ac9c0a9c-8a76-4419-bd64-9c34c5782666
    internal-label: Privacy
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 100%
---

# Règlement sur la protection des informations personnelles{#general-data-protection-regulation-gdpr}


Les workflows présentés ci-dessous sont installés par défaut avec le module **Règlement sur la protection des informations personnelles**. Voir à ce propos cet [article](https://helpx.adobe.com/fr/campaign/kb/acc-privacy.html).

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Libellé</strong><br /> </td> 
   <td> <strong>Nom interne</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Collecter les demandes d’accès à des informations personnelles</span> <br /> </td> 
   <td> <span class="uicontrol">collectPrivacyRequests</span> <br /> </td> 
   <td> Ce workflow génère les données du destinataire stockées dans Adobe Campaign et les met à disposition sur l’écran de la demande d’accès.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Supprimer les données des demandes d’accès à des informations personnelles</span> <br /> </td> 
   <td> <span class="uicontrol">deletePrivacyRequestsData</span> <br /> </td> 
   <td> Ce workflow supprime les données du destinataire stockées dans Adobe Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Nettoyage des demandes d’accès à des informations personnelles</span> <br /> </td> 
   <td> <span class="uicontrol">cleanupPrivacyRequests</span> <br /> </td> 
   <td> Ce workflow supprime les fichiers de demande d’accès qui ont plus de 90 jours.<br /> </td> 
  </tr> 
 </tbody> 
</table>

