---
title: Notes de mise à jour de Campaign v8 2021
description: Liste des fonctionnalités et améliorations des versions 2021 de Campaign v8
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
source-git-commit: e7f4982a9b13fe5413b6cce0a1cc58e2b3a6afa4
workflow-type: tm+mt
source-wordcount: '1592'
ht-degree: 100%

---

# Notes de mise à jour 2021{#2021-release}

Cette page répertorie les nouvelles fonctionnalités, les améliorations et les correctifs des **dernières versions 2021 de Campaign Classic v8**.

## Version 8.2.8 {#release-8-2-8}

_28 octobre 2021_

<table>
<thead>
<tr>
<th><strong>Interaction entrante</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Real-time interaction management est désormais disponible pour les canaux entrants. Utilisez le module Interaction entrante Campaign pour présenter la meilleure offre à vos clients lorsqu’ils visitent votre site web ou contactent votre centre d’appel. Cette fonctionnalité est fournie avec Campaign v8 comme option et nécessite une configuration spécifique sur votre instance. Contactez votre représentant Adobe pour avoir accès au module Interaction entrante.</p>
<p>Pour plus d’informations, consultez la <a href="../interaction/interaction-architecture.md">documentation détaillée</a>.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>Optimisation des campagnes</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Le module Optimisation des campagnes est désormais disponible. Ce module permet de contrôler, de filtrer et de surveiller l’envoi des diffusions. Pour éviter les conflits entre les campagnes, Adobe Campaign peut tester différentes combinaisons en appliquant des règles de contrainte spécifiques. Elles permettent de s’assurer que les messages envoyés répondent aux attentes et aux besoins des clients et des stratégies de communication de l’entreprise.</p>
<p>Pour plus d’informations, consultez la <a href="https://experienceleague.adobe.com/docs/campaign/automation/campaign-optimization/campaign-typologies.html?lang=fr">documentation détaillée</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong>Unicity Service</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Unicity Service est un nouveau composant Cloud Database Manager. Il permet aux utilisateurs de préserver et de surveiller l’intégrité des contraintes de clé unique dans les tables de base de données cloud (Cloud Database). Cela permet de réduire le risque d’insertion de clés en double.
<p>Comme Cloud Database n’applique pas les contraintes d’unicité, Unicity Service introduit au niveau de l’application, <b>un ensemble de nouveaux mécanismes de sécurisation</b> qui réduisent le risque d’insertion de doublons lors de la gestion des données avec Adobe Campaign.</p> 
<p>Unicity Service lance un nouveau workflow intégré appelé <b>ffdaUnicity</b> pour surveiller les contraintes d’unicité et alerter lorsque des doublons sont détectés.</p>
<p>Pour plus d’informations, consultez la <a href="../architecture/keys.md">documentation détaillée</a>.</p>
</td> </tr> 
</tbody> 
</table>


**Améliorations**

* Le connecteur Snowflake a été amélioré en termes de performances.
* À des fins de surveillance et de test, les journaux d’audit du workflow de données **[!UICONTROL Répliquer les données Staging]** incluent désormais le nombre d’enregistrements envoyés à la base de données FFDA (Full Federated Data Access).
* L’activité Code SQL permet désormais de choisir dans quelle base de données sera stocké le script SQL : la source de données par défaut ou le compte externe FDA principal choisi.
* Un ensemble d’entrepôts prédéfinis est désormais disponible et peut être utilisé pour exécuter diverses requêtes en parallèle, telles que la segmentation, l’ETL ou les pics. [En savoir plus](../config/workflows.md)

**Autres changements**

* Le champ **[!UICONTROL Identifiant chiffré]** a été ajouté au schéma des visiteurs (`nms:visitor`). Ce champ est calculé et doit être utilisé pour les applications web.
* Correction dʼun problème qui entraînait lʼéchec de lʼanalyse des diffusions lorsque certaines affinités IP existaient dans certains conteneurs de mid-sourcing mais pas dans tous. Désormais, les affinités IP sont toutes stockées dans la base de données, de sorte que n’importe quel conteneur puisse accéder aux affinités présentes dans tous les autres conteneurs. (NEO-37564)
* Vous pouvez désormais importer un package comportant plusieurs schémas et nœuds d’arborescence de navigation.

**Correctifs**

