---
product: campaign
title: Canal LINE
description: Canal LINE
feature: Workflows, Line App
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
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: d9d413df-4e9e-4906-bbbc-28c06c2ccf59
    internal-label: LINE App
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 100%
---

# Canal LINE{#line-channel}

Les workflows présentés ci-dessous sont installés par défaut avec le module **canal LINE**. Pour plus d’informations sur ce module, consultez [cette page](../../v8/send/line/line.md).

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Libellé</strong><br /> </td> 
   <td> <strong>Nom interne</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Mise à jour du jeton d’accès LINE V2</span> <br /> </td> 
   <td> <span class="uicontrol">updateLineV2AccessToken</span> <br /> </td> 
   <td> Ce workflow actualise le jeton d’accès à la version LINE V2.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Nettoyage des utilisateurs LINE bloqués</span> <br /> </td> 
   <td> <span class="uicontrol">deleteBlockedLineUsersV2</span> <br /> </td> 
   <td> Ce workflow assure la suppression des données des utilisateurs LINE V2 s’ils ont bloqué le compte officiel LINE pendant 180 jours.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Migration du MID vers l’identifiant utilisateur Line</span> <br /> </td> 
   <td> <span class="uicontrol">MIDToUserIDMigration</span> <br /> </td> 
   <td> Ce workflow génère les ID des utilisateurs LINE V2 pour la migration de LINE V1 vers LINE V2.<br /> </td> 
  </tr> 
 </tbody> 
</table>

