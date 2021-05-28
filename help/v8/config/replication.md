---
solution: Campaign v8
product: Adobe Campaign
title: Workflows techniques et réplication des données
description: Workflows techniques et réplication des données
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4,df76e7ff-3b97-41be-abc2-640748680ff3
source-git-commit: ab7e458db5ad5696d144c17f6e89e4437a476d11
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 71%

---

# Workflows techniques et réplication des données

## Workflows techniques{#tech-wf}

Adobe Campaign s’accompagne d’un ensemble de workflows techniques intégrés. Les workflows techniques exécutent des processus ou des traitements planifiés de manière régulière sur le serveur.

Ces workflows effectuent des opérations de maintenance sur la base de données, tirent parti des informations de tracking contenues dans les logs de diffusion, créent des campagnes récurrentes, etc.

[!DNL :arrow_upper_right:] La liste complète des workflows techniques est présentée dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html?lang=fr)


Outre ces workflows techniques, Campaign v8 s’appuie sur des workflows techniques spécifiques pour gérer la [réplication des données](#data-replication).

* **[!UICONTROL Répliquer les tables de référence]**
Ce workflow effectue une réplication automatique des tables intégrées qui doivent être présentes dans la base de données locale de Campaign (Postgres) et la base de données cloud ([!DNL Snowflake]). Il est planifié pour s’exécuter toutes les heures, quotidiennement. Si le champ **lastModified** existe, la réplication se produit de manière incrémentielle. Dans le cas contraire, la table entière est répliquée. L’ordre des tables dans le tableau ci-dessous correspond à celui utilisé par le workflow de réplication.
* **[!UICONTROL Répliquer les données Staging]**
Ce workflow réplique les données Staging pour les appels unitaires. Il est planifié pour s’exécuter toutes les heures, quotidiennement.
* **[!UICONTROL Déployer immédiatement FFDA]**\
   Ce workflow effectue un déploiement immédiat dans la base de données cloud.
* **[!UICONTROL Répliquer les données FFDA immédiatement]**
Ce workflow réplique les données XS pour un compte externe donné.

Ces workflows techniques sont disponibles à partir du nœud **[!UICONTROL Administration > Exploitation > Workflows techniques > Réplication FFDA complète]** de l’Explorateur Campaign. **Ils ne doivent pas être modifiés.**

Si nécessaire, vous pouvez lancer manuellement la synchronisation des données. Pour ce faire, cliquez avec le bouton droit de la souris sur l&#39;activité **Planificateur** et sélectionnez **Traitement anticipé de la (des) tâche(s)**.

## Réplication des données{#data-replication}

Certaines tables intégrées sont répliquées de la base de données locale de Campaign vers la base de données [!DNL Snowflake] cloud par le biais de workflows dédiés décrits ci-dessus.

Les stratégies de réplication sont basées sur la taille des tables. Certaines tables sont répliquées en temps réel. D’autres le sont sur une base horaire. Certaines tables sont mises à jour de manière incrémentielle tandis que d’autres sont remplacées.

Outre le workflow technique intégré **Répliquer les tables de référence**, vous pouvez forcer la réplication des données dans vos workflows.

Vous pouvez ainsi :

* ajoutez une activité **Code JavaScript** spécifique avec le code suivant :

```
nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
```

![](assets/jscode.png)


* ajoutez une activité **nlmodule** spécifique avec la commande suivante :

```
nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
```

![](assets/nlmodule.png)

**Rubriques connexes**

[!DNL :arrow_upper_right:] Découvrez comment commencer à utiliser les workflows dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=fr#automating-with-workflows)

[!DNL :bulb:] Accéder aux périodes de conservation des données dans  [cette section](../dev/datamodel-best-practices.md#data-retention)
