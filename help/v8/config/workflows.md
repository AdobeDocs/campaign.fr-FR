---
solution: Campaign
product: Adobe Campaign
title: Prise en main de l’automatisation de campagne
description: Prise en main de l’automatisation de campagne
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
exl-id: 0be1c5f5-f07d-46dc-bebc-5eb50f466547
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 2%

---

# Gestion et automatisation des processus

Configurez Campaign pour tirer parti des puissantes fonctionnalités d’automatisation des campagnes marketing.

Vous pouvez configurer :

* Workflows
* Campagnes récurrentes
* Cycle de validation de bout en bout
* Alertes
* Envoi automatique de rapports
* Événements déclenchés

## Conception et utilisation de workflows{#gs-ac-wf}

Utilisez les workflows Adobe Campaign pour améliorer la vitesse et l’échelle de chaque aspect de vos campagnes marketing, de la création de segments à la préparation de messages en passant par la diffusion.

En savoir plus sur les workflows dans ces sections :

* [Commencer avec les flux de travaux](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html?lang=en#automating-with-workflows)
* Activités de workflow
   * [Activités](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html) de ciblage : requête, lecture de la liste, de l’enrichissement, de l’union, etc.
   * [Activités](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/flow-control-activities/about-flow-control-activities.html) de contrôle de flux : Planificateur, fourchette, alerte, signal externe, etc.
   * [Activités](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html) d&#39;action : diffusions entre canaux, code JavaScript, activités CRM, agrégat de mise à jour, etc.
   * [Activités](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/action-activities/about-action-activities.html) événements : transfert de fichiers, téléchargement Web, etc.
* [Découvrez les cas d&#39;utilisation de bout en bout](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/about-workflow-use-cases.html)
* [Création d’une audience dans un processus de campagne marketing](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow)
* [Bonnes pratiques relatives aux workflows](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/workflow-best-practices.html)
* [Flux de travail techniques intégrés](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/advanced-management/about-technical-workflows.html)
* [Exécution des workflows de surveillance](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html)

## Configuration de campagnes récurrentes

Créez une instance de diffusion récurrente et créez-en une chaque fois qu’elle s’exécute. Par exemple, si votre flux de travail est conçu pour s’exécuter une fois par semaine, cela créera 52 Diffusions après une année. Cela signifie également que les journaux seront séparés par chaque instance de diffusion.

:flèche_supérieur_droite : Découvrez comment créer une campagne récurrente dans [la documentation du Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#recurring-and-periodic-campaigns).

## Configuration de votre cycle de validation de bout en bout

Configurez le processus d’approbation pour chaque étape de vos diffusions et veillez à surveiller et contrôler intégralement les divers processus de vos campagnes marketing : ciblage, contenu, budget, extraction et envoi d’un BAT.

Les notifications sont envoyées aux opérateurs Adobe Campaign configurés en tant que réviseurs pour les informer d’une demande d’approbation.

:flèche_supérieur_droite : Découvrez comment configurer et gérer le processus d’approbation dans [la documentation du Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html).


## Envoyer des alertes

En tant qu’opérateur Campaign, vous pouvez recevoir des alertes en cas d’échec.

Vous pouvez créer un processus qui vous permettra de surveiller l&#39;état d&#39;un ensemble de workflows et d&#39;envoyer des messages récurrents aux superviseurs.

:flèche_supérieur_droite : Découvrez comment créer un flux de travail pour surveiller l&#39;état des autres workflows dans [la documentation du Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/supervising-workflows.html?lang=en#step-1--creating-the-monitoring-workflow).

Vous pouvez également recevoir une alerte en cas d’échec

## Envoyer des rapports automatiques

:flèche_supérieur_droite : Découvrez comment envoyer automatiquement un rapport à une liste d&#39;opérateurs [documentation du Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/monitoring/sending-a-report-to-a-list.html?lang=en#step-1--creating-the-recipient-list).


## Exploiter les événements de déclenchement

Utilisez la messagerie Campaign Transactional pour automatiser les messages générés à partir de événements déclenchés à partir de systèmes d&#39;information. Ces messages transactionnels peuvent être une facture, une confirmation de commande, une confirmation d&#39;expédition, un changement de mot de passe, une notification d&#39;indisponibilité du produit, un relevé de compte ou la création d&#39;un compte Web, par exemple. Ces messages peuvent être envoyés individuellement ou par lots par courriel, SMS ou notifications Push.

:flèche_supérieur_droite : Pour en savoir plus sur les fonctionnalités de messagerie transactionnelle, consultez la [documentation du Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html?lang=en#transactional-messaging).


Connectez Adobe Campaign et Adobe Analytics pour récupérer les actions des utilisateurs et envoyer des messages personnalisés en temps quasi réel.

:flèche_supérieur_droite : Découvrez comment intégrer Campaign aux déclencheurs Analytics dans [la documentation du Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/experience-triggers/about-triggers.html?lang=en#integrating-with-adobe-experience-cloud).

: bulb: Découvrez comment intégrer Campaign à d&#39;autres solutions dans [cette section](../start/connect.md)
