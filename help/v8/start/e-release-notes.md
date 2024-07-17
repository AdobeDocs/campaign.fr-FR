---
title: Notes de mise à jour anticipées de Campaign v8
description: Version anticipée de Campaign v8
feature: Release Notes
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: 09b8ced170ff28b24713722e0a82852038053201
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 58%

---

# Notes de mise à jour anticipées {#e-new-release}

Cette page décrit les améliorations et correctifs inclus dans la prochaine version de Campaign .v8 **Les notes de mise à jour anticipées ci-dessous peuvent être modifiées sans préavis jusqu’à la date de publication.**. Les liens, les écrans et la documentation mise à jour sont publiés dans les [notes de mise à jour](release-notes.md), à la date de publication.

## Version 8.7.2 {#release-8-7-2}

_mercredi 30 juillet 2024_


>[!AVAILABILITY]
>
>Cette version est en **disponibilité limitée** (LA). Elle est limitée aux personnes effectuant la migration **depuis Adobe Campaign Standard vers Adobe Campaign v8** et ne peut pas être déployée dans un autre environnement.
>
>Si vous êtes un utilisateur ou une utilisatrice de Campaign Standard et que vous passez à Campaign v8, apprenez-en plus sur cette transition dans la [documentation sur l’interface d’utilisation d’Adobe Campaign Web v8](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/release-notes/acs-migration){target="_blank"}.

### Nouveautés {#new-8-7-2}

* **Nouveau connecteur d&#39;envoi de SMS** - Le connecteur d&#39;envoi de SMS a été modernisé et amélioré afin d&#39;activer les connexions SMPP en mode émetteur-récepteur, d&#39;activer les connexions SMPP persistantes et d&#39;assurer une meilleure compatibilité pour les environnements en transition depuis Adobe Campaign Standard. Un nouveau compte externe SMS est désormais disponible pour toutes les nouvelles implémentations SMS. L’implémentation existante est toujours prise en charge, mais il est recommandé de passer à ce nouveau connecteur moderne et étendu.

* **Notification push enrichie (GA)** - Vous pouvez désormais envoyer des notifications push enrichies. La notification push enrichie est une forme améliorée de notification mobile qui va au-delà des messages texte simples en incorporant des éléments multimédias tels que des images, des boutons interactifs ou d’autres contenus multimédias enrichis. Avec cette version, un ensemble de modèles pour les notifications push enrichies est désormais disponible pour vos applications iOS et Android. [En savoir plus](../send/rich-push.md).

* **Marque** - Les options de marque sont désormais disponibles pour tous les canaux, y compris les SMS et les courriers. [En savoir plus](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=fr){target="_blank"}

<!--
### Fixes {#fixes-8-7-2}

The following issues are fixed in this release:

NEO-76592, NEO-75400, NEO-77406, NEO-77674, NEO-77899, NEO-73989, NEO-76064, NEO-76039, NEO-76040, NEO-76845, NEO-76664, NEO-76682, NEO-76663, NEO-73602, NEO-72915, NEO-78134, NEO-77000, NEO-77002, NEO-76955, NEO-76864, NEO-76926, NEO-76495, NEO-77168, NEO-41058, NEO-75581, NEO-74647, NEO-74585, NEO-74586, NEO-74831, NEO-77319, NEO-78607.-->

## Version 8.6.3 {#release-8-6-3}

_mercredi 30 juillet 2024_


### Nouveautés {#new-8-6-3}

* **Notification push enrichie** - Vous pouvez désormais envoyer des notifications push enrichies. La notification push enrichie est une forme améliorée de notification mobile qui va au-delà des messages texte simples en incorporant des éléments multimédias tels que des images, des boutons interactifs ou d’autres contenus multimédias enrichis. Avec cette version, un ensemble de modèles pour les notifications push enrichies est désormais disponible pour vos applications iOS et Android. [En savoir plus](../send/rich-push.md).

* À compter de cette version, les informations d’identification du compte de service (JWT) étant abandonnées par Adobe, les intégrations sortantes de Campaign aux solutions et applications d’Adobe dépendent désormais des informations d’identification OAuth serveur à serveur. [En savoir plus](release-notes.md#change-8-7-1)


### Améliorations générales {#improvements-8-6-3}

* Pour accroître la sécurité de toutes les communications entre les applications, mTLS est désormais pris en charge pour les appels API externes.

<!--
### Fixes {#fixes-8-7-2}

The following issues are fixed in this release:
-->