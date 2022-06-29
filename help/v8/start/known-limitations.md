---
title: Limites connues de Campaign v8
description: Limites connues
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: true
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
source-git-commit: 63e109f31706880a1723dfd0c611835842e39083
workflow-type: ht
source-wordcount: '228'
ht-degree: 100%

---

# Limites connues

Les limites connues identifient les fonctionnalités, l&#39;architecture ou les processus qui ne sont pas pris en charge par cette version du produit ou qui n&#39;interagissent pas correctement avec celle-ci. Examinez attentivement ces limites.

Pour Adobe Campaign v8, les limites suivantes existent :

* Adobe Campaign v8 n&#39;est pas disponible pour les déploiements on-premise/hybrides. Il est disponible uniquement en tant que Managed Cloud Service d&#39;Adobe.
* Les clients existants ne peuvent pas migrer d&#39;un environnement Adobe Campaign existant vers Adobe Campaign v8
* Dans le contexte d’un [Déploiement Enterprise (FFDA)](../architecture/enterprise-deployment.md), aucune réplication de données bidirectionnelle n’est fournie : la réplication se produit uniquement de la base de données locale Campaign vers la base de données Cloud.
* Les fonctionnalités répertoriées [dans cette section](v7-to-v8.html#gs-unavailable-features) ne sont pas disponibles dans la versio actuelle de Campaign v8.
* Certaines fonctionnalités non disponibles ou supprimées sont toujours visibles dans l&#39;interface utilisateur.
* Dans le contexte d’un [Déploiement Enterprise (FFDA)](../architecture/enterprise-deployment.md), les mécanismes d’abonnement (opt-in) et de désabonnement (opt-out), et l’enregistrement mobile sont des processus asynchrones. Les demandes sont traitées toutes les heures par l&#39;intermédiaire d&#39;un workflow technique spécifique. [En savoir plus](../architecture/replication.md#tech-wf)
* Les doublons doivent être gérés manuellement par les utilisateurs finaux. [En savoir plus](../architecture/keys.md)
* Adobe Campaign v8 ne prend pas en charge le débit étendu sur les API et les applications web. En cas de besoins spécifiques, contactez Adobe pour obtenir des conseils.
* Le module Optimisation des campagnes (Campaign Optimization) dʼAdobe Campaign ne prend pas en compte les diffusions planifiées dans les règles de typologie de pression. Apprenez-en davantage en consultant la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/pressure-rules.html?lang=fr#setting-the-period).