---
title: Prise en main du modèle de données de Campaign
description: Commencez avec le modèle de données Campaign et l’utilisation des données provenant de vos sources pour améliorer vos sorties de communication et de marketing.
feature: Data Model
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 93%

---

# Prise en main du modèle de données de Campaign {#gs-ac-datamodel}

Un modèle de données d’usine est fourni avec Adobe Campaign. Cette section fournit un certain nombre de détails sur les tables intégrées du modèle de données d&#39;Adobe Campaign et leurs interactions. Adobe Campaign repose sur une base de données cloud contenant des tables liées entre elles.

La structure de base du modèle de données Adobe Campaign peut être décrite comme suit :

* **Table des destinataires** : le modèle de données repose sur une table principale qui est par défaut la table des destinataires (**nmsRecipient**). Cette table enregistre tous les profils marketing. En savoir plus sur la table des destinataires dans [cette section](#ootb-profiles).

* **Table de diffusion** : cette table stocke un enregistrement par action de diffusion. Généralement, il s’agit de la table de diffusion (**NmsDelivery**). de cette table représente une action de diffusion ou un modèle de diffusion. Elle contient tous les paramètres nécessaires pour effectuer des diffusions telles que la cible, le contenu, etc. Chaque enregistrement est mis à jour plusieurs fois pour refléter la progression de la diffusion.

* **Tables de logs** : ces tables stockent tous les logs associés à l&#39;exécution des campagnes.

   * Les logs de diffusion sont tous les messages envoyés aux destinataires ou aux appareils sur tous les canaux. La table principale des logs de diffusion (**NmsBroadLogRcp**) contient les logs de diffusion de tous les destinataires.
   * La table **nmsBroadlog** est la plus volumineuse du système. Elle stocke un enregistrement par message envoyé. Les enregistrements sont insérés et mis à jour, afin de suivre le statut de la diffusion, puis supprimés lorsque l’historique est purgé.
   * La table principale des logs de tracking (**NmsTrackingLogRcp**) stocke les logs de tracking pour tous les destinataires. Les logs de tracking se rapportent aux réactions des destinataires, telles que les ouvertures d’e-mail et les clics. Chaque réaction correspond à un log de tracking.

  Les mpgs de diffusion et de tracking sont supprimés après une certaine période, spécifiée dans Adobe Campaign et modifiable. Il est donc vivement recommandé d&#39;exporter les logs de façon régulière.

* **Tables techniques** : rassemble les données techniques utilisées pour le processus applicatif, y compris les opérateurs/opératrices et les droits d’utilisation (**xtkGroup**), les sessions d’utilisation (**xtkSessionInfo**), les dossiers de l’arborescence de l’explorateur (**XtkFolder**), les workflows (**xtkWorkflow**), etc.

>[!NOTE]
>
>Pour obtenir la description de chaque table, accédez à **Administration > Configuration > Schémas de données**, sélectionnez une ressource dans la liste et cliquez sur l’onglet **Documentation**.

Lorsque vous commencez à utiliser Adobe Campaign, vous devez évaluer le modèle de données par défaut pour déterminer quelle table est adaptée au stockage de vos données marketing.

Vous pouvez utiliser la table des destinataires par défaut avec les champs d&#39;usine, comme décrit dans [cette section](#ootb-profiles). Le cas échéant, vous pouvez l&#39;étendre avec deux mécanismes :

* [Étendez une table existante](extend-schema.md) avec de nouveaux champs. Par exemple, vous pouvez ajouter un nouveau champ « Fidélité » au tableau des destinataires.
* [Créez un tableau](create-schema.md), par exemple un tableau « Achat » répertoriant tous les achats effectués par chaque profil de la base de données, et liez-le au tableau des destinataires.

Découvrez les bonnes pratiques d’utilisation du modèle de données Campaign dans [cette section](datamodel-best-practices.md).

## Table des profils intégrée {#ootb-profiles}

La table des destinataires intégrée (nmsrecipient) dʼAdobe Campaign est un bon point de départ pour créer votre modèle de données. Elle comporte un certain nombre de champs prédéfinis et de liens vers des tables faciles à étendre. Son emploi est particulièrement efficace si vous ciblez principalement les destinataires, car elle sʼappuie sur un modèle de données centré sur ces derniers.

Les avantages liés à l&#39;utilisation d&#39;une table des destinataires standard sont les suivants :

* Une utilisation prête à l&#39;emploi, avec des fonctionnalités clés telles que les abonnements, les listes de contrôle, etc.
* La mise à disposition d&#39;une base de données marketing dotée d&#39;un modèle de données axé sur les destinataires
* Une implémentation plus rapide
* Des prestations de maintenance facilitées de la part des intervenants chargés de l&#39;assistance et des partenaires

Il est possible d&#39;étendre la table des destinataires, mais sans réduire le nombre de champs ou de liens qu&#39;elle contient.

Découvrez comment étendre un schéma existant dans [cette section](extend-schema.md).

Découvrez des exemples d’extensions de table de destinataires intégrées dans . [Documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=fr#extending-a-table){target="_blank"}

Vous pouvez également utiliser une autre table des destinataires, mieux adaptée à vos besoins professionnels ou fonctionnels. Cette méthode s&#39;accompagne de limitations et est décrite dans [cette section](custom-recipient.md).

## Base de données cloud et tables Campaign

Pour une meilleure compréhension de la gestion des tables dans Campaign v8, notez que, dans le cadre d&#39;une [Déploiement Enterprise (FFDA)](../architecture/enterprise-deployment.md), les tables sont répliquées entre Campaign et sa base de données Cloud Snowflake.

En savoir plus sur la stratégie et les mécanismes de réplication dans [cette section](../architecture/replication.md).

**Rubriques connexes** 

Découvrez comment importer des profils dans [cette section](../start/import.md)
En savoir plus sur les audiences Campaign dans [cette section](../start/audiences.md)
