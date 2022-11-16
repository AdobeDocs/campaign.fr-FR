---
title: Prise en main du modèle de données de Campaign
description: Prise en main du modèle de données Campaign et exploitation des données de vos sources pour bénéficier de vos sorties de communication et de marketing.
feature: Data Model
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896
source-git-commit: 507f30d16eecf5400ee88a4d29913e4cdaca9cba
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 92%

---

# Prise en main du modèle de données de Campaign{#gs-ac-datamodel}

Un modèle de données d’usine est fourni avec Adobe Campaign. Cette section fournit un certain nombre de détails sur les tables intégrées du modèle de données d&#39;Adobe Campaign et leurs interactions. Adobe Campaign repose sur une base de données cloud contenant des tables liées entre elles.

La structure de base du modèle de données Adobe Campaign peut être décrite comme suit :

* **Table des destinataires** : le modèle de données repose sur une table principale qui est par défaut la table des destinataires (nmsRecipient). Cette table enregistre tous les profils marketing.

   ![](../assets/do-not-localize/glass.png) Pour plus d&#39;informations sur la table des destinataires, consultez cette [section](#ootb-profiles).

* **Table des diffusions** : le modèle de données comprend également une partie dédiée au stockage de toutes les activités marketing. Généralement, il s&#39;agit de la table des diffusions (NmsDelivery). Chaque enregistrement de cette table représente une action de diffusion ou un modèle de diffusion. Elle contient tous les paramètres nécessaires pour effectuer des diffusions telles que la cible, le contenu, etc.

* **Tables de logs** : ces tables stockent tous les logs associés à l&#39;exécution des campagnes.

   Les logs de diffusion sont tous les messages envoyés aux destinataires ou aux appareils sur tous les canaux. Le tableau principal des logs de diffusion (NmsBroadLogRcp) contient les logs de diffusion pour tous les destinataires.
Le tableau principal des logs de suivi (NmsTrackingLogRcp) stocke les logs de suivi pour tous les destinataires. Les logs de tracking se rapportent aux réactions des destinataires, telles que les ouvertures d&#39;e-mail et les clics. Chaque réaction correspond à un log de tracking.
Les mpgs de diffusion et de tracking sont supprimés après une certaine période, spécifiée dans Adobe Campaign et modifiable. Il est donc vivement recommandé d&#39;exporter les logs de façon régulière.

* **Tables techniques** : rassemblent les données techniques utilisées pour le processus d&#39;application, y compris les opérateurs et les droits d&#39;utilisateur (xtkGroup), et les dossiers (XtkFolder).

>[!NOTE]
>
>Pour obtenir la description de chaque table, accédez à Admin > Paramétrage > Schémas de données, sélectionnez une ressource dans la liste et cliquez sur l&#39;onglet **Documentation**.

Lorsque vous commencez à utiliser Adobe Campaign, vous devez évaluer le modèle de données par défaut pour déterminer quelle table est adaptée au stockage de vos données marketing.

Vous pouvez utiliser la table des destinataires par défaut avec les champs d&#39;usine, comme décrit dans [cette section](#ootb-profiles). Le cas échéant, vous pouvez l&#39;étendre avec deux mécanismes :

* [Étendez une table existante](extend-schema.md) avec de nouveaux champs. Par exemple, vous pouvez ajouter un nouveau champ « Fidélité » à la table des destinataires.
* [Créer un tableau](create-schema.md), par exemple une table &quot;Achat&quot; répertoriant tous les achats effectués par chaque profil de la base de données, et la lier à la table des destinataires.

![](../assets/do-not-localize/glass.png) Découvrez les bonnes pratiques d&#39;utilisation du modèle de données Campaign dans [cette section](datamodel-best-practices.md).

## Table des profils intégrée {#ootb-profiles}

La table des destinataires intégrée (nmsrecipient) dʼAdobe Campaign est un bon point de départ pour créer votre modèle de données. Elle comporte un certain nombre de champs prédéfinis et de liens vers des tables faciles à étendre. Son emploi est particulièrement efficace si vous ciblez principalement les destinataires, car elle sʼappuie sur un modèle de données centré sur ces derniers.

Les avantages liés à l&#39;utilisation d&#39;une table des destinataires standard sont les suivants :

* Une utilisation prête à l&#39;emploi, avec des fonctionnalités clés telles que les abonnements, les listes de contrôle, etc.
* La mise à disposition d&#39;une base de données marketing dotée d&#39;un modèle de données axé sur les destinataires
* Une implémentation plus rapide
* Des prestations de maintenance facilitées de la part des intervenants chargés de l&#39;assistance et des partenaires

Il est possible d&#39;étendre la table des destinataires, mais sans réduire le nombre de champs ou de liens qu&#39;elle contient.

![](../assets/do-not-localize/glass.png) Découvrez comment étendre un schéma existant dans [cette section](extend-schema.md).

![](../assets/do-not-localize/book.png) Découvrez des exemples d&#39;extensions de table de destinataires intégrées dans la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=fr#extending-a-table).{target=&quot;_blank&quot;}

Vous pouvez également utiliser une autre table des destinataires, mieux adaptée à vos besoins professionnels ou fonctionnels. Cette méthode s&#39;accompagne de limitations et est décrite dans [cette section](custom-recipient.md).

## Base de données cloud et tables Campaign

Pour une meilleure compréhension de la gestion des tables dans Campaign v8, notez que, dans le cadre d&#39;une [Déploiement Enterprise (FFDA)](../architecture/enterprise-deployment.md), les tables sont répliquées entre Campaign et sa base de données Cloud Snowflake.

![](../assets/do-not-localize/glass.png) Pour en savoir plus sur la stratégie et les mécanismes de réplication, consultez [cette section](../architecture/replication.md).

**Rubriques connexes**

![](../assets/do-not-localize/glass.png) Découvrez comment importer des profils dans [cette section![](../assets/do-not-localize/glass.png)](../start/import.md).
Pour en savoir plus sur les audiences Campaign, consultez [cette section.](../start/audiences.md)
