---
title: Notes de mise à jour de Campaign v8 (console) 2025
description: Liste des fonctionnalités et améliorations des versions 2025 de Campaign v8
feature: Release Notes
exl-id: 3f91d83e-594e-49ee-a898-606e3de00bf3
source-git-commit: b52308bcbe68a7c382918fe28f8166e3bfcb6cde
workflow-type: tm+mt
source-wordcount: '936'
ht-degree: 96%

---

# Notes de mise à jour 2025 {#2025-rn}

Cette page répertorie les nouvelles fonctionnalités, les améliorations et les correctifs des **versions 2025 de Campaign v8**. Pour connaître la version la plus récente, consultez [cette page](release-notes.md).

Pour toute nouvelle implémentation ou mise à niveau vers un environnement existant, installez [la dernière version](release-notes.md).

>[!BEGINSHADEBOX]

**Dans cette page**

* [Version 8.6.5](#release-8-6-5)
* [Version 8.6.4](#release-8-6-4)
* [Version 8.7.4](#release-8-7-4)
* [Version 8.7.3](#release-8-7-3)


>[!ENDSHADEBOX]

## Version 8.6.5 {#release-8-6-5}

_25 avril 2025_

>[!AVAILABILITY]
>
>Cette version est en **disponibilité limitée** (LA).

### Nouvelles fonctionnalités {#features-8-6-5}

**Nouveau connecteur d’envoi de SMS** : le connecteur d’envoi de SMS a été modernisé et amélioré afin d’activer les connexions SMPP en mode émetteur-récepteur, d’activer les connexions SMPP persistantes et d’assurer une meilleure compatibilité pour les environnements en transition depuis Adobe Campaign Standard. Un nouveau compte externe SMS est désormais disponible pour toutes les nouvelles implémentations SMS. L’implémentation existante est toujours prise en charge, mais il est recommandé de passer au nouveau connecteur moderne et étendu. [En savoir plus](../send/sms/sms.md).

### Améliorations générales {#improvements-8-6-5}

* Les performances de l’application ont été améliorées, dans le contexte d’un déploiement Grands comptes (FFDA), notamment l’envoi de BAT de diffusion et le nettoyage de la base de données.

* Pour accroître la sécurité de toutes les communications entre les applications, mTLS est désormais pris en charge pour les appels API externes.

* MTA (Mail Transfer Agent) : correction du blocage d’un enfant MTA orphelin au statut **[!UICONTROL Démarrage en attente]**.

### Correctifs {#fixes-8-6-5}

Les problèmes suivants ont également été corrigés dans cette version :

NEO-67620, NEO-71534, NEO-80245, NEO-81105, NEO-81758, NEO-81908, NEO-82351, NEO-82742, NEO-83044, NEO-83138, NEO-83350, NEO-83729, NEO-83793, NEO-83809, NEO-84038, NEO-84108, NEO-85269, NEO-86121, NEO-86556, NEO-86739

## Version 8.7.4 {#release-8-7-4}

_10 avril 2025_

>[!AVAILABILITY]
>
>Cette version est en **disponibilité limitée** (LA). Elle est limitée aux personnes effectuant la migration **depuis Adobe Campaign Standard vers Adobe Campaign v8** et ne peut pas être déployée dans un autre environnement.
>
>Si vous êtes un utilisateur ou une utilisatrice de Campaign Standard et que vous passez à Campaign v8, apprenez-en plus sur cette transition dans la [documentation sur l’interface d’utilisation d’Adobe Campaign Web v8](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nouvelles fonctionnalités {#features-8-7-4}

* **Prise en charge de l’API REST SMS** : l’API REST de messagerie transactionnelle est désormais disponible pour le canal SMS. Lorsque le payload contient à la fois un e-mail et un téléphone mobile, vous pouvez utiliser le champ « wishedChannel » pour spécifier le canal. S’il n’est pas fourni, l’e-mail est utilisé par défaut, sauf si wishedChannel demande explicitement un SMS.

* **Diffusions multilingues** : à compter de la version d’avril de l’interface d’utilisation de Campaign Web, vous pourrez envoyer plusieurs diffusions par e-mail dans différentes langues et accéder aux rapports dynamiques associés. Cette fonctionnalité ne sera disponible dans l’interface d’utilisation d’Adobe Campaign Web qu’à la fin du mois d’avril et nécessite une mise à jour du serveur vers la version 8.7.4 de Campaign.

### Correctifs {#fixes-8-7-4}

Les problèmes suivants ont été corrigés dans cette version :

NEO-80245, NEO-83559

## Version 8.7.3 {#release-8-7-3}

_14 février 2025_

>[!AVAILABILITY]
>
>Cette version est en **disponibilité limitée** (LA). Elle est limitée aux personnes effectuant la migration **depuis Adobe Campaign Standard vers Adobe Campaign v8** et ne peut pas être déployée dans un autre environnement.
>
>Si vous êtes un utilisateur ou une utilisatrice de Campaign Standard et que vous passez à Campaign v8, apprenez-en plus sur cette transition dans la [documentation sur l’interface d’utilisation d’Adobe Campaign Web v8](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nouvelles fonctionnalités {#features-8-7-3}

* **Rapports dynamiques pour les messages transactionnels** : vous pouvez désormais surveiller vos messages transactionnels dans l’interface d’utilisation des rapports dynamiques. Ces rapports permettent aux professionnelles et professionnels du marketing de visualiser toutes les mesures et dimensions de rapports des messages transactionnels, ainsi que la répartition des diffusions envoyées via un modèle en temps réel. [En savoir plus](https://experienceleague.adobe.com/docs/campaign-web/v8/reports/dynamic-reporting/get-started-reporting.html?lang=fr){target="_blank"}

* **API REST de messagerie transactionnelle** : les API transactionnelles basées sur un événement sont désormais disponibles pour les e-mails. [En savoir plus](../dev/api/get-started-apis.md)

### Correctifs {#fixes-8-7-3}

Les problèmes suivants ont été corrigés dans cette version :

NEO-79373, NEO-81908, NEO-83081

## Version 8.6.4 {#release-8-6-4}

_15 janvier 2025_

### Améliorations générales {#improvements-8-6-4}

* La stabilité de l’application Campaign a été améliorée lors de l’analyse de la diffusion dans le contexte d’un [déploiement Grands comptes (FFDA)](../../v8/architecture/enterprise-deployment.md).
* Cette version s’accompagne de mécanismes d’architecture FFDA améliorés et renforcés, notamment la gestion des clés, l’évaluation et la réplication de données.
* De nouveaux workflows techniques ont été introduits pour le [déploiement Grands comptes (FFDA)](../../v8/architecture/enterprise-deployment.md). Ces workflows répliquent la diffusion et les données associées en centralisant les demandes de réplication parallèles sur les tables correspondantes. Ces workflows commencent par `Replicate nms`. [En savoir plus](../architecture/replication.md)
* Une nouvelle option **Activer le superviseur de surveillance pour que le workflow continue à fonctionner en permanence** est désormais disponible dans les propriétés du workflow. Lorsque cette option est activée, les workflows redémarrent automatiquement après une erreur. Par défaut, le redémarrage se produit toutes les 30 secondes si le workflow rencontre toujours une erreur. Pour ajuster cet intervalle, vous pouvez créer une nouvelle option `XtkWorkflow_WatchdogRestartTimerTimeout` et définir un type de données Entier pour spécifier le nouveau délai. Cette option ne doit être activée que dans les workflows techniques. [En savoir plus](../../automation/workflow/workflow-properties.md#execution)

### Améliorations de la sécurité {#security-8-6-4}

La connexion aux solutions et applications Adobe par le biais du compte externe **[!UICONTROL Adobe Experience Cloud]** a été mise à jour pour renforcer la sécurité.

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### Mises à jour de compatibilité {#comp-8-6-4}

Les connecteurs FDA suivants ont été ajoutés. Consultez cette [page](compatibility-matrix.md#FederatedDataAccessFDA).

* Databricks est désormais pris en charge en tant que base de données externe avec Adobe Campaign Federated Data Access (FDA).

* Un nouveau connecteur ODBC FDA Amazon Redshift est désormais disponible. Il offre une connectivité améliorée, une maintenance plus facile et une meilleure compatibilité. Cette nouvelle version apporte les améliorations suivantes :

   * Le nouveau connecteur repose sur l’interface ODBC qui s’aligne sur nos connecteurs FDA les plus récents. Cela garantit une prise en charge à long terme.
   * Il introduit également un nouveau mécanisme de chargement de données à l’aide de compartiments s3, ce qui améliore considérablement les performances.

  Le connecteur hérité peut toujours être utilisé. Si vous souhaitez tester la nouvelle version, contactez votre représentant ou représentante Adobe.

### Correctifs {#fixes-8-6-4}

Les problèmes suivants ont été corrigés dans cette version :

NEO-48232, NEO-67814, NEO-71388, NEO-74855, NEO-75643, NEO-75962, NEO-76132, NEO-76958, NEO-76986, NEO-77162, NEO-77452, NEO-78946, NEO-79373, NEO-80243, NEO-80314, NEO-81127, NEO-81209, NEO-81223, NEO-81287, NEO-81290, NEO-81312, NEO-81512, NEO-81520, NEO-81566, NEO-81704, NEO-81908, NEO-82195, NEO-82591, NEO-82592, NEO-82640, NEO-82665, NEO-82781, NEO-82920, NEO-83081, NEO-83096, NEO-83137, NEO-83143.

