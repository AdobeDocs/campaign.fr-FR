---
title: Réplication des données
description: Workflows techniques et réplication des données
feature: Workflows, FFDA
role: Developer
level: Intermediate
exl-id: 7b145193-d4ae-47d0-b694-398c1e35eee4
source-git-commit: b8f774ce507cff67163064b6bd1341b31512c08f
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 9%

---


# Réplication des données {#wf-data-replication}

## Principe

Dans le contexte d’un déploiement [ Enterprise (FFDA)](enterprise-deployment.md), la réplication de données garantit que les deux bases de données, la base de données locale Campaign (PostgreSQL) et la base de données Cloud ([!DNL Snowflake]), sont opérationnelles en parallèle et restent synchronisées en temps réel.

La base de données cloud ([!DNL Snowflake]) est optimisée pour gérer les lots de données volumineux, comme la mise à jour d’un million d’adresses. Dans le même temps, la base de données locale de Campaign (PostgreSQL) est mieux adaptée aux opérations individuelles ou à petit volume, comme la mise à jour d’une adresse de contrôle unique. La synchronisation s’effectue automatiquement et de manière transparente en arrière-plan, en veillant à ce que les données de la base de données locale de Campaign (PostgreSQL) soient dupliquées dans la base de données cloud ([!DNL Snowflake]) en temps réel, ce qui permet de synchroniser les deux bases de données. La synchronisation des données implique des schémas, des tables et des données.

