---
solution: Campaign Classic
product: campaign
title: Workflows techniques et réplication des données
description: Workflows techniques et réplication des données
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4,df76e7ff-3b97-41be-abc2-640748680ff3
translation-type: tm+mt
source-git-commit: a67c83eb531c795d621fdf36696ae4bde2151dba
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 3%

---

# Workflows techniques et réplication des données

## Workflows techniques

Adobe Campaign est livré avec un ensemble de workflows techniques intégrés. Les workflows techniques exécutent des processus ou des tâches, planifiés régulièrement sur le serveur.

Ces workflows effectuent des opérations de maintenance sur la base de données, tirent parti des informations de suivi dans les logs de diffusion, créent des campagnes récurrentes, etc.

:flèche_supérieur_droite : La liste complète des workflows techniques est détaillée dans [la documentation Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html?lang=en#overview)

Outre ces workflows techniques, Campaign v8 s&#39;appuie sur des workflows techniques spécifiques pour gérer la [réplication des données](#data-replication).

* **[!UICONTROL Répliquer]**
les tables de référenceCe processus effectue la réplication automatique des tables de référence qui doivent être présentes dans la base de données locale Campaign (Postgres) et la base de données Cloud ([!DNL Snowflake]). Il est planifié pour s’exécuter toutes les heures, tous les jours. Si le champ **lastModified** existe, la réplication se produit de manière incrémentielle, sinon la table entière est répliquée. L&#39;ordre des tables dans la baie ci-dessous correspond à l&#39;ordre utilisé par le processus de réplication.
* **[!UICONTROL Répliquer les]**
données d&#39;évaluationCe processus répliquera les données d&#39;évaluation pour les appels uniques. Il est planifié pour s’exécuter toutes les heures, tous les jours.
* **[!UICONTROL Déployer immédiatement FFDA]**\
   Ce processus effectue un déploiement immédiat dans la base de données Cloud.
* **[!UICONTROL Répliquer]**
immédiatement les données FFDACe processus répliquera les données XS pour un compte externe donné.

Ces workflows techniques sont disponibles à partir du noeud **[!UICONTROL Administration > Production > Workflows techniques > Réplication FFDA complète]** de Campaign Explorer.

## Réplication des données{#data-replication}

Les tables sont répliquées de la base de données Campaign vers la base de données [!DNL Snowflake] Cloud par le biais de workflows dédiés décrits ci-dessus.

Les stratégies de réplication sont basées sur la taille de la table. Certaines tables seront répliquées. Certains tableaux seront répliqués en temps réel, d&#39;autres seront répliqués toutes les heures. Certains tableaux seront mis à jour progressivement lorsque d&#39;autres seront remplacés.

| Espace de noms | Tableau | réplication de processus | Réplication en temps réel |
| --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- | --------------------- |
| XTK | xtk:enum<br>xtk:enumValue<br>xtk:enumAlias<br>xtk:folder<br>xtk:formRendering<br>xtk:opérateur<br>xtk:group<br>xtk:report<br>xtk:olap be<br>xtk:olapDimension<br>xtk:olapMeasure<br>xtk:dictionaryString<br> | Oui (incrémentiel) | Oui |
| XTK | xtk:opsecurity<br>xtk:rights<br>xtk:operatorGroup<br>xtk:reportHistory<br>xtk:reportRights | Oui (plein) | Oui |
| NMS | nms:budget<br>nms:programme<br>nms:operation<br>nms:plan<br>nms:typologyRule<br>nms:typology<br>nms:extAccount<br>nms:deliveryMapping<br>nms:diffusion (réplication immédiate)<br>nms:seed Member<br>nms:webApp<br>nms:trackingUrl (réplication immédiate)<br>nms:service<br>nms:offerEnv<br>nms:offerCategory<br>nms:offerSpace<br>nms:offre ms <br>nms:offerView<br>nms:destinataire (incrémentiel ?)<br>nms:<br>groupnms:<br>dlvExclusionnms:stock | Oui (incrémentiel) | Oui |
| NMS | nms:country<br>nms:localOrgUnit<br>nms:state<br>nms:SuppressionAddress<br>nms:SuppressionDomain<br>nms:catégorie<br>nms:trackingUrlInfo<br>nms:webTrackingLog<br>nms:mobileApp&lt;a 8/>nms:budgetCategory<br>nms:costType<br>nms:costCenter<br>nms:costStructure<br>nms:stockLine<br>nms:costLine<br>nms:costLine<br> | Oui (plein) | Oui |
| NMS | nms:address<br>nms:userAgent<br>nms:userAgentReject<br>nms:userAgentStats<br>nms:wideLogMsg<br>nms:broadLog<br>nms:trackingLog<br>nms:deliveryLogStats<br>nms ms:appSubscription<br>nms:proposition<br>nms:rcpGrpRel<br>nms:broadLogRcp<br>nms:excludeLogRcp<br>nms:trackingLogRcp<br>nms:propositionms cp<br>nms:localValidationRcp<br>nms:visiteur<br>nms:broadLogVisitor<br>nms:trackingLogVisitor<br>nms:propositionVisitor<br>nms:webAppLog cp<br>nms:appSubscriptionRcp<br>nms:wideLogAppSubRcp<br>nms:excludeLogAppSubRcp<br>nms:trackingLogAppSubRcp<br>événement nms Histo<br>nms:broadLogEventHisto<br>nms:trackingLogEventHisto<br>nms:abonnement<br>nms:subHisto<br>nms:trackingStats (utilisation de Snowflake uniquement)<br>ms:tmpBroadcast (utilisation de Snowflake uniquement)<br>nms:tmpBroadcastExclusion (utilisation de Snowflake uniquement)<br>nms:tmpBroadcastPaper (utilisation de Snowflake uniquement) | Non | Non |

**Rubriques connexes :**

:flèche_supérieur_droite : Découvrez comment commencer à utiliser les flux de travaux dans [la documentation du Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)

: bulb: Accéder aux périodes de rétention des données dans [cette section](../dev/datamodel-best-practices.md#data-retention)
