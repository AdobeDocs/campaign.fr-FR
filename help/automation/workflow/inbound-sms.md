---
product: campaign
title: Réception de SMS
description: En savoir plus sur l’activité de workflow de réception de SMS
feature: Workflows, Channels Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 2c12c45b-4429-4e60-bc96-ff70a95d4c9e
TQID: 'https://experienceleague.adobe.com/ZZcWkqyokq5qWLAHGLW7TNJimNc5a9MUEQkSr0fgKgc'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: bce277d1-7efa-48d8-9a1b-b588bb45ba1c
    internal-label: Channels Activity
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 100%
---
# Réception de SMS{#inbound-sms}



L’activité **Réception de SMS** permet de récupérer et de traiter des SMS depuis un compte externe.

## Propriétés {#properties}

![](assets/sms_rec_edit.png)

Le premier onglet de l’activité **Réception de SMS** vous permet de renseigner les paramètres de routage des SMS et de saisir le script à exécuter à la réception de chaque message. Le deuxième onglet vous permet d’attribuer un planning à l’activité et le troisième onglet définit les conditions d’expiration de l’activité.

1. **[!UICONTROL Routage SMS]** : sélectionnez le compte externe à utiliser pour la réception des SMS. Les comptes externes sont configurés via le nœud **[!UICONTROL Administration > Plateforme > Comptes externes]** de l&#39;arborescence. [En savoir plus](../../v8/config/external-accounts.md)
1. **[!UICONTROL Script]**
1. **[!UICONTROL Planning]**

   ![](assets/sms_rec_edit_2.png)

1. **[!UICONTROL Expiration]**

Les onglets **[!UICONTROL Script]**, **[!UICONTROL Planning]** et **[!UICONTROL Expiration]** sont décrits dans la section [Réception d’emails](inbound-emails.md).
