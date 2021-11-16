---
title: Modification de votre table de destinataires par défaut
description: Découvrez comment utiliser une table de destinataires personnalisée
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
source-git-commit: 7234ca65f785b005b11851a5cd88add8cddeff4f
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 100%

---

# Utilisation d’une table des destinataires personnalisée{#gs-ac-custom-recipient}

Adobe Campaign sʼaccompagne dʼune table des profils native : **nmsRecipient**. Cette table comporte un certain nombre de champs prédéfinis et de tables faciles à étendre. En savoir plus au sujet de cette table sur [cette page](datamodel.md#ootb-profiles).

L&#39;extension de table native offre de la flexibilité. Toutefois, elle ne permet pas de supprimer certains champs ou liens inutilisés. Par conséquent, l&#39;utilisation d&#39;une table de destinataires personnalisée est une option qui peut s&#39;avérer pratique lorsque votre modèle de données diffère considérablement de la structure de table de destinataires native Campaign, ou encore ou si vous disposez d&#39;un grand nombre de profils.  Toutefois, cette méthode nécessite de prendre certaines précautions lors de son implémentation.

![](../assets/do-not-localize/book.png) Découvrez comment configurer votre instance pour utiliser une table des destinataires personnalisée dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/use-a-custom-recipient-table/about-custom-recipient-table.html?lang=fr){target=&quot;_blank&quot;}.