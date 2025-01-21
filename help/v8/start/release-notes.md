---
title: Notes de mise à jour de Campaign v8
description: Dernière version de Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 4a4bcb0b540d6e8a426839e77bf81ad30eb93653
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 51%

---

# Dernières versions {#latest-release}

Cette page répertorie les nouvelles fonctionnalités, les améliorations et les correctifs de Campaign v8 (console) **dernières versions**. Pour en savoir plus sur les versions et mises à niveau de Campaign, consultez [cette page](upgrades.md). Les autres versions sont répertoriées dans la section Versions précédentes de cette documentation.

## Version 8.6.4 {#release-8-6-4}

_15 janvier 2025_

### Améliorations générales {#improvements-8-6-4}

* La stabilité de l’application Campaign a été améliorée lors de l’analyse de la diffusion dans le contexte d’un déploiement [ Entreprise (FFDA)](../../v8/architecture/enterprise-deployment.md).
* Cette version s’accompagne de mécanismes d’architecture FFDA améliorés et renforcés, notamment la gestion des clés, l’évaluation et la réplication des données.
* De nouveaux workflows techniques ont été introduits pour le déploiement [ Entreprise (FFDA)](../../v8/architecture/enterprise-deployment.md). Ces workflows répliquent la diffusion et les données associées en centralisant les demandes de réplication parallèles sur les tables correspondantes. Ces workflows commencent par `Replicate nms`. [En savoir plus](../architecture/replication.md)
* Une nouvelle option **Activer le superviseur de chien de garde pour maintenir le workflow en cours d’exécution de manière permanente** est désormais disponible dans les propriétés du workflow. Lorsque cette option est activée, les workflows redémarrent automatiquement après une erreur. Par défaut, le redémarrage se produit toutes les 30 secondes si le workflow rencontre toujours une erreur. Pour ajuster cet intervalle, vous pouvez créer une nouvelle option `XtkWorkflow_WatchdogTimerTimeout` et définir un type de données Entier pour spécifier le nouveau délai. Cette option ne doit être activée que dans les workflows techniques. [En savoir plus](../../automation/workflow/workflow-properties.md#execution)

### Amélioration de la sécurité {#security-8-6-4}

La connexion aux solutions et applications Adobe via le compte externe **[!UICONTROL Adobe Experience Cloud]** a été mise à jour pour renforcer la sécurité.

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### Mises à jour de compatibilité {#comp-8-6-4}

Databricks est désormais pris en charge en tant que base de données externe avec Adobe Campaign Federated Data Access (FDA). En savoir plus [sur cette page](compatibility-matrix.md#FederatedDataAccessFDA).

### Correctifs {#fixes-8-6-4}

Les problèmes suivants ont été corrigés dans cette version :

NEO-48232, NEO-67814, NEO-71388, NEO-74855, NEO-75643, NEO-75962, NEO-76132, NEO-76958, NEO-76986, NEO-77162, NEO-77452, NEO-78946, NEO-79373, NEO-80243, NEO-80314, NEO-81127, NEO-81209, NEO-81223, NEO-81287, NEO-81290, NEO-81312, NEO-81512, NEO-81520 NEO-81566, NEO-81704, NEO-81908, NEO-82195, NEO-82591, NEO-82592 82640 82665 82781 82920 83081 83096 83137 83143.

## Version 8.7.2 {#release-8-7-2}

_3 septembre 2024_

>[!AVAILABILITY]
>
>Cette version est en **disponibilité limitée** (LA). Elle est limitée aux personnes effectuant la migration **depuis Adobe Campaign Standard vers Adobe Campaign v8** et ne peut pas être déployée dans un autre environnement.
>
>Si vous êtes un utilisateur ou une utilisatrice de Campaign Standard et que vous passez à Campaign v8, apprenez-en plus sur cette transition dans la [documentation sur l’interface d’utilisation d’Adobe Campaign Web v8](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nouvelles fonctionnalités {#new-8-7-2}

* **Nouveau connecteur d’envoi de SMS** : le connecteur d’envoi de SMS a été modernisé et amélioré afin d’activer les connexions SMPP en mode émetteur-récepteur, d’activer les connexions SMPP persistantes et d’assurer une meilleure compatibilité pour les environnements en transition depuis Adobe Campaign Standard. Un nouveau compte externe SMS est désormais disponible pour toutes les nouvelles implémentations SMS. L’implémentation existante est toujours prise en charge, mais il est recommandé de passer au nouveau connecteur moderne et étendu. [En savoir plus](../send/sms/sms.md).

* **Modèles de notification push enrichis (disponibilité générale)** : vous pouvez désormais envoyer des notifications push enrichies via Android. La notification push enrichie est une forme améliorée de notification mobile qui va au-delà des messages texte simples en incorporant des éléments multimédias tels que des images, des boutons interactifs ou d’autres contenus multimédias enrichis. Avec cette version, un ensemble de modèles pour les notifications push enrichies est désormais disponible pour vos applications iOS et Android. [En savoir plus](../send/rich-push-android.md).

* **Branding** : les options de branding sont désormais disponibles pour tous les canaux, y compris les SMS et les courriers. [En savoir plus](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=fr){target="_blank"}

### Correctifs {#fixes-8-7-2}

Les problèmes suivants ont été corrigés dans cette version :

NEO-48232, NEO-56832, NEO-72504, NEO-74855, NEO-75898, NEO-76097, NEO-76958, NEO-77014, NEO-77795, NEO-78843, NEO-79328.