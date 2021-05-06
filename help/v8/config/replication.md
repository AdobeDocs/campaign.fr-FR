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
source-git-commit: 9efd6442336a62e627b0da4e17fa742f59f715f9
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 2%

---

# Workflows techniques et réplication des données

## Workflows techniques

Adobe Campaign est livré avec un ensemble de workflows techniques intégrés. Les workflows techniques exécutent des processus ou des tâches, planifiés régulièrement sur le serveur.

Ces workflows effectuent des opérations de maintenance sur la base de données, tirent parti des informations de suivi dans les logs de diffusion, créent des campagnes récurrentes, etc.

:flèche_supérieur_droite : La liste complète des workflows techniques est détaillée dans [la documentation Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html?lang=en#overview)

Outre ces workflows techniques, Campaign v8 s&#39;appuie sur des workflows techniques spécifiques pour gérer la [réplication des données](#data-replication).

* **[!UICONTROL Répliquer]**
les tables de référenceCe processus effectue la réplication automatique des tables de référence qui doivent être présentes dans la base de données locale Campaign (Postgres) et la base de données Cloud (Snowflake). Il est planifié pour s’exécuter toutes les heures, tous les jours. If 
**** lastModifiedfield existe, la réplication se produit progressivement, sinon la table entière est répliquée. L&#39;ordre des tables dans la baie ci-dessous correspond à l&#39;ordre utilisé par le processus de réplication.
* **[!UICONTROL Répliquer les]**
données d&#39;évaluationCe processus répliquera les données d&#39;évaluation pour les appels uniques. Il est planifié pour s’exécuter toutes les heures, tous les jours.
* **[!UICONTROL Déployer immédiatement FFDA]**\
   Ce processus effectue un déploiement immédiat dans la base de données Cloud.
* **[!UICONTROL Répliquer]**
immédiatement les données FFDACe processus répliquera les données XS pour un compte externe donné.

Ces workflows techniques sont disponibles à partir du noeud **[!UICONTROL Administration > Production > Workflows techniques > Réplication FFDA complète]** de Campaign Explorer.

## Réplication des données{#data-replication}

Les tables sont répliquées de la base de données Campaign vers la base de données Snowflake Cloud par le biais de workflows dédiés décrits ci-dessus.

Les stratégies de réplication sont basées sur la taille de la table. Certaines tables seront répliquées. Certains tableaux seront répliqués en temps réel, d&#39;autres seront répliqués toutes les heures. Certains tableaux seront mis à jour progressivement lorsque d&#39;autres seront remplacés.

**DEVRIONS-NOUS LISTE TOUTES LES TABLES ?**

POUR VÉRIFIER

**Rubriques connexes :**

:flèche_supérieur_droite : Découvrez comment commencer à utiliser les flux de travaux dans [la documentation du Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)

: bulb: Accéder aux périodes de rétention des données dans [cette section](../dev/datamodel-best-practices.md#data-retention)
