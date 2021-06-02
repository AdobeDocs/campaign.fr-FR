---
product: Adobe Campaign
title: Limites connues de Campaign v8
description: Limites connues
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
hidefromtoc: true
source-git-commit: 08c1f2fbe79845fe54670e25ac4a63ab65517513
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 3%

---

# Limites connues

Les limites connues identifient les fonctionnalités, l’architecture ou les processus qui ne sont pas pris en charge par cette version du produit ou qui n’interagissent pas correctement avec celui-ci. Examinez attentivement ces limites.

Pour Adobe Campaign v8, les restrictions suivantes s’appliquent :

* Adobe Campaign v8 n’est pas disponible pour les déploiements on-premise/hybrides. Il est disponible uniquement en tant que Cloud Service géré par Adobe.
* Les clients existants ne peuvent pas migrer d’un environnement Adobe Campaign existant vers Adobe Campaign v8
* Aucune réplication bidirectionnelle des données : la réplication se produit uniquement de la base de données locale Campaign vers la base de données Cloud.
* Les fonctionnalités répertoriées [dans cette section](capability-matrix.md#gs-unavailable-features) ne sont pas disponibles dans le build actuel de Campaign v8.
* Certaines fonctionnalités non disponibles ou supprimées sont toujours visibles dans l’interface utilisateur.
* Les mécanismes d’inscription (opt-in) et de désinscription (opt-out), et l’enregistrement mobile sont des processus asynchrones. Les demandes sont traitées toutes les heures par l’intermédiaire d’un workflow technique spécifique. [En savoir plus](../config/replication.md#tech-wf)
* Les doublons doivent être gérés manuellement par les utilisateurs finaux. [En savoir plus](../dev/keys.md)
* LINE - pour confirmer + détails
* Latence - pour confirmer + détails
