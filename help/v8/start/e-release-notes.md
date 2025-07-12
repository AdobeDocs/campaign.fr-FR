---
title: Notes de mise à jour anticipées de Campaign v8
description: Version anticipée de Campaign v8
feature: Release Notes
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: 4ed5799c77c647c9f1aeabba7645fbb475d03c09
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 99%

---

# Notes de mise à jour anticipées {#e-new-release}

Cette page décrit les améliorations et correctifs inclus dans la prochaine version de Campaign .v8 **Les notes de mise à jour anticipées ci-dessous peuvent être modifiées sans préavis jusqu’à la date de publication.**. Les liens, les écrans et la documentation mise à jour sont publiés dans les [notes de mise à jour](release-notes.md), à la date de publication.


## Version 8.7.2 {#release-8-7-2}

_3 septembre 2024_

>[!AVAILABILITY]
>
>Cette version est en **disponibilité limitée** (LA). Elle est limitée aux personnes effectuant la migration **depuis Adobe Campaign Standard vers Adobe Campaign v8** et ne peut pas être déployée dans un autre environnement.
>
>Si vous êtes un utilisateur ou une utilisatrice de Campaign Standard et que vous passez à Campaign v8, apprenez-en plus sur cette transition dans la [documentation sur l’interface d’utilisation d’Adobe Campaign Web v8](https://experienceleague.adobe.com/docs/campaign-web/v8/start/acs-migration.html?lang=fr){target="_blank"}.

### Nouvelles fonctionnalités {#new-8-7-2}

* **Nouveau connecteur d’envoi de SMS** : le connecteur d’envoi de SMS a été modernisé et amélioré afin d’activer les connexions SMPP en mode émetteur-récepteur, d’activer les connexions SMPP persistantes et d’assurer une meilleure compatibilité pour les environnements en transition depuis Adobe Campaign Standard. Un nouveau compte externe SMS est désormais disponible pour toutes les nouvelles implémentations SMS. L’implémentation existante est toujours prise en charge, mais il est recommandé de passer au nouveau connecteur moderne et étendu.

* **Modèles de notification push enrichis (disponibilité générale)** : vous pouvez désormais envoyer des notifications push enrichies via Android. La notification push enrichie est une forme améliorée de notification mobile qui va au-delà des messages texte simples en incorporant des éléments multimédias tels que des images, des boutons interactifs ou d’autres contenus multimédias enrichis. Avec cette version, un ensemble de modèles pour les notifications push enrichies est désormais disponible pour vos applications iOS et Android. [En savoir plus](../send/rich-push-android.md).

* **Branding** : les options de branding sont désormais disponibles pour tous les canaux, y compris les SMS et les courriers. [En savoir plus](https://experienceleague.adobe.com/docs/campaign-web/v8/conf/branding/branding-gs.html?lang=fr){target="_blank"}


### Correctifs {#fixes-8-7-2}

Les problèmes suivants ont été corrigés dans cette version :

NEO-48232, NEO-56832, NEO-72504, NEO-74855, NEO-75898, NEO-76097, NEO-76958, NEO-77014, NEO-77795, NEO-78843, NEO-79328.
