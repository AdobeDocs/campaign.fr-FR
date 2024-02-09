---
title: Mise à niveau de l’infrastructure d’envoi d’e-mails dans Campaign
description: Mise à niveau de l’infrastructure d’envoi d’e-mails dans Campaign
exl-id: f01e38ad-490e-4389-af5e-87beef533eb0
source-git-commit: 68252db5ad53e2a37c76765cd35650f824101289
workflow-type: ht
source-wordcount: '331'
ht-degree: 100%

---

# Mise à niveau de l’infrastructure d’envoi d’e-mails dans Campaign {#migrate-infra-to-aws}

## Quels éléments seront mis à niveau ?{#aws-changes}

Dans le cadre de nos efforts constants pour offrir une expérience client de qualité optimale, nous mettons à niveau notre service de diffusion par e-mail.

## Cela vous concerne-t-il ?{#aws-impact}

Cette modification affecte :

* Les clientes et clients d’Adobe Campaign Classic Managed Services
* Les clientes et clients d’Adobe Campaign Managed Cloud Services
* Les clientes et clients d’Adobe Campaign Standard On-demand

## Quand cette mise à niveau aura-t-elle lieu ?{#aws-timeline}

Les mises à niveau des environnements de développement et d’évaluation ont commencé en **octobre 2023**.

Les mises à niveau des environnements de production ont commencé en **janvier 2024**.

## À quoi s’attendre ?{#impact}

* La durée de chaque vague de mise à niveau varie en fonction du nombre d’instances Campaign impactées. Lorsqu’une vague de mise à niveau d’environnement de production est planifiée, la notification inclut la durée prévue.

* Les instances de Campaign, que ce soit pour les environnements d’évaluation ou les environnements de production, ne pourront pas envoyer d’e-mails pendant la durée de la mise à niveau. Les autres fonctionnalités de Campaign ne devraient pas être affectées.

## Forum aux questions {#aws-faq}

* **Cette mise à niveau est-elle obligatoire ?**

  Oui. En tant que client ou cliente Campaign, votre fonctionnalité d’envoi d’e-mails nécessite l’utilisation d’une infrastructure appropriée.

* **Qui sont les clientes et clients ciblés par cette mise à niveau ?**

  Les environnements de l’ensemble des clientes et clients Campaign référencés ci-dessus seront mis à niveau.

* **Quel est le temps d’arrêt prévu ?**

  La durée de chaque vague de mise à niveau peut varier en fonction du nombre d’instances Campaign impactées. Lorsqu’une vague de mise à niveau d’environnement de production est planifiée, la notification inclut la durée prévue.

* **Les clientes et clients doivent-ils prendre des mesures pour cette mise à niveau ?**

  Aucune action n’est requise. Adobe gère le processus de mise à niveau, qui s’exécute automatiquement.

* **Quels sont les tests requis par les clientes et clients ?**

  Nous ne nous attendons pas à ce que les clientes et clients aient à effectuer des tests en rapport avec cet événement de mise à niveau. Contactez l’[Assistance clientèle d’Adobe](https://experienceleague.adobe.com/?support-solution=Campaign&amp;lang=fr#support) pour tout problème rencontré{target="_blank"}.


* **Puis-je demander un changement de date/heure du créneau prévu pour la mise à niveau de sécurité ?**

  Non. Nous ne pouvons pas prendre en charge les modifications demandées au planning existant, au risque de perturber l’événement de mise à niveau assigné à d’autres personnes.

Pour toute autre question, contactez l’[Assistance clientèle d’Adobe](https://experienceleague.adobe.com/?support-solution=Campaign&amp;lang=fr#support){target="_blank"}.
