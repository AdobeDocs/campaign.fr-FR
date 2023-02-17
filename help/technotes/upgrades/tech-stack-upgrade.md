---
product: campaign
title: Note technique - mises à niveau du système Adobe Campaign
description: Mise à niveau du système Adobe Campaign
hide: true
hidefromtoc: true
exl-id: 78949d94-60b3-44f1-8e5a-d61b5b723e87
source-git-commit: f1e963a880e8499dbbb16c44831a4ce1b537601f
workflow-type: ht
source-wordcount: '310'
ht-degree: 100%

---

# Mises à niveau de l’environnement Adobe Campaign 2023 {#ac-system-upgrade}

L’infrastructure de Campaign repose sur des systèmes tiers qui doivent être régulièrement mis à jour avec les versions et les correctifs les plus récents. Ces mises à jour sont obligatoires pour assurer la continuité du service et sécuriser les environnements Campaign contre les risques de sécurité. En outre, une mise à niveau de Campaign est nécessaire pour garantir la compatibilité avec les modifications des systèmes tiers.

Vous êtes **client(e) Managed Cloud Services** et Adobe vous informe de ces mises à niveau lorsqu’elles sont nécessaires. Vos environnements devront être mis à niveau conformément aux recommandations pour garantir leur conformité.

Pour des raisons de sécurité, Adobe doit [installer la version la plus récente de Campaign](#ac-upgrade), puis mettre à niveau votre [système d’exploitation](#os-upgrade) et/ou votre [système de gestion de la base de données relationnelle (SGBD)](#pg-upgrade).

>[!NOTE]
>
>Pour toute question sur ces modifications, contactez l’[Assistance clientèle d’Adobe](https://helpx.adobe.com/fr/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).

## Mise à niveau de la version de Campaign {#ac-upgrade}

**Cela vous concerne-t-il ?**

Si vous êtes affecté(e) par la [mise à niveau du système d’exploitation](#os-upgrade) et/ou la [mise à niveau du système de la base de données](#pg-upgrade) présentées ci-dessous, vous devez mettre à niveau vos environnements Campaign vers [la dernière version 8.4.3](../../v8/start/release-notes.md), compatible avec ces systèmes.

**Comment effectuer la mise à jour ?**

Vous êtes client(e) Managed Cloud Services et Adobe vous contactera et mettra à niveau votre version de Campaign.

## Mise à niveau du système d’exploitation {#os-upgrade}

**Cela vous concerne-t-il ?**

Si vous exécutez Campaign sur un système d’exploitation Debian, vous devez déplacer votre infrastructure Campaign vers **Debian 11** pour bénéficier des dernières mises à jour de sécurité de Debian. Notez que la prise en charge en matière de sécurité de Debian 9 sera disponible jusqu’au 30 juin 2023.

**Comment effectuer la mise à jour ?**

Vous êtes client(e) Managed Cloud Services : Adobe vous contactera et mettra à niveau votre environnement.

## Mise à niveau du système de la base de données {#pg-upgrade}

**Cela vous concerne-t-il ?**

Si votre système de base de données pour Campaign est PostgreSQL, Adobe doit effectuer la mise à niveau vers **PostgreSQL 14** pour bénéficier des dernières innovations et mises à jour de sécurité de PostgreSQL. Notez que PostgreSQL 11 atteindra sa fin de vie le 9 novembre 2023.

**Comment effectuer la mise à jour ?**

Vous êtes client(e) Managed Cloud Services : Adobe vous contactera et mettra à niveau votre système de base de données de PostgreSQL 11 vers PostgreSQL 14.
