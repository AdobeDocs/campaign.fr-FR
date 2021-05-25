---
solution: Campaign v8
product: Adobe Campaign
title: 'Prise en main du modèle de données de Campaign '
description: 'Prise en main du modèle de données de Campaign '
feature: Vue d'ensemble
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896,b1319b34-ee07-48ed-9ab1-e2d12d3d99f8
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 43%

---

# Prise en main du modèle de données de Campaign {#gs-ac-datamodel}

Un modèle de données d’usine est fourni avec Adobe Campaign. Cette section donne un certain nombre de détails sur les tables intégrées du modèle de données d’Adobe Campaign et leurs interactions. Adobe Campaign repose sur une base de données Cloud contenant des tables liées entre elles.

La structure de base du modèle de données Adobe Campaign peut être décrite comme suit:

* **Table** des destinataires : Le modèle de données repose sur une table principale qui est par défaut la table des destinataires (nmsRecipient). Cette table permet de stocker tous les profils marketing.

   :bulb: Pour plus d’informations sur la table des destinataires, voir [cette section](#ootb-profiles).

* **Table** de diffusion : Le modèle de données comprend également une partie dédiée au stockage de toutes les activités marketing. Généralement, il s&#39;agit de la table de diffusion (NmsDelivery). Chaque enregistrement de cette table représente une action de diffusion ou un modèle de diffusion. Elle contient tous les paramètres nécessaires pour effectuer des diffusions telles que la cible, le contenu, etc.

* **Tables** de logs : Ces tables stockent tous les logs associés à l&#39;exécution des campagnes.

   Les logs de diffusion sont tous des messages envoyés aux destinataires ou aux appareils sur tous les canaux. La table des logs de diffusion principale (NmsBroadLogRcp) contient les logs de diffusion pour tous les destinataires.
La table principale des logs de tracking (NmsTrackingLogRcp) stocke les logs de tracking pour tous les destinataires. Les logs de tracking se rapportent aux réactions des destinataires, telles que les ouvertures d’email et les clics. Chaque réaction correspond à un log de tracking.
Les mpgs de diffusion et de tracking sont supprimés après une certaine période, spécifiée dans Adobe Campaign et modifiable. Il est donc vivement recommandé d’exporter les logs de façon régulière.

* **Tables techniques** : Rassemblez les données techniques utilisées pour le processus applicatif, y compris les opérateurs et les droits utilisateur (xtkGroup), les dossiers (XtkFolder).

>[!NOTE]
>
>Pour obtenir la description de chaque table, accédez à Admin > Paramétrage > Schémas de données, sélectionnez une ressource dans la liste et cliquez sur l’onglet **Documentation**.

Lorsque vous commencez à utiliser Adobe Campaign, vous devez évaluer le modèle de données par défaut pour déterminer quelle table est adaptée au stockage de vos données marketing.

Vous pouvez utiliser la table des destinataires par défaut avec les champs d&#39;usine, comme décrit dans [cette section](#ootb-profiles). En cas de besoin, vous pouvez l’étendre avec deux mécanismes :

* [Étendez une table existante avec de nouveaux champs.](extend-schema.md) Par exemple, vous pouvez ajouter un nouveau champ &quot;Fidélité&quot; à la table des destinataires.
* [Créez une nouvelle table](create-schema.md), par exemple une table &quot;Achat&quot; répertoriant tous les achats effectués par chaque profil de la base de données, et liez-la à la table des destinataires.

:bulb: Découvrez les bonnes pratiques lorsque vous utilisez le modèle de données Campaign dans [cette section](datamodel-best-practices.md).

## Table de profils intégrée {#ootb-profiles}

La table des destinataires intégrée (nmsrecipient) dans Adobe Campaign constitue un bon point de départ pour la création de votre modèle de données. Elle comporte un certain nombre de champs prédéfinis et de liens vers des tables faciles à étendre. Son emploi est particulièrement efficace si vous ciblez principalement les destinataires, car elle s&#39;appuie sur un modèle de données centré sur ces derniers.

Les avantages de l&#39;utilisation de la table des destinataires standard sont les suivants :

* Utilisation prête à l’emploi avec des fonctionnalités clés telles que les abonnements, les listes de contrôle, etc.
* Disposer d&#39;une base de données marketing dotée d&#39;un modèle de données axé sur les destinataires
* Permettre une mise en œuvre plus rapide
* Faciliter les prestations de maintenance des intervenants chargés de l&#39;assistance et des partenaires

Il est possible d&#39;étendre la table des destinataires, mais pas de réduire le nombre de champs ou de liens dans la table.

:bulb: Découvrez comment étendre un schéma existant dans [cette section](extend-schema.md).

:flèche_upper_right : Découvrez des exemples d’extensions de table de destinataires intégrée dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#extending-a-table)

Vous pouvez également utiliser une autre table de destinataires pour mieux répondre aux besoins de votre entreprise ou de vos besoins fonctionnels. Cette méthode est fournie avec des restrictions et est décrite dans [cette section](custom-recipient.md).

## Tables Campaign et base de données Cloud

Pour une meilleure compréhension de la gestion des tables dans Campaign v8, notez que les tables sont répliquées entre Campaign et sa base de données Snowflake Cloud.

:bulb: Pour en savoir plus sur la stratégie et les mécanismes de réplication, consultez [cette section](../config/replication.md).

**Rubriques connexes :**

:bulb: Découvrez comment importer des profils dans [cette section](../start/import.md)
:bulb: En savoir plus sur les audiences Campaign dans [cette section](../start/audiences.md)
