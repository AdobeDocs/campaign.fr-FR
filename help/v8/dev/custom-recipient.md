---
title: Modification de votre table de destinataires par défaut
description: Découvrez comment utiliser une table de destinataires personnalisée
feature: Custom Resources, Profiles, Configuration
role: User, Developer
level: Intermediate, Experienced
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
TQID: 'https://experienceleague.adobe.com/W67Z2xVEBDpju5xlL2WiE5ZTzvrFmhuByMvfPb4x6nM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: a2002dba-5e37-4dff-8e04-1cc3ec73558c
    internal-label: Custom resources
  - id: f529d0bd-1401-4c88-9833-43228cc1d40f
    internal-label: Profiles
  - id: a14877cc-63b1-41d9-bf0b-5f97cadd0417
    internal-label: Configuration guidelines
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 88%
---
# Utilisation d’une table des destinataires personnalisée{#gs-ac-custom-recipient}

Adobe Campaign s’accompagne d’une table des profils native : nmsRecipient **.** Cette table comporte un certain nombre de champs prédéfinis et de tables faciles à étendre. En savoir plus au sujet de cette table sur [cette page](datamodel.md#ootb-profiles).

L’extension de table native offre de la flexibilité. Toutefois, elle ne permet pas de supprimer certains champs ou liens inutilisés. Par conséquent, l’utilisation d&#39;une table des destinataires personnalisée peut être une bonne solution lorsque votre modèle de données diffère considérablement de la structure de la table des destinataires native de Campaign, ou si vous disposez d’un grand nombre de profils.  Toutefois, cette méthode nécessite de prendre certaines précautions lors de son implémentation.

Découvrez comment configurer votre instance pour utiliser une table des destinataires personnalisée dans la documentation de [Campaign Classic v7 ](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/use-a-custom-recipient-table/about-custom-recipient-table.html?lang=fr){target="_blank"}.