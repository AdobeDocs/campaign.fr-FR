---
product: Adobe Campaign
title: Limites connues de Campaign v8
description: Limites connues
feature: Vue d'ensemble
role: Data Engineer
level: Beginner
hidefromtoc: true
source-git-commit: cf00895f988514fc029d0060d7404bdef0c8b30e
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 87%

---

# Limites connues

Les limites connues identifient les fonctionnalités, l&#39;architecture ou les processus qui ne sont pas pris en charge par cette version du produit ou qui n&#39;interagissent pas correctement avec celle-ci. Examinez attentivement ces limites.

Pour Adobe Campaign v8, les limites suivantes existent :

* Adobe Campaign v8 n&#39;est pas disponible pour les déploiements on-premise/hybrides. Il est disponible uniquement en tant que Managed Cloud Service d&#39;Adobe.
* Les clients existants ne peuvent pas migrer d&#39;un environnement Adobe Campaign existant vers Adobe Campaign v8
* Aucune réplication bidirectionnelle des données : la réplication se produit uniquement de la base de données locale Campaign vers la base de données Cloud.
* Les fonctionnalités répertoriées [dans cette section](capability-matrix.md#gs-unavailable-features) ne sont pas disponibles dans la versio actuelle de Campaign v8.
* Certaines fonctionnalités non disponibles ou supprimées sont toujours visibles dans l&#39;interface utilisateur.
* Les mécanismes d&#39;abonnement (opt-in) et de désabonnement (opt-out), et l&#39;enregistrement mobile sont des processus asynchrones. Les demandes sont traitées toutes les heures par l&#39;intermédiaire d&#39;un workflow technique spécifique. [En savoir plus](../config/replication.md#tech-wf)
* Les doublons doivent être gérés manuellement par les utilisateurs finaux. [En savoir plus](../dev/keys.md)
* Adobe Campaign v8 ne prend pas en charge le débit étendu sur les API et les applications web. En cas de besoins spécifiques, contactez l&#39;Adobe pour obtenir des conseils.


