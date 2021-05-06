---
solution: Campaign Classic
product: campaign
title: Travailler avec Campaign et Adobe Analytics
description: Découvrez comment travailler avec Campaign et Adobe Analytics
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
translation-type: tm+mt
source-git-commit: c2d066ca2f935455861c3d6747c9805c847f2e0d
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 22%

---

# Travailler avec Campaign et Adobe Analytics

## Triggers Experience Cloud

Vous pouvez utiliser des déclencheurs Experience Cloud pour connecter des données entre Adobe Campaign et Adobe Analytics à l’aide du pipeline. Le pipeline récupère les actions ou déclencheurs des utilisateurs de votre site Web. Un abandon de panier est un exemple de déclencheur. Les déclencheurs sont traités dans Adobe Campaign pour envoyer des emails en temps quasi réel.

:speak_bulon: En tant qu’utilisateur Cloud Services géré, [contactez l’Adobe](../start/support.md#support) pour mettre en oeuvre des déclencheurs Experience Cloud avec Campaign.

## Adobe Analytics - Data Connector

POUR METTRE À JOUR LA NOUVELLE INTÉGRATION

Vous pouvez également configurer les connecteurs de données Adobe Analytics pour intégrer Campaign et Analytics.

Le connecteur de données (précédemment appelé Adobe Genesis) permet à Adobe Campaign et Adobe Analytics d’interagir via le **module Connecteurs Web Analytics**. Cette intégration partage les données d’Analytics vers Campaign en tant que segments liés au comportement des utilisateurs suite à un courrier électronique. Inversement, il envoie les indicateurs et les attributs des campagnes par courrier électronique fournies par Adobe Campaign au connecteur de données Adobe Analytics.

Grâce à ces intégrations, Adobe Campaign peut récupérer des données sur le comportement des visiteurs pour un ou plusieurs sites à la suite d’une campagne marketing et (après analyse) exécuter des campagnes de remarketing avec une vue pour les convertir en acheteurs. Inversement, les outils d&#39;analyse Web permettent à Adobe Campaign de transférer des indicateurs et des attributs de campagne à leurs plateformes.

Les champs d&#39;action de chaque outil sont les suivants :

* Adobe Analytics:

   * marque les campagnes email lancées avec Adobe Campaign
   * enregistre le comportement des destinataires, sur le site qu’ils ont parcouru après avoir cliqué sur le courriel de la campagne, sous la forme de segments. Les segments sont liés aux produits abandonnés (affichés mais non ajoutés au panier ou achetés), aux achats ou aux abandons de panier.

* Adobe Campaign:

   * envoie les indicateurs et les attributs de la campagne vers le connecteur qui les transfère vers l&#39;outil de Web Analytics
   * récupère et analyse les segments
   * déclenche une campagne de remarketing

VOIR https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/adobe-analytics-data-connector.html?lang=en#technical-workflows-of-web-analytics-processes

:speak_bulon: En tant qu’utilisateur Cloud Services géré, [contactez l’Adobe](../start/support.md#support) pour intégrer Adobe Analytics Data Connector à Campaign.

