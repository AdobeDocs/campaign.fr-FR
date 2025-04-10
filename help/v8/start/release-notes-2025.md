---
title: Notes de mise à jour de Campaign v8 (console) 2025
description: Liste des fonctionnalités et améliorations des versions 2025 de Campaign v8.
feature: Release Notes
exl-id: 3f91d83e-594e-49ee-a898-606e3de00bf3
source-git-commit: ff874a8e06303625b4c96f49fdf4f303b50fb908
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 68%

---

# Notes de mise à jour 2025 {#2025-rn}

Cette page répertorie les nouvelles fonctionnalités, les améliorations et les correctifs des versions **2025 de Campaign v8**. Les dernières versions sont répertoriées dans [cette page](release-notes.md).

## Version 8.7.3 {#release-8-7-3}

_14 février 2025_

>[!AVAILABILITY]
>
>Cette version est en **disponibilité limitée** (LA). Elle est limitée aux personnes effectuant la migration **depuis Adobe Campaign Standard vers Adobe Campaign v8** et ne peut pas être déployée dans un autre environnement.
>
>En tant qu’utilisateur Campaign Standard passant à Campaign v8, apprenez-en davantage sur cette transition dans la [documentation de l’interface utilisateur web de Campaign v8](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nouvelles fonctionnalités {#features-8-7-3}

* **Rapports dynamiques pour les messages transactionnels** - Vous pouvez désormais surveiller vos messages transactionnels dans l’interface utilisateur des rapports dynamiques. Ces rapports permettent au professionnel du marketing de visualiser toutes les mesures et dimensions de rapports des messages transactionnels, ainsi que la répartition des diffusions envoyées via un modèle en temps réel. [En savoir plus](https://experienceleague.adobe.com/fr/docs/experience-cloud/campaign/reporting/get-started-reporting){target="_blank"}

* **API REST de messagerie transactionnelle** - Les API transactionnelles basées sur un événement sont désormais disponibles pour les e-mails. [En savoir plus](https://experienceleague.adobe.com/en/docs/experience-cloud/campaign/apis/managing-transactional-messages){target="_blank"}

### Correctifs {#fixes-8-7-3}

Les problèmes suivants ont été corrigés dans cette version :

NEO-79373, NEO-81908, NEO-83081

## Version 8.7.2 {#release-8-7-2}

_3 septembre 2024_

>[!AVAILABILITY]
>
>Cette version est en **disponibilité limitée** (LA). Elle est limitée aux personnes effectuant la migration **depuis Adobe Campaign Standard vers Adobe Campaign v8** et ne peut pas être déployée dans un autre environnement.
>
>En tant qu’utilisateur Campaign Standard passant à Campaign v8, apprenez-en davantage sur cette transition dans la [documentation de l’interface utilisateur web de Campaign v8](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nouvelles fonctionnalités {#new-8-7-2}

* **Nouveau connecteur d’envoi de SMS** : le connecteur d’envoi de SMS a été modernisé et amélioré afin d’activer les connexions SMPP en mode émetteur-récepteur, d’activer les connexions SMPP persistantes et d’assurer une meilleure compatibilité pour les environnements en transition depuis Adobe Campaign Standard. Un nouveau compte externe SMS est désormais disponible pour toutes les nouvelles implémentations SMS. L’implémentation existante est toujours prise en charge, mais il est recommandé de passer au nouveau connecteur moderne et étendu. [En savoir plus](../send/sms/sms.md).

* **Modèles de notification push enrichis (disponibilité générale)** : vous pouvez désormais envoyer des notifications push enrichies via Android. La notification push enrichie est une forme améliorée de notification mobile qui va au-delà des messages texte simples en incorporant des éléments multimédias tels que des images, des boutons interactifs ou d’autres contenus multimédias enrichis. Avec cette version, un ensemble de modèles pour les notifications push enrichies est désormais disponible pour vos applications iOS et Android. [En savoir plus](../send/rich-push-android.md).

* **Branding** : les options de branding sont désormais disponibles pour tous les canaux, y compris les SMS et les courriers. [En savoir plus](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=fr){target="_blank"}

### Correctifs {#fixes-8-7-2}

Les problèmes suivants ont été corrigés dans cette version :

NEO-48232, NEO-56832, NEO-72504, NEO-74855, NEO-75898, NEO-76097, NEO-76958, NEO-77014, NEO-77795, NEO-78843, NEO-79328.
