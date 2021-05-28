---
solution: Campaign v8
product: Adobe Campaign
title: Prise en main du modèle de données de Campaign
description: Prise en main du modèle de données de Campaign
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896,b1319b34-ee07-48ed-9ab1-e2d12d3d99f8
source-git-commit: ab7e458db5ad5696d144c17f6e89e4437a476d11
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 88%

---

# Prise en main du modèle de données de Campaign{#gs-ac-datamodel}

Un modèle de données d’usine est fourni avec Adobe Campaign. Cette section fournit un certain nombre de détails sur les tables intégrées du modèle de données d’Adobe Campaign et leurs interactions. Adobe Campaign repose sur une base de données cloud contenant des tables liées entre elles.

La structure de base du modèle de données Adobe Campaign peut être décrite comme suit :

* **Table des destinataires** : le modèle de données repose sur une table principale qui est par défaut la table des destinataires (nmsRecipient). Cette table permet de stocker tous les profils marketing.

   [!DNL :bulb:] Pour plus d’informations sur la table des destinataires, voir cette [section](#ootb-profiles).

* **Table des diffusions** : le modèle de données comprend également une partie dédiée au stockage de toutes les activités marketing. Généralement, il s’agit de la table des diffusions (NmsDelivery). Chaque enregistrement de cette table représente une action de diffusion ou un modèle de diffusion. Elle contient tous les paramètres nécessaires pour effectuer des diffusions telles que la cible, le contenu, etc.

* **Tables de logs** : ces tables stockent tous les logs associés à l’exécution des campagnes.

   Les logs de diffusion sont tous les messages envoyés aux destinataires ou aux appareils sur tous les canaux. La table des logs de diffusion principale (NmsBroadLogRcp) contient les logs de diffusion pour tous les destinataires.
La table principale des logs de tracking (NmsTrackingLogRcp) stocke les logs de tracking pour tous les destinataires. Les logs de tracking se rapportent aux réactions des destinataires, telles que les ouvertures d’email et les clics. Chaque réaction correspond à un log de tracking.
Les mpgs de diffusion et de tracking sont supprimés après une certaine période, spécifiée dans Adobe Campaign et modifiable. Il est donc vivement recommandé d’exporter les logs de façon régulière.

* **Tables techniques** : Rassemblez les données techniques utilisées pour le processus applicatif, y compris les opérateurs et les droits utilisateur (xtkGroup), les dossiers (XtkFolder).

>[!NOTE]
>
>Pour obtenir la description de chaque table, accédez à Admin > Paramétrage > Schémas de données, sélectionnez une ressource dans la liste et cliquez sur l’onglet **Documentation**.

Lorsque vous commencez à utiliser Adobe Campaign, vous devez évaluer le modèle de données par défaut pour déterminer quelle table est adaptée au stockage de vos données marketing.

Vous pouvez utiliser la table des destinataires par défaut avec les champs d’usine, comme décrit dans [cette section](#ootb-profiles). Le cas échéant, vous pouvez l’étendre avec deux mécanismes :

* [Étendez une table existante](extend-schema.md) avec de nouveaux champs. Par exemple, vous pouvez ajouter un nouveau champ « Fidélité » à la table des destinataires.
* [Créez une table](create-schema.md), par exemple une table « Achat » répertoriant tous les achats effectués par chaque profil de la base de données, puis liez-la à la table des destinataires.

[!DNL :bulb:] Découvrez les bonnes pratiques d’utilisation du modèle de données Campaign dans [cette section](datamodel-best-practices.md).

## Table des profils intégrée {#ootb-profiles}

La table des destinataires intégrée (nmsrecipient) d’Adobe Campaign est un bon point de départ pour créer votre modèle de données. Elle comporte un certain nombre de champs prédéfinis et de liens vers des tables faciles à étendre. Son emploi est particulièrement efficace si vous ciblez principalement les destinataires, car elle s&#39;appuie sur un modèle de données centré sur ces derniers.

Les avantages liés à l’utilisation d’une table des destinataires standard sont les suivants :

* Une utilisation prête à l’emploi, avec des fonctionnalités clés telles que les abonnements, les listes de contrôle, etc.
* La mise à disposition d’une base de données marketing dotée d’un modèle de données axé sur les destinataires
* Une implémentation plus rapide
* Des prestations de maintenance facilitées de la part des intervenants chargés de l’assistance et des partenaires

Il est possible d’étendre la table des destinataires, mais sans réduire le nombre de champs ou de liens qu’elle contient.

[!DNL :bulb:] Découvrez comment étendre un schéma existant dans [cette section](extend-schema.md).

[!DNL :arrow_upper_right:] Découvrez des exemples d’extensions de table de destinataires intégrée dans la documentation de  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=fr#extending-a-table)

Vous pouvez également utiliser une autre table des destinataires, mieux adaptée à vos besoins professionnels ou fonctionnels. Cette méthode s’accompagne de limitations et est décrite dans [cette section](custom-recipient.md).

## Base de données cloud et tables Campaign

Pour une meilleure compréhension de la gestion des tables dans Campaign v8, notez que celles-ci sont répliquées entre Campaign et sa base de données cloud Snowflake.

[!DNL :bulb:] Pour en savoir plus sur la stratégie et les mécanismes de réplication, consultez [cette section](../config/replication.md).

**Rubriques connexes**

[!DNL :bulb:] Découvrez comment importer des profils dans  [cette ](../start/import.md)
[!DNL :bulb:] sectionEn savoir plus sur les audiences Campaign dans  [cette section](../start/audiences.md)
