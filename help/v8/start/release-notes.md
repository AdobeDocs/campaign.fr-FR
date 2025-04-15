---
title: Notes de mise à jour de Campaign v8
description: Dernière version de Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 66e4b59915eae595b28076622f7bcfb5b5a0ffa4
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 17%

---

# Dernières versions {#latest-release}

Cette page répertorie les nouvelles fonctionnalités, les améliorations et les correctifs de Campaign v8 (console) **dernières versions**. Pour en savoir plus sur les versions et mises à niveau de Campaign, consultez [cette page](upgrades.md). Les autres versions sont répertoriées dans la section Versions précédentes de cette documentation.

>[!BEGINSHADEBOX]

**Dans cette page**

* [Version 8.7.4](#release-8-7-4)
* [Version 8.6.4](#release-8-6-4)

>[!ENDSHADEBOX]

## Version 8.7.4 {#release-8-7-4}

_vendredi 10 avril 2025_

>[!AVAILABILITY]
>
>Cette version est en **disponibilité limitée** (LA). Elle est limitée aux personnes effectuant la migration **depuis Adobe Campaign Standard vers Adobe Campaign v8** et ne peut pas être déployée dans un autre environnement.
>
>En tant qu’utilisateur Campaign Standard passant à Campaign v8, apprenez-en davantage sur cette transition dans la [documentation de l’interface utilisateur web de Campaign v8](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nouvelles fonctionnalités {#features-8-7-4}

* **Prise en charge de l’API REST SMS** - L’API REST de messagerie transactionnelle est désormais disponible pour le canal SMS. Lorsque le payload contient à la fois un e-mail et un téléphone mobile, vous pouvez utiliser le champ « wishedChannel » pour spécifier le canal. S’il n’est pas fourni, l’e-mail est utilisé par défaut, sauf si wishedChannel demande explicitement un SMS.

* **Diffusions multilingues** - À compter de la version d’avril de l’interface utilisateur web de Campaign, vous pourrez envoyer plusieurs diffusions par e-mail dans différentes langues et accéder aux rapports dynamiques associés. Cette fonctionnalité ne sera disponible dans l’interface utilisateur web d’Adobe Campaign qu’à la fin du mois d’avril et nécessite une mise à jour du serveur vers la version 8.7.4 de Campaign.

### Correctifs {#fixes-8-7-4}

Les problèmes suivants ont été corrigés dans cette version :

NEO-80245, NEO-83559

## Version 8.6.4 {#release-8-6-4}

_15 janvier 2025_

### Améliorations générales {#improvements-8-6-4}

* La stabilité de l’application Campaign a été améliorée lors de l’analyse de la diffusion dans le contexte d’un déploiement [ Entreprise (FFDA)](../../v8/architecture/enterprise-deployment.md).
* Cette version s’accompagne de mécanismes d’architecture FFDA améliorés et renforcés, notamment la gestion des clés, l’évaluation et la réplication des données.
* De nouveaux workflows techniques ont été introduits pour le déploiement [ Entreprise (FFDA)](../../v8/architecture/enterprise-deployment.md). Ces workflows répliquent la diffusion et les données associées en centralisant les demandes de réplication parallèles sur les tables correspondantes. Ces workflows commencent par `Replicate nms`. [En savoir plus](../architecture/replication.md)
* Une nouvelle option **Activer le superviseur de chien de garde pour maintenir le workflow en cours d’exécution de manière permanente** est désormais disponible dans les propriétés du workflow. Lorsque cette option est activée, les workflows redémarrent automatiquement après une erreur. Par défaut, le redémarrage se produit toutes les 30 secondes si le workflow rencontre toujours une erreur. Pour ajuster cet intervalle, vous pouvez créer une nouvelle option `XtkWorkflow_WatchdogRestartTimerTimeout` et définir un type de données Entier pour spécifier le nouveau délai. Cette option ne doit être activée que dans les workflows techniques. [En savoir plus](../../automation/workflow/workflow-properties.md#execution)

### Améliorations de la sécurité {#security-8-6-4}

La connexion aux solutions et applications Adobe par le biais du compte externe **[!UICONTROL Adobe Experience Cloud]** a été mise à jour pour renforcer la sécurité.

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### Mises à jour de compatibilité {#comp-8-6-4}

Les connecteurs FDA suivants ont été ajoutés. Voir cette [page](compatibility-matrix.md#FederatedDataAccessFDA).

* Databricks est désormais pris en charge en tant que base de données externe avec Adobe Campaign Federated Data Access (FDA).

* Un nouveau connecteur ODBC FDA Amazon Redshift est désormais disponible. Elle offre une meilleure connectivité, une maintenance plus facile et une meilleure compatibilité. Cette nouvelle version apporte les améliorations suivantes :

   * Le nouveau connecteur repose sur l’interface ODBC qui s’aligne sur nos connecteurs FDA les plus récents. Cela garantit une prise en charge à long terme.
   * Il introduit également un nouveau mécanisme de chargement de données à l’aide d’intervalles s3, ce qui améliore considérablement les performances.

  Le connecteur hérité peut toujours être utilisé. Si vous souhaitez tester la nouvelle version, contactez votre représentant ou représentante Adobe.

### Correctifs {#fixes-8-6-4}

Les problèmes suivants ont été corrigés dans cette version :

NEO-48232, NEO-67814, NEO-71388, NEO-74855, NEO-75643, NEO-75962, NEO-76132, NEO-76958, NEO-76986, NEO-77162, NEO-77452, NEO-78946, NEO-79373, NEO-80243, NEO-80314, NEO-81127, NEO-81209, NEO-81223, NEO-81287, NEO-81290, NEO-81312, NEO-81512, NEO-81520 NEO-81566, NEO-81704, NEO-81908, NEO-82195, NEO-82591, NEO-82592 82640 82665 82781 82920 83081 83096 83137 83143.

