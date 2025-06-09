---
title: Migrer l’infrastructure d’envoi de Campaign vers Amazon Web Services (AWS)
description: Migrer l’infrastructure d’envoi de Campaign vers Amazon Web Services (AWS)
hide: true
hidefromtoc: true
exl-id: 50279a2f-0296-43f5-8967-16cc6a0c88f6
source-git-commit: 3e95a56825a143a4457ab7ee242208d7daaeb414
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 98%

---

# Migration de l’infrastructure d’envoi de Campaign vers Amazon Web Services (AWS) {#migrate-infra-to-aws}

## Qu’est-ce qui a changé ?{#aws-changes}

Dans le cadre de nos efforts continus pour fournir un service de diffusion d’e-mails de la plus haute qualité, l’infrastructure d’envoi d’e-mails de Campaign est déplacée des centres de données hébergés par Adobe vers Amazon Web Services (AWS).

Ce déplacement garantit une haute disponibilité, un débit optimal et la possibilité de s’adapter aux besoins de nos clientes et clients.

## Cela vous concerne-t-il ?{#aws-impact}

Cette modification affecte :

* Les clientes et clients hébergés et hybrides de Campaign Classic v7
* Les clientes et clients de Campaign Managed Services
* L’ensemble des clientes et clients de Campaign v8
* Clientes et clients Campaign Standard

## Quand cette migration aura-t-elle lieu ?{#aws-timeline}

La migration des environnements de développement et d’évaluation aura lieu en **octobre 2023**.

La migration des environnements de production doit commencer en **janvier 2024**. Plus de détails seront fournis à l’approche de ces dates.

En tant que client ou cliente Campaign, vous recevrez des notifications supplémentaires au fur et à mesure que les vagues de migration seront planifiées. Les notifications seront envoyées au moins 7 jours avant la migration pour les environnements d’évaluation et au moins 30 jours avant la migration pour les environnements de production.

## Quel est l’impact ?{#impact}

Cette action sera transparente :

* La longueur de chaque vague de migration peut varier en fonction du nombre d’instances Campaign impactées. Lorsqu’une vague de migration est planifiée, la notification inclut la durée prévue.

* Les instances Campaign ne pourront pas envoyer d’e-mail pendant la durée de la migration. Aucune autre fonction de Campaign ne sera affectée.


## Forum aux questions {#aws-faq}

* **Pourquoi cette mise à niveau est-elle obligatoire ?**

  Adobe prévoit de mettre hors service l’ancien centre de données. Les instances d’Adobe Campaign qui y sont exécutées doivent être transférées vers Amazon Web Services (AWS), le nouveau centre de données de référence.

  Le cloud Adobe Managed Services est hébergé sur Amazon Web Services (AWS), un environnement moderne, sécurisé et optimisé. [En savoir plus sur Amazon Web Services](https://aws.amazon.com/application-hosting/benefits/){target="_blank"}.

* **Qui sont les clientes et clients ciblés par cette migration ?**

  L’ensemble des clientes et clients de Campaign v8 et Campaign Classic v7 hybrides et hébergés, ainsi que de Campaign Managed Services verront leurs environnements migrer. Les clientes et clients Campaign Standard sont également affectées.

* **Quel est le temps d’arrêt prévu ?**

  La migration doit durer entre 30 et 60 minutes, mais la longueur de chaque vague de migration peut varier en fonction du nombre d’instances Campaign impactées. Lorsqu’une vague de migration est planifiée, la notification inclut la durée prévue.

* **Les clientes et clients doivent-ils prendre des mesures pour cette migration ?**

  Aucune action n’est requise, car la migration sera exécutée automatiquement par Adobe.

* **Le client ou la cliente doit-il/elle effectuer des validations ?**

  Aucun test spécifique n’est nécessaire pour cette migration. Contactez l’[Assistance clientèle d’Adobe](https://experienceleague.adobe.com/fr?support-solution=Campaign&amp;lang=fr#support){target="_blank"} pour tout problème rencontré.


* **Puis-je demander un changement de date/heure du créneau prévu pour la mise à niveau de sécurité ?**

  Puisqu’il s’agit d’une migration obligatoire, nous ne pouvons pas prendre en charge les modifications apportées au planning existant.

Pour toute autre question, contactez l’[Assistance clientèle d’Adobe](https://experienceleague.adobe.com/fr?support-solution=Campaign&amp;lang=fr#support){target="_blank"}.
