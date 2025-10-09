---
title: Notes de mise à jour de Campaign v8
description: Dernière version de Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 3bc247ba81de3de56c26bdf8fa9b8aa5ea91fb2a
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 24%

---

# Dernières versions {#latest-release}

Cette page répertorie les nouvelles fonctionnalités, les améliorations et les correctifs des **dernières versions** de Campaign v8 (console). Pour en savoir plus sur les publications, les versions et les mises à jour de Campaign, consultez [cette page](upgrades.md). Les autres versions sont répertoriées dans la section Versions précédentes de cette documentation.

## Version 8.8.2 {#release-8-8-2}

_9 octobre 2025_

>[!AVAILABILITY]
>
>Cette version est en **disponibilité limitée** (LA).

### Nouvelles fonctionnalités {#features-8-8-2}

Le **nouveau connecteur d’envoi de SMS** est désormais disponible pour les [déploiements Campaign FFDA](../architecture/enterprise-deployment.md). Consultez la [documentation détaillée](../send/sms/sms.md).

Cette version comprend également un ensemble de fonctionnalités disponibles dans l’interface utilisateur web de Campaign :

* [Enrichissement du profil dans les messages transactionnels](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html){target="_blank"}
* [Fonctionnalités multilingues pour les messages transactionnels, les notifications push et les SMS](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html){target="_blank"}

Reportez-vous aux notes de mise à jour de l’interface utilisateur web de Campaign [&#128279;](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=fr){target="_blank"}

### Correctifs {#fixes-8-8-2}

<!--
* Fixed an issue which prevented dynamic reporting from being available for transactional messages.
-->
* Correction d’un problème qui entraînait l’échec du workflow de nettoyage de la base de données. (NEO-87949)
* Correction d&#39;un problème dans le marketing distribué en raison duquel les données de tracking n&#39;étaient pas enregistrées pour les diffusions de campagnes collaboratives. (NEO-86836)
<!--
* Issue SMS2.0 with FFDA Continuous Deliveries (NEO-88785)
-->
* Correction d’un problème qui empêchait le bon fonctionnement de la personnalisation dans les fragments. (NEO-88161)
* Correction d’un problème, après la migration vers le nouveau connecteur ODBC Redshift, qui entraînait l’échec de l’activité de workflow Partage avec des erreurs SQL. (NEO-87466)
* Correction d’un problème qui entraînait des nombres d’exclusions inexacts dans les workflows. (NEO-89207)
* Correction d&#39;un problème qui entraînait des indicateurs de clic inexacts pour les notifications push. (NEO-89503)
* Correction d’un problème en raison duquel les logs de diffusion SMS n’étaient pas correctement mis à jour, empêchant la création de rapports d’état précis dans Adobe Campaign. (NEO-88479)
* Correction d’un problème en raison duquel les devis français étaient incorrectement convertis en devis anglais dans le contenu de la diffusion. (NEO-89631)
* Correction d’un problème en raison duquel le serveur en temps réel renvoyait un code de réponse incorrect pour les jetons IMS non valides. (NEO-87428)
* Correction d’un problème en raison duquel les statistiques de diffusion pour les e-mails et les SMS n’étaient pas entièrement recalculées, entraînant des indicateurs de succès inexacts. (NEO-88106)
* Correction d’un problème lié au nouveau connecteur d’envoi SMS en raison duquel les logs de diffusion attribuaient incorrectement le statut de diffusion pour un petit sous-ensemble de messages. (NEO-89581)
* Correction d’un problème lié au nouveau connecteur d’envoi SMS en raison duquel les mesures de succès sur les diffusions T-Mobile n’étaient pas correctement mises à jour sur les serveurs marketing et de mid-sourcing. (NEO-89850)
* Correction d’un problème de synchronisation entre les instances Real-Time et Marketing qui entraînait l’absence de logs de tracking et des rapports incorrects. (NEO-90247)
* Correction d’un problème d’enrichissement du workflow qui entraînait des erreurs lors de la sélection de champs sur deux liens 1-N consécutifs dans les schémas personnalisés. (NEO-87682)

