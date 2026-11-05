---
product: campaign
title: Plateforme de Mid-sourcing
description: Plateforme de Mid-sourcing
feature: Workflows
role: User
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
source-git-commit: 8a7bf8408d15e0bd9e1c3e72f7846bf9a79c6885
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 41%
---

# Plateforme de Mid-sourcing{#mid-sourcing-platform}



Le workflow détaillé ci-dessous est installé par défaut avec le module **Plateforme de midsourcing**.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Libellé</strong><br /> </td> 
   <td> <strong>Nom interne</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Indicateurs de diffusion</span> <br /> </td> 
   <td> <span class="uicontrol">deliveryIndicators</span> <br /> </td> 
   <td> Ce workflow met à jour les indicateurs de tracking des diffusions. Par défaut, ce workflow se déclenche toutes les heures.<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>La période de conservation des logs sur le serveur de mid-sourcing doit être supérieure à la période de validité de la diffusion plus la valeur **indicatorsDuration**. Dans le cas contraire, les indicateurs de diffusion diminuent lorsque les anciens logs sont purgés et que les valeurs les plus faibles sont synchronisées avec l’instance marketing. Par exemple, avec une période de validité de 5 jours et un **indicatorsDuration** de 30 jours, définissez la période de conservation sur au moins 36 jours.
