---
title: Migration de l’infrastructure d’envoi de Campaign vers Amazon Web Services (AWS)
description: Migration de l’infrastructure d’envoi de Campaign vers Amazon Web Services (AWS)
hide: true
hidefromtoc: true
source-git-commit: d0935df57d8a25fa023dd93e7923c2728d889577
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---


# Migration de l’infrastructure d’envoi de campagne vers Amazon Web Services (AWS) {#migrate-infra-to-aws}

## Qu’est-ce qui a changé ?{#aws-changes}

Dans le cadre de nos efforts continus pour fournir un service de diffusion d’emails de la plus haute qualité, l’infrastructure d’envoi d’emails de Campaign est déplacée des centres de données hébergés par Adobe vers Amazon Web Services (AWS).

Ce déplacement garantit une haute disponibilité, un débit optimal et la possibilité de s’adapter aux besoins de nos clients.

## Cela vous concerne-t-il ?{#aws-impact}

En tant que client v8, hébergé, hybride ou Managed Services Campaign v7, vous êtes impacté.

## Quand cette migration aura-t-elle lieu ?{#aws-timeline}

La migration des environnements de développement et d’évaluation aura lieu dans **Octobre 2023**.

La migration des environnements de production doit commencer dans **Janvier 2024**. Plus de détails seront fournis à l’approche de la date.

En tant que client Campaign, vous recevrez une notification supplémentaire au fur et à mesure que les vagues de migration seront planifiées. Les notifications seront envoyées au moins sept jours avant la migration.

## Quel est l&#39;impact ?{#aws-impact}

Cette action sera transparente pour les clients :

* L&#39;envoi d&#39;adresses IP et de la version de build de Campaign restera le même qu&#39;avant le déplacement.

* Pendant la fenêtre de migration, les instances Campaign ne pourront pas envoyer de courrier. Aucune autre fonction de Campaign ne sera affectée.

* Tout courrier en file d&#39;attente pour diffusion avant la fenêtre de maintenance doit être renvoyé.

>[!NOTE]
>
>Pour toute question concernant cette migration, contactez votre représentant Adobe ou contactez [Adobe de l’assistance clientèle](https://helpx.adobe.com/fr/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).
>


