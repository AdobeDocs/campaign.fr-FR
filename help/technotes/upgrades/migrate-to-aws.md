---
title: Migration de l’infrastructure d’envoi de Campaign vers Amazon Web Services (AWS)
description: Migration de l’infrastructure d’envoi de Campaign vers Amazon Web Services (AWS)
hide: true
hidefromtoc: true
source-git-commit: 15beb6e4aae7a00b245277bcb4c6c60c13b22884
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 20%

---


# Migration de l’infrastructure d’envoi de campagne vers Amazon Web Services (AWS) {#migrate-infra-to-aws}

## Qu’est-ce qui a changé ?{#aws-changes}

Dans le cadre de nos efforts continus pour fournir un service de diffusion d’emails de la plus haute qualité, l’infrastructure d’envoi d’emails de Campaign est déplacée des centres de données hébergés par Adobe vers Amazon Web Services (AWS).

Ce déplacement garantit une haute disponibilité, un débit optimal et la possibilité de s’adapter aux besoins de nos clients.

## Cela vous concerne-t-il ?{#aws-impact}

Cette modification affecte :

* Clients hébergés et hybrides Campaign Classic v7
* Clients Campaign Managed Services
* Tous les clients de Campaign v8
* Clients Campaign Standards

## Quand cette migration aura-t-elle lieu ?{#aws-timeline}

La migration des environnements de développement et d’évaluation aura lieu dans **Octobre 2023**.

La migration des environnements de production doit commencer dans **Janvier 2024**. Plus de détails seront fournis à l’approche de la date.

En tant que client Campaign, vous recevrez une notification supplémentaire au fur et à mesure que les vagues de migration seront planifiées. Les notifications seront envoyées au moins 7 jours avant la migration pour les environnements intermédiaires et au moins 30 jours avant la migration pour les environnements de production.

## Quel est l&#39;impact ?{#impact}

Cette action sera transparente pour les clients :

* La migration doit durer entre 30 min et 60 min.

* Les instances Campaign ne pourront pas envoyer de courrier pendant la fenêtre de migration. Aucune autre fonction de Campaign ne sera affectée.


## Forum aux questions {#aws-faq}

* **Pourquoi cette mise à niveau est-elle obligatoire ?**

  Adobe prévoit de désactiver l’ancien centre de données, les instances Adobe Campaign s’y exécutant doivent être transférées vers le nouveau centre de données de référence, Amazon Web Services (AWS).

  Le cloud Adobe Managed Services est hébergé sur Amazon Web Services (AWS), un environnement moderne, sécurisé et optimisé. [En savoir plus sur Amazon Web Services](https://aws.amazon.com/application-hosting/benefits/){target="_blank"}.

* **Quels sont les clients ciblés par cette migration ?**

  Tous les clients Campaign v8 et Campaign Classic v7 hybrides, hébergés et Campaign Managed Services auront leurs environnements migrés. Les clients Campaign Standards sont également affectés.

* **Quel est le temps d’arrêt prévu ?**

  Le temps d’arrêt attendu est compris entre 30 et 60 minutes.

* **Existe-t-il des actions requises par le client pour la migration ?**

  Aucune action n’est requise, car la migration sera exécutée automatiquement par Adobe.

* **Le client doit-il effectuer des validations ?**

  Aucun test spécifique n’est nécessaire pour cette migration. Si un problème est observé, veuillez contacter [Adobe de l’assistance clientèle](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.


* **Puis-je demander un changement de date/heure du créneau prévu pour la mise à niveau de sécurité ?**

  Comme il s&#39;agit d&#39;une migration obligatoire, il est vivement recommandé de s&#39;adapter au planning existant.


Pour toute autre question, contactez l’[Assistance clientèle d’Adobe](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.