➡️ [Découvrez le fonctionnement de la réplication des données en vidéo](#video)

## Modes de réplication {#modes}

La réplication des données peut se produire dans différents modes en fonction du cas d’utilisation.

* La **réplication à la volée** gère les cas où la duplication en temps réel est essentielle. Elle repose sur des threads techniques spécifiques pour répliquer immédiatement les données dans des cas d’utilisation tels que la création d’une diffusion ou la mise à jour d’une adresse de contrôle.
* La **réplication planifiée** est utilisée lorsque la synchronisation immédiate n’est pas requise. La réplication planifiée utilise des [workflows techniques](#workflows) spécifiques qui s’exécutent toutes les heures pour synchroniser les données, comme les règles de typologie.

## Politiques de réplication

Les politiques de réplication définissent la quantité de données répliquées à partir d’une table de base de données locale Campaign (PostgreSQL). Ces politiques dépendent de la taille de la table et du cas d’utilisation spécifique. Certaines tables sont mises à jour de manière incrémentielle tandis que d’autres sont entièrement répliquées. Il existe trois principaux types de politiques de réplication :

* **XS** : cette politique est utilisée pour les tables de relativement petite taille. La table entière est répliquée en une seule fois. La réplication incrémentielle évite de répliquer à plusieurs reprises les mêmes données à l’aide d’un pointeur d’horodatage pour ne répliquer que les modifications récentes.
* **SingleRow** : cette politique ne reproduit qu’une ligne à la fois. Il est généralement utilisé pour la réplication à la volée impliquant les objets Campaign actuels et les objets associés.
* **SomeRows** : cette politique est conçue pour répliquer un sous-ensemble limité de données à l’aide de définitions de requête ou de filtres. Il est utilisé pour les tables plus volumineuses où une réplication sélective est nécessaire.

## Workflows de réplication {#workflows}

Campaign v8 s’appuie sur des workflows techniques spécifiques pour gérer la réplication planifiée des données. Ces workflows techniques sont disponibles à partir du nœud **[!UICONTROL Administration > Exploitation > Workflows techniques > Réplication FFDA complète]** de l&#39;explorateur Campaign. **Ils ne doivent pas être modifiés.**

Les workflows techniques exécutent des processus ou des traitements, planifiés de manière régulière sur le serveur. La liste complète des workflows techniques est détaillée sur [cette page](https://experienceleague.adobe.com/docs/campaign/automation/workflows/introduction/wf-type/technical-workflows.html?lang=fr){target="_blank"}.

Les workflows techniques assurant la réplication des données sont les suivants :

| Workflow technique | Description |
|------|-----------|
| **[!UICONTROL Répliquer les tables de référence]** (ffdaReplicateReferenceTables) | Effectue la réplication automatique des tables intégrées qui doivent être présentes dans la base de données locale de Campaign (PostgreSQL) et la base de données cloud ([!DNL Snowflake]). Il est planifié pour s&#39;exécuter toutes les heures, quotidiennement. Si le champ **lastModified** existe, la réplication se produit de manière incrémentielle. Dans le cas contraire, la table entière est répliquée. |
| **[!UICONTROL Répliquer les données Staging]** (ffdaReplicateStagingData) | Réplique les données Staging pour les appels unitaires. Il est planifié pour s&#39;exécuter toutes les heures, quotidiennement. |
| **[!UICONTROL Déployer immédiatement FFDA]** (ffdaDeploy) | Effectue un déploiement immédiat dans la base de données cloud. |
| **[!UICONTROL Répliquer les données FFDA immédiatement]** (ffdaReplicate) | Réplique les données XS pour un compte externe donné. |

Si nécessaire, vous pouvez lancer manuellement la synchronisation des données. Pour ce faire, cliquez avec le bouton droit de la souris sur l&#39;activité **Planificateur** et sélectionnez **Traitement anticipé de la (des) tâche(s)**.

Outre le workflow technique intégré **Répliquer les tables de référence**, vous pouvez forcer la réplication des données dans vos workflows à l’aide de l’une de ces méthodes

+++Comment forcer la réplication des données

* Ajoutez une activité **Code JavaScript** spécifique avec le code suivant :

  ```
  nms.replicationStrategy.StartReplicateStagingData("dem:sampleTable")
  ```

  ![](assets/jscode.png)

* Ajoutez une activité **nlmodule** spécifique avec la commande suivante :

  ```
  nlserver ffdaReplicateStaging -stagingSchema -instance:acc1
  ```

  ![](assets/nlmodule.png)

+++

<br/>

>[!NOTE]
>
>La réplication à la volée est gérée par des threads techniques spécifiques plutôt que par des workflows. La configuration de ce mode est gérée dans le fichier serverConf.xml . Vous pouvez configurer serverConf.xml pour qu’il corresponde à des cas d’utilisation spécifiques, comme demander que les tables XS soient répliquées de manière incrémentielle plutôt que entièrement. Pour plus d’informations, contactez votre représentant ou représentante Adobe.

## API

Les API permettent la réplication des données personnalisées et prêtes à l’emploi de la base de données locale de Campaign (PostgreSQL) vers la base de données cloud ([!DNL Snowflake]). Ces API vous permettent de contourner les workflows prédéfinis et de personnaliser la réplication en fonction d’exigences spécifiques, telles que la réplication de tables personnalisées.

Exemple :

```
var dataSource = "nms:extAccount:ffda";
var xml = xtk.builder.CopyXxlData(
    <params dataSource={dataSource} policy="xs">
        <srcSchema name="cus:recipient"/>
    </params>
);
```

## Files d’attente de réplication

Lorsque des volumes élevés de demandes de réplication se produisent simultanément, des problèmes de performances peuvent survenir dans la base de données cloud ([!DNL Snowflake]) en raison de verrous au niveau de la table lors des opérations de FUSION. Pour pallier ce problème, les workflows de réplication centralisés regroupent les requêtes en files d’attente.

Chaque file d&#39;attente est gérée par un workflow technique, qui gère la réplication pour une table spécifique, exécutant les demandes en attente comme une seule opération de FUSION. Ces workflows sont déclenchés toutes les 20 secondes pour traiter les nouvelles demandes de réplication :

| Workflow technique | Description |
|------|-----------|
| **Répliquer la file d’attente nmsDelivery** (ffdaReplicateQueueDelivery) | File d&#39;attente pour la table `nms:delivery`. |
| **File d’attente nmsDlvExclusion de réplication** (ffdaReplicateQueueDlvExclusion) | File d&#39;attente pour la table `nms:dlvExclusion`. |
| **File d’attente nmsDlvMidRemoteIdRel de réplication** (ffdaReplicateQueueDlvMidRemoteIdRel) | File d&#39;attente pour la table `nms:dlvRemoteIdRel`. |
| **Répliquer la file d’attente nmsTrackingUrl** (ffdaReplicateQueueTrackingUrl)<br/>**Répliquer la file d’attente nmsTrackingUrl en simultanéité** (ffdaReplicateQueueTrackingUrl_2) | Files d’attente en simultanéité pour la table `nms:trackingUrl`, utilisant deux workflows pour améliorer l’efficacité en traitant les requêtes en fonction de priorités différentes. |

## Tutoriel {#video}

Cette vidéo présente les concepts clés des bases de données utilisées par Adobe Campaign v8, les raisons de la réplication des données, les données qui sont répliquées et le fonctionnement du processus de réplication.

>[!VIDEO](https://video.tv.adobe.com/v/334460?quality=12)

D’autres tutoriels sur la console cliente Campaign v8 sont disponibles [ici](https://experienceleague.adobe.com/fr/docs/campaign-learn/tutorials/overview).
