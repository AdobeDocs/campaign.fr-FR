---
title: Mise à niveau de l’infrastructure d’envoi de courriers électroniques de Campaign
description: Mise à niveau de l’infrastructure d’envoi de courriers électroniques de Campaign
hide: true
hidefromtoc: true
source-git-commit: 47fc1ee7e0a1cb96d66151cf79137c80ef2d67d5
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 17%

---


# Mise à niveau de l’infrastructure d’envoi de courriers électroniques de Campaign {#migrate-infra-to-aws}

## Que sera mis à niveau ?{#aws-changes}

Dans le cadre de nos efforts constants pour offrir une expérience utilisateur de qualité optimale, nous mettons à niveau notre service de diffusion par courrier électronique.

## Cela vous concerne-t-il ?{#aws-impact}

Cette modification affecte :

* Clients Adobe Campaign Classic Managed Services
* Clients Adobe Campaign Managed Cloud Services
* Clients à la demande Adobe Campaign Standard

## Quand cette mise à niveau aura-t-elle lieu ?{#aws-timeline}

Les mises à niveau des environnements de développement et d’évaluation sont attendues à l’adresse **Octobre 2023**.

Nous prévoyons de planifier les mises à niveau de l’environnement de production à partir de **Janvier 2024**.

En tant que client Campaign, vous recevrez au moins trente (30) jours à l&#39;avance une notification supplémentaire concernant l&#39;upgrade de production.

## À quoi s&#39;attendre ?{#impact}

* La longueur de chaque vague d&#39;upgrade varie en fonction du nombre d&#39;instances Campaign impactées. Lorsqu&#39;une vague d&#39;upgrade de production est planifiée, la notification inclut la durée estimée.

* Les instances de Campaign, dans les environnements intermédiaires et de production, ne pourront pas envoyer de courrier pendant la fenêtre de mise à niveau. Les autres fonctionnalités de Campaign ne devraient pas être affectées.

## Questions fréquentes {#aws-faq}

* **Cette mise à niveau est-elle obligatoire ?**

  Oui. En tant que client Campaign, votre fonctionnalité d’envoi d’emails nécessite l’utilisation d’une infrastructure d’envoi d’emails.

* **Quels sont les clients ciblés pour cette mise à niveau ?**

  Les environnements de tous les clients Campaign référencés ci-dessus seront mis à niveau.

* **Quel est le temps d’arrêt prévu ?**

  La longueur de chaque vague d&#39;upgrade peut varier en fonction du nombre d&#39;instances Campaign impactées. Lorsqu&#39;une vague d&#39;upgrade de production est programmée, la notification inclura une durée estimée.

* **Existe-t-il des actions requises par le client pour la mise à niveau ?**

  Aucune action n’est requise. Adobe gère le processus de mise à niveau, qui s’exécute automatiquement.

* **Quels tests sont requis par les clients ?**

  Nous ne nous attendons pas à ce que les clients effectuent des tests en rapport avec cet événement de mise à niveau. Contactez l’[Assistance clientèle d’Adobe](https://experienceleague.adobe.com/?support-solution=Campaign#support) pour tout problème rencontré{target="_blank"}.


* **Puis-je demander un changement de date/heure du créneau prévu pour la mise à niveau de sécurité ?**

  Non. Nous ne pouvons pas prendre en charge les modifications demandées au planning existant, car cela perturbera probablement l’événement de mise à niveau assigné à un autre client.

Pour toute autre question, contactez l’[Assistance clientèle d’Adobe](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.
