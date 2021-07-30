---
product: Adobe Campaign
title: Notes de mise à jour de Campaign v8
description: Dernière version de Campaign v8
feature: Vue d’ensemble
role: Data Engineer
level: Beginner
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471,a9d18e75-18e7-491e-bfc4-671c3600396e
source-git-commit: 328f1bca11f8554def6ad4ccb741a86695481e98
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 91%

---

# Dernière version{#latest-release}

Cette page répertorie les nouvelles fonctionnalités, les améliorations et les correctifs de la **dernière version de Campaign Classic v8**.

## Version 8.1.14 {#release-8-1-14}

_23 juillet 2021_

**Nouveautés**

<table>
<thead>
<tr>
<th><strong>Nouvelle activité de workflow : Modifier la source de données</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>La nouvelle activité de workflow <b>Modifier la source de données</b> permet de modifier la source de données de la table de travail d’un workflow. Cela offre plus de flexibilité pour la gestion des données entre différentes sources de données (FDA, FFDA et base de données locale).</p>
<p>Dans les workflows Adobe Campaign, les données sont gérées à l’aide de tables de travail (ou temporaires). Au fur et à mesure de l’exécution d’un workflow, les tables de travail partagent les données entre les activités du workflow. Par défaut, les tables de travail sont créées dans la même base de données que la source des données sur lesquelles nous effectuons des requêtes.</p>
<p>Avec Campaign v8, la table des profils principaux est directement stockée dans la base de données cloud. L’interrogation de la table Profils crée donc également une table de travail sur la base de données cloud. Dans certains cas, il peut être judicieux de déplacer la table de travail vers une autre source de données afin d’effectuer des opérations spécifiques.</p>
<p>Pour plus d'informations, consultez la <a href="../config/workflows.md#change-data-source-activity">documentation détaillée</a>.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>Disponibilité du canal LINE</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Le <a href="../send/line.md">canal LINE</a> est désormais disponible avec Campaign v8, y compris les améliorations suivantes lorsqu’elles sont combinées avec le module <a href="../send/transactional.md">messagerie transactionnelle</a> :
<ul> 
<li><p>Correction d'une erreur qui pouvait empêcher les visiteurs d'être ciblés dans une diffusion LINE. 
</p></li>
<li><p>Correction d’un problème qui pouvait entraîner des erreurs lors de la récupération de visiteurs de l’instance d’exécution vers l’instance marketing.
</p></li>
<li><p>Correction de problèmes lors du traitement des événements temps réel.</p></li>
</ul>
</td> 
</tr> 
</tbody> 
</table>

**Autres améliorations**

* Correction d’un problème qui empêchait l’affichage du rapport **Position des clics** pour des diffusions spécifiques.
* Correction d’un problème lié à l’activité de workflow **Déduplication** qui pouvait entraîner un comptage en double inexact.
* Correction d’un problème lors de l’utilisation d’une requête de workflow avec le filtre « L’identifiant n’est pas vide » qui pouvait entraîner l’affichage d’un élément vide dans la population de transition.
* Correction d’un problème qui empêchait la création de champs supplémentaires dans un nouveau mapping de ciblage.