* Dans un schéma de données, lors de la suppression par un utilisateur de lʼattribut `<autoStg>` dʼun élément de définition de table ou la modification de sa valeur de `true` à `false`, la table dlʼévaluation associée nʼétait pas supprimée. Ce problème est à présent résolu.
* Correction dʼun problème qui entraînait une erreur lors de la création dʼenregistrements au moyen dʼun formulaire dédié en raison de la gestion des identifiants avec une source de données FFDA.
* Correction dʼun problème qui empêchait lʼinsertion dʼoffres dans une diffusion si celles-ci étaient gérées par une activité dʼenrichissement dans un workflow.
* Correction dʼun problème en raison duquel lʼimportation de packages pouvait être ralentie.
* Correction dʼun problème en raison duquel les diffusions e-mail avec des adresses de contrôle nʼétaient pas envoyées.
* Correction dʼun problème en raison duquel les propositions nʼétaient pas enregistrées dans la table des propositions dʼoffre.
* Correction dʼun problème en raison duquel les problèmes de délai dʼexpiration du réseau étaient incorrectement enregistrés en tant que problèmes dʼinterruption de script au lieu dʼerreurs de réseau. Ce problème se produisait dans le cas de requêtes HTTP incluses dans les activités JavaScript.
* Correction d’un problème qui empêchait la réplication des offres dans l’environnement des offres en ligne sur Snowflake.
* Correction d’un problème qui ignorait l’attribut &#39;autoStg&#39; pour les schémas intégrés non étendus.
* Correction d’un problème qui empêchait les utilisateurs de sélectionner le lien **[!UICONTROL Pays/zone géographique]** lors de la prévisualisation d’un profil.
* Correction d’un problème en raison duquel le sélecteur de date dans les rapports personnalisés entraînait une erreur de script. (NEO-36345)
* Correction d’un problème en raison duquel le système se bloquait lors de la régénération de la configuration en cas de fichiers de configuration erronés.
* Correction dʼun problème qui entraînait lʼéchec de la mise à niveau des instances marketing et de contrôle.
* Correction dʼun problème qui entraînait le blocage du workflow de facturation sur les instances marketing.
* Correction dʼun problème qui pouvait entraîner la duplication de clés dans les tables FFDA Snowflake prêtes à lʼemploi. (NEO-38583)
* Correction dʼun problème qui pouvait entraîner la perte de schémas temporaires de workflow lors de la modification de deux activités de déduplication lʼune après lʼautre. (NEO-34063)
* Correction dʼun problème en raison duquel des résultats incorrects étaient renvoyés lors de lʼexécution des fonctions Amazon Redshift HoursDiff et MinutesDiff lors de la tentative dʼextraction du composant dʼheure.(NEO-31673)
* Correction dʼun problème au cours duquel les utilisateurs ne parvenaient pas à se connecter à la console en raison dʼun problème de configuration du proxy. (NEO-38388)
* Correction dʼun problème de régression qui empêchait la fonctionnalité **Purger le dossier** de fonctionner correctement. (NEO-37459)
* Correction dʼun problème en raison duquel les diffusions mobiles jointes à un workflow ne pouvaient pas être prévisualisées.
* Correction dʼun problème en raison duquel lʼactivité du workflow de **Lecture de liste** ne fonctionnait pas lorsque la liste était identifiée dans la base de données par un identifiant négatif. (NEO-39607)

## Version 8.1.20 {#release-8-1-20}

_7 septembre 2021_

**Améliorations de la sécurité**

* Correction d’un problème de sécurité afin de renforcer la protection contre les attaques par traversée de répertoires. (NEO-28547)

**Améliorations**

* Après sa fin de vie, Flash a été supprimé de toutes les fonctionnalités et composants de Campaign associés, et remplacé par HTML5. Le type de graphique **Jauge** a été supprimé. (NEO-30330) [En savoir plus](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/creating-a-chart.html?lang=fr)
* Lors de l’installation de la console cliente sous Windows, le programme d’installation vérifie maintenant s’il existe un nœud de registre parent et en crée un s’il n’en existe pas. Cela évite les problèmes potentiels lors du lancement de la console. (NEO-34854)
* La fonctionnalité de signature de suivi a été améliorée afin d’éviter les erreurs liées à la manière dont les outils tiers (clients de messagerie, navigateurs Internet, etc.) gèrent les caractères spéciaux. Les paramètres d’URL sont désormais chiffrés.

**Autres changements**

* Les connecteurs Microsoft CRM (déploiements Office 365 et On-premise) précédemment obsolètes ont été supprimés de l’interface. [En savoir plus](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=fr#configure-acc-for-microsoft)
* Suite à la migration vers Tomcat 8, le script de configuration IIS a été mis à jour afin de corriger les problèmes d&#39;intégration IIS. (NEO-31019)
* Un mécanisme de sécurisation a été ajouté pour permettre uniquement l’exécution du [workflow technique de facturation](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/monitoring-processes.html?lang=fr#billing-report) sur l’instance marketing.
* L&#39;identification de la source de données a été améliorée dans les onglets de données et de schéma de la fenêtre **Visualiser la population** des transitions de workflow.
* Des index de base de données manquants ont été ajoutés aux schémas suivants afin d’éviter des problèmes de mise à jour de la base de données : xtk:rights, nms:dlvExclusion, nms:seedMember, nms:trackingUrl

**Correctifs**

* Correction d’un problème qui empêchait le fonctionnement du rapport **Position des clics** lorsque des offres étaient liées à la diffusion. (NEO-26295)
* Correction d’un problème lié à l’activité **Sous-workflow** lorsque son exécution ne générait pas de table de sortie. (NEO-36242)
* Correction de divers problèmes lors de l’exportation du rapport **Analyse descriptive** au format PDF. (NEO-25847)
* Correction d’un problème qui entraînait l’échec des diffusions lors de l’utilisation d’une diffusion par courrier externe. (NEO-37435)
* Correction d&#39;une erreur lors de la connexion à Microsoft CRM à l&#39;aide de l&#39;API web. Le message d’erreur a été supprimé, car les fonctionnalités n’ont pas été affectées.
* Correction d’un problème de déduplication des logs de tracking lorsque le serveur mid-sourcing était défini comme relais entre les serveurs de tracking et marketing. (NEO-36285)
* Correction d’une régression qui empêchait Vault d’être utilisé comme entrepôt de code spécifique.
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
<p>Dans les workflows Adobe Campaign, les données sont gérées à l’aide de tables de travail (ou temporaires). Au fur et à mesure de l’exécution d’un workflow, les tables de travail partagent les données entre les activités du workflow. Par défaut, les tables de travail sont créées dans la même base de données que la source des données sur lesquelles nous effectuons des requêtes.</p>
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
