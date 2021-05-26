---
solution: Campaign v8
product: Adobe Campaign
title: Utilisation de Campaign et Adobe Analytics
description: Découvrez comment utiliser Campaign et Adobe Analytics
feature: Vue d'ensemble
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
source-git-commit: 4ae0c968bd68d76d7ceffb91023d5426d6a810ea
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 20%

---

# Utilisation de Campaign et Adobe Analytics


## Connecteur Adobe Analytics

Vous pouvez configurer les connecteurs Adobe Analytics pour intégrer Campaign et Analytics.

Adobe Analytics Connector permet à Adobe Campaign et à Adobe Analytics d’interagir par le biais du module complémentaire **Connecteurs Web Analytics**. Cette intégration partage les données d’Analytics vers Campaign en tant que segments liés au comportement des utilisateurs suite à un email. Inversement, il envoie les indicateurs et les attributs des campagnes email diffusées par Adobe Campaign à Adobe Analytics - connecteur de données.

Avec Adobe Analytics Connector, Adobe Campaign permet de mesurer l’audience Internet (Web Analytics). Grâce à ces intégrations, Adobe Campaign peut récupérer des données sur le comportement des visiteurs d’un ou plusieurs sites à la suite d’une campagne marketing et (après analyse) lancer des campagnes de remarketing afin de les convertir en acheteurs. Inversement, les outils d’analyse Web permettent à Adobe Campaign de transférer des indicateurs et des attributs de campagne vers leurs plateformes.

Les champs d&#39;action de chaque outil sont les suivants :

* **Adobe Analytics**

   * marque les campagnes email lancées avec Adobe Campaign
   * enregistre le comportement des destinataires, sous la forme de segments, sur le site qu’ils ont consulté après avoir cliqué sur l’email de la campagne. Les segments sont liés aux produits abandonnés (consultés mais non ajoutés au panier ou achetés), aux achats ou aux abandons de panier.

* **Adobe Campaign**

   * envoie les indicateurs et les attributs de la campagne vers le connecteur qui les transfère vers l&#39;outil de Web Analytics
   * récupère et analyse les segments
   * déclenche une campagne de remarketing

En savoir plus sur Adobe Campaign et Adobe Analytics sur [cette page](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/adobe-analytics-data-connector.html)

[!DNL :speech_balloon:]  En tant qu’utilisateur Cloud Services géré,  [contactez ](../start/campaign-faq.md#support) Adobe pour intégrer Adobe Analytics Data Connector à Campaign.


## Triggers Experience Cloud

Vous pouvez utiliser des Triggers Experience Cloud pour connecter les données entre Adobe Campaign et Adobe Analytics à l’aide du pipeline. Le pipeline récupère les actions ou déclencheurs de l’utilisateur sur votre site web. Un abandon de panier est un exemple de déclencheur. Les déclencheurs sont traités dans Adobe Campaign pour envoyer des emails en temps quasi réel.

Pour en savoir plus sur Adobe Campaign et les Triggers Experience Cloud, consultez [cette page](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/experience-triggers/about-triggers.html?lang=en).

[!DNL :speech_balloon:]  En tant qu’utilisateur Cloud Services gérés,  [contactez ](../start/campaign-faq.md#support) Adobe pour mettre en oeuvre des déclencheurs Experience Cloud avec Campaign.
