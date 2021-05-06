---
solution: Campaign Classic
product: campaign
title: 'Prise en main du modèle de données de Campaign '
description: 'Prise en main du modèle de données de Campaign '
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896,b1319b34-ee07-48ed-9ab1-e2d12d3d99f8
translation-type: tm+mt
source-git-commit: e509feb4624b26e33d43f2a1d926b563ab52a8c4
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 47%

---

# Prise en main du modèle de données de Campaign {#gs-ac-datamodel}

Un modèle de données d’usine est fourni avec Adobe Campaign. Cette section donne un certain nombre de détails sur les tables intégrées du modèle de données d’Adobe Campaign et leurs interactions. Adobe Campaign repose sur une base de données Cloud contenant des tables qui sont liées entre elles.

La structure de base du modèle de données Adobe Campaign peut être décrite comme suit:

* **Table** du destinataire : Le modèle de données repose sur une table principale qui est par défaut la table du Destinataire (nmsRecipient). Cette table permet de stocker tous les profils marketing.

   : bulb: Pour plus d’informations sur le tableau du Destinataire, voir [cette section](#ootb-profiles).

* **Table** de diffusions : Le modèle de données comprend également une partie dédiée au stockage de toutes les activités marketing. Généralement, il s&#39;agit de la table de diffusion (NmsDelivery). Chaque enregistrement de cette table représente une action de diffusion ou un modèle de diffusion. Elle contient tous les paramètres nécessaires pour effectuer des diffusions telles que la cible, le contenu, etc.

* **Journalise les tables** : Ces tableaux stockent tous les journaux associés à l’exécution des campagnes.

   Les logs de diffusion sont tous des messages envoyés aux destinataires ou aux appareils sur tous les canaux. Le tableau des logs de diffusion principale (NmsBroadLog) contient les logs de diffusion pour tous les destinataires.
La table principale des logs de tracking (NmsTrackingLog) stocke les logs de tracking pour tous les destinataires. Les logs de tracking se rapportent aux réactions des destinataires, telles que les ouvertures d’email et les clics. Chaque réaction correspond à un log de tracking.
Les mpgs de diffusion et de tracking sont supprimés après une certaine période, spécifiée dans Adobe Campaign et modifiable. Il est donc vivement recommandé d’exporter les logs de façon régulière.

* **Tableaux** techniques : Rassemblez les données techniques utilisées pour le processus d’application, y compris les opérateurs et les droits d’utilisateur (NmsGroup), les dossiers (XtkFolder).

>[!NOTE]
>
>Pour obtenir la description de chaque table, accédez à Admin > Paramétrage > Schémas de données, sélectionnez une ressource dans la liste et cliquez sur l’onglet **Documentation**.

Lorsque vous commencez à utiliser Adobe Campaign, vous devez évaluer le modèle de données par défaut pour déterminer quelle table est adaptée au stockage de vos données marketing.

Vous pouvez utiliser la table de Destinataires par défaut avec les champs prêts à l’emploi, comme décrit dans [cette section](#ootb-profiles). En cas de besoin, vous pouvez l’étendre avec deux mécanismes :

* [Étendez une table existante avec de nouveaux champs.](extend-schema.md) Par exemple, vous pouvez ajouter un nouveau champ &quot;Fidélité&quot; à la table du Destinataire.
* [Créez une table](create-schema.md), par exemple une table &quot;Achat&quot; répertoriant tous les achats effectués par chaque profil de la base de données et liez-la à la table du Destinataire.

: bulb: Découvrez les meilleures pratiques lors de l&#39;utilisation du modèle de données Campaign dans [cette section](datamodel-best-practices.md).

## Table de profil intégrée {#ootb-profiles}

La table de destinataires intégrée (nmsRecipient) dans Adobe Campaign constitue un bon point de départ pour la création de votre modèle de données. Elle comporte un certain nombre de champs prédéfinis et de liens vers des tables faciles à étendre. Son emploi est particulièrement efficace si vous ciblez principalement les destinataires, car elle s&#39;appuie sur un modèle de données centré sur ces derniers.

L’utilisation du tableau destinataire standard présente les avantages suivants :

* Utilisation prête à l&#39;emploi avec des fonctionnalités clés telles que les abonnements, les listes de base, etc.
* Disposer d&#39;une base de données marketing dotée d&#39;un modèle de données axé sur les destinataires
* Permettre une mise en œuvre plus rapide
* Faciliter les prestations de maintenance des intervenants chargés de l&#39;assistance et des partenaires

Il est possible d’étendre le tableau du destinataire, mais pas de réduire le nombre de champs ou de liens du tableau.

: bulb: Découvrez comment étendre un schéma existant dans [cette section](extend-schema.md).

:flèche_supérieur_droite : Découvrez des exemples d’extensions de table de destinataires intégrées dans [la documentation du Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#extending-a-table)

Vous pouvez également utiliser une autre table de destinataires pour mieux répondre à vos besoins professionnels ou fonctionnels. Cette méthode est fournie avec des limites et est décrite dans [cette section](custom-recipient.md).

## Tables Campaign et base de données Cloud

Pour une meilleure compréhension de la gestion des tables dans Campaign v8, notez que les tables sont répliquées entre Campaign et sa base de données Snowflake Cloud.

: bulb: Pour en savoir plus sur la stratégie et les mécanismes de réplication, consultez [cette section](../config/replication.md).

**Rubriques connexes :**

: bulb: Découvrez comment importer des profils dans [cette section](../start/import.md)
: bulb: Pour en savoir plus sur les audiences Campaign, voir [cette section](../start/audiences.md)
