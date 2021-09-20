---
title: Notes de mise à jour de Campaign v8
description: Dernière version de Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471,a9d18e75-18e7-491e-bfc4-671c3600396e
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '756'
ht-degree: 100%

---

# Dernière version{#latest-release}

Cette page répertorie les nouvelles fonctionnalités, les améliorations et les correctifs de la **dernière version de Campaign Classic v8**.

## Version 8.1.20 {#release-8-1-20}

_7 septembre 2021_

**Améliorations de la sécurité**

* Correction d’un problème de sécurité afin de renforcer la protection contre les attaques par traversée de répertoires. (NEO-28547)

**Améliorations**

* À l’issue de sa fin de vie, Flash a été supprimé de l’ensemble des fonctionnalités et composants de Campaign associés et remplacé par HTML5. Le type de graphique **Gauge** a été supprimé. (NEO-30330) [En savoir plus](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/creating-a-chart.html?lang=fr)
* Lors de l’installation de la console cliente sous Windows, le programme d’installation vérifie maintenant s’il existe un nœud de registre parent et en crée un si ce n’est pas le cas. Des problèmes potentiels sont ainsi évités lors du lancement de la console. (NEO-34854)
* La fonctionnalité de tracking de signature a été améliorée afin d’éviter les erreurs liées à la façon dont les outils tiers (clients de messagerie, navigateurs Internet, etc.) gèrent les caractères spéciaux. Les paramètres d’URL sont maintenant codés.

**Autres changements**

* Les connecteurs Microsoft CRM (déploiements Office 365 et On-premise) précédemment obsolètes ont été supprimés de l’interface. [En savoir plus](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=fr#configure-acc-for-microsoft)
* Suite à la migration vers Tomcat 8, le script de configuration IIS a été mis à jour afin de corriger les problèmes d&#39;intégration IIS. (NEO-31019)
* Une barrière de sécurité a été ajoutée pour permettre uniquement l’exécution du [workflow technique de facturation](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/monitoring-processes.html?lang=fr#billing-report) sur l’instance marketing.
* L&#39;identification de la source de données a été améliorée dans les onglets de données et de schéma de la fenêtre **Affichage de la population** des transitions de workflow.
* Des index de base de données manquants ont été ajoutés aux schémas suivants afin d’éviter des problèmes de mise à jour de la base de données : xtk:rights, nms:dlvExclusion, nms:seedMember, nms:trackingUrl

**Correctifs**

* Correction d’un problème qui empêchait le fonctionnement du rapport **Position des clics** lorsque des offres étaient liées à la diffusion. (NEO-26295)
* Correction d’un problème lié à l’activité **Sous-workflow** lorsque son exécution ne générait pas de tableau de sortie. (NEO-36242)
* Correction de divers problèmes lors de l’exportation du rapport **Analyse descriptive** au format PDF. (NEO-25847)
* Correction d’un problème qui entraînait l’échec des diffusions lors de l’utilisation d’une diffusion par courrier externe. (NEO-37435)
* Correction d&#39;une erreur lors de la connexion à Microsoft CRM à l&#39;aide de l’API Web. Le message d’erreur a été supprimé, car les fonctionnalités n’étaient pas affectées.
* Correction d’un problème de déduplication des logs de tracking lorsque le serveur mid-sourcing était défini comme relais entre les serveurs de tracking et marketing. (NEO-36285)
* Correction d’une régression qui empêchait Vault d’être utilisé comme magasin de code spécifique.
* Correction d’un problème qui empêchait l’utilisation de variables dans une activité de workflow **Enrichissement** lorsque la transition entrante provenait d’une source de données FDA.
* Correction d’un problème lié à FFDA qui empêchait la réplication correcte des groupes d’opérateurs et des droits.
* Correction d’un problème qui entraînait l’envoi d’un lien de désabonnement incorrect par le biais de la diffusion.
* Correction d’un problème dans la gestion de la réplication qui avait un impact sur la durée du postupgrade.
* Correction d’un problème qui empêchait l’affichage de la **Position des clics**.
* Correction d’un problème qui entraînait des URL rompues dans les e-mails.

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
<td> <p>Le <a href="../send/line.md">canal LINE</a> est maintenant disponible avec Campaign v8. Il comprend les améliorations suivantes lorsqu’il est combiné avec le module de <a href="../send/transactional.md">messagerie transactionnelle</a> :
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
