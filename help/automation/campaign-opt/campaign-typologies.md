---
product: campaign
title: Prise en main des typologies de campagne
description: Découvrez comment configurer et implémenter des typologies de campagne
feature: Typology Rules
exl-id: 7832ffe1-eb65-4b37-9fc5-1374516755d9
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 57%

---

# Prise en main des typologies de campagne{#about-campaign-typologies}

Le module d’optimisation des campagnes d’Adobe Campaign permet de contrôler, de filtrer et de surveiller l’envoi des diffusions. Pour éviter les conflits entre les campagnes, Adobe Campaign peut tester différentes combinaisons en appliquant des règles de contrainte spécifiques. Elles permettent de s’assurer que les messages envoyés répondent aux attentes et aux besoins des clients et des stratégies de communication de l’entreprise.

![](assets/do-not-localize/how-to-video.png) [Découvrez cette fonctionnalité en vidéo](#typologies-video)

>[!NOTE]
>
>Selon votre offre, Campaign Optimization peut être inclus ou proposé sous la forme d&#39;un composant additionnel. Vérifiez votre contrat de licence.

## Règles de typologie et typologies {#typology-rules}

Avec Adobe Campaign, vous pouvez concevoir et appliquer quatre types de **règles de typologie**:

* Les règles de **filtrage** qui vous permettent d’exclure une partie de la cible en fonction de critères. [En savoir plus](filtering-rules.md).
* Les règles de **pression** qui vous permettent de contrôler la lassitude marketing. [En savoir plus](pressure-rules.md).
* Les règles de **capacité** qui vous permettent de limiter les charges pour garantir des conditions de traitement optimales. [En savoir plus](consistency-rules.md#controlling-capacity).
* Les règles de **contrôle** qui vous permettent de vérifier la validité des messages avant leur envoi. [En savoir plus](control-rules.md).

Une fois créées, les règles de typologie sont regroupées dans l&#39;opération. **typologies** qui sont référencés dans les diffusions. [En savoir plus](#apply-typologies).

Une typologie de campagne peut contenir plusieurs règles de typologie, mais une diffusion ne peut référencer qu&#39;une seule typologie.

Les règles et typologies de typologie intégrées sont disponibles dans la section **[!UICONTROL Administration > Gestion de campagne > Gestion des typologies]** noeud de l’Explorateur Campaign.

Pour chaque typologie, la variable **[!UICONTROL Règles]** vous permet d&#39;ajouter, supprimer ou visualiser les règles de typologie à appliquer.

![](assets/campaign_opt_rules_tab.png)

## Principales étapes pour appliquer des typologies {#apply-typologies}

Les étapes clés pour créer et appliquer une typologie à vos diffusions sont répertoriées ci-dessous :

1. Créez des règles de typologie et créez une typologie pour les y référencer.
Les étapes détaillées sont répertoriées dans la section suivante :
   * [Règles de pression](pressure-rules.md)
   * [Règles de filtrage](filtering-rules.md)
   * [Règles de capacité](consistency-rules.md)
   * [Règles de contrôle](control-rules.md)

1. Configurez votre diffusion pour utiliser la typologie que vous avez créée. [En savoir plus](apply-rules.md#apply-a-typology-to-a-delivery).
1. Testez et contrôlez le comportement par le biais de simulations de campagne. [En savoir plus](campaign-simulations.md).

Lors de la préparation de la diffusion, les destinataires sont exclus lorsque le critère est satisfait. Vous pouvez consulter les journaux pour surveiller les exclusions.

Des exemples de cas d’utilisation des règles de typologie de pression sont disponibles dans la section [cette page](pressure-rules.md#use-cases-on-pressure-rules).

## Tutoriels vidéo {#typologies-video}

### Configuration de la gestion de la lassitude à l&#39;aide de règles de typologie

Cette vidéo explique comment implémenter la gestion de la fatigue dans Adobe Campaign en utilisant les règles de typologie.

>[!VIDEO](https://video.tv.adobe.com/v/25090?quality=12)

### Configuration de la gestion de la fatigue à l’aide de filtres prédéfinis

La gestion de la lassitude contrôle la fréquence et le nombre des messages afin d&#39;éviter une sollicitation excessive des destinataires. Si votre instance ne contient pas le module d&#39;optimisation de campagne, vous pouvez configurer un filtre prédéfini qui filtrera la population cible en fonction du nombre de messages reçus. Cette vidéo explique comment implémenter la gestion de la fatigue dans Adobe Campaign  à l&#39;aide de filtres.

>[!VIDEO](https://video.tv.adobe.com/v/25091?quality=12)
