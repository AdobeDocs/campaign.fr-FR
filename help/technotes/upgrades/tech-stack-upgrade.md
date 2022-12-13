---
product: campaign
title: Note technique - mises à niveau du système Adobe Campaign
description: Mise à niveau du système Adobe Campaign
hide: true
hidefromtoc: true
exl-id: 78949d94-60b3-44f1-8e5a-d61b5b723e87
source-git-commit: 3535e1e4fcd326412b6378253e5dde1249bce1f2
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 40%

---

# Mises à niveau de l’environnement Adobe Campaign 2023 {#ac-system-upgrade}

L’infrastructure de Campaign repose sur des systèmes tiers qui doivent être régulièrement mis à jour avec les versions et les correctifs les plus récents. Ces mises à jour sont obligatoires pour assurer la continuité du service et sécuriser les environnements Campaign contre les risques de sécurité. En outre, une mise à niveau de Campaign est nécessaire pour garantir la compatibilité avec les modifications des systèmes tiers.

Comme **Client Cloud Services géré**, Adobe vous informe sur ces mises à niveau lorsqu’elles sont nécessaires. Vos environnements devront être mis à niveau conformément aux recommandations pour garantir la conformité.

Pour des raisons de sécurité, l’Adobe doit [installer le dernier build de Campaign](#ac-upgrade), puis mettez à niveau votre [système d&#39;exploitation](#os-upgrade) et/ou votre [Système de gestion de la base de données des relations (SGBD)](#pg-upgrade).

>[!NOTE]
>
>Pour toute question sur ces modifications, contactez l&#39;[Assistance clientèle d&#39;Adobe](https://helpx.adobe.com/fr/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).

## Mise à niveau de la version de Campaign {#ac-upgrade}

**Cela vous concerne-t-il ?**

Si vous êtes affecté par la variable [mise à niveau du système d’exploitation](#os-upgrade) et/ou [mise à niveau du système de base de données](#pg-upgrade) présenté ci-dessous, Adobe doit mettre à niveau vos environnements Campaign vers [la dernière version 8.4.3](../../v8/start/release-notes.md), qui est compatible avec ces systèmes.

**Comment effectuer la mise à jour ?**

En tant que client Cloud Services géré, Adobe vous contactera et mettra à niveau votre version de Campaign.

## Mise à niveau du système d’exploitation {#os-upgrade}

**Cela vous concerne-t-il ?**

Si vous exécutez Campaign sur un système d&#39;exploitation Debian, pour bénéficier des dernières mises à jour de sécurité de Debian, Adobe doit déplacer votre infrastructure Campaign vers **Debian 11**. Notez que la prise en charge en matière de sécurité de Debian 9 sera disponible jusqu’au 30 juin 2023.

**Comment effectuer la mise à jour ?**

En tant que client Cloud Services géré, Adobe vous contactera et mettra à niveau votre environnement.

## Mise à niveau du système de la base de données {#pg-upgrade}

**Cela vous concerne-t-il ?**

Si votre système de base de données pour Campaign est PostgreSQL, pour bénéficier des dernières innovations de PostgreSQL et des mises à jour de sécurité, Adobe doit effectuer la mise à niveau vers **PostgreSQL 14**. Notez que PostgreSQL 11 atteindra sa fin de vie le 9 novembre 2023.

**Comment effectuer la mise à jour ?**

* En tant que client Cloud Services géré, Adobe vous contactera et mettra à niveau votre système de base de données de PostgreSQL 11 vers PostgreSQL 14.
