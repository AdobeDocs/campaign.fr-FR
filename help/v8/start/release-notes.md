---
title: Notes de mise à jour de Campaign v8
description: Dernière version de Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471,a9d18e75-18e7-491e-bfc4-671c3600396e
source-git-commit: 0061c536ff309d86061548b98d2c6e1124e01a0e
workflow-type: tm+mt
source-wordcount: '1604'
ht-degree: 50%

---

# Dernière version{#latest-release}

Cette page répertorie les nouvelles fonctionnalités, les améliorations et les correctifs de la **dernière version de Campaign Classic v8**.

## Version 8.2.1 {#release-8-2-1}

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
<p>La gestion des interactions en temps réel est désormais disponible pour les canaux entrants. Utilisez le module Interaction entrant de Campaign pour présenter la meilleure offre à vos clients lorsqu'ils visitent votre site web ou se rendent dans votre centre d'appels. Cette fonctionnalité est fournie avec Campaign v8 comme option et nécessite une configuration spécifique sur votre instance. Contactez votre représentant d’Adobe pour avoir accès au module Interaction entrant.</p>
<p>Pour plus d'informations, consultez la <a href="../send/interaction-architecture.md">documentation détaillée</a>.</p>
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
<td> <p>Le module Optimisation des campagnes est désormais disponible. Ce module permet de contrôler, filtrer et suivre l'envoi des diffusions. Pour éviter les conflits entre les campagnes, Adobe Campaign peut tester différentes combinaisons en appliquant des règles de contrainte spécifiques. Elles permettent de s’assurer que les messages envoyés répondent aux attentes et aux besoins des clients et des stratégies de communication de l’entreprise.</p>
<p>Pour plus d’informations, reportez-vous à la section <a href="https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/about-campaign-typologies.html">Documentation de Campaign Classic v7</a>.</p>
</td> 
</tr> 
</tbody> 
</table>
<table> 
<thead>
<tr> 
<th> <strong>Service d'unicité</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Unicity Service est un nouveau composant Cloud Database Manager. Elle permet aux utilisateurs de préserver et de surveiller l’intégrité des contraintes de clé uniques dans les tables de la base de données cloud. Cela permet de réduire le risque d'insertion de clés en double.
<p>Comme la base de données Cloud n’impose pas de contraintes d’unicité, le service d’unicité s’introduit au niveau de l’application, <b>un ensemble de nouvelles barrières de sécurité</b> réduire le risque d’insertion de doublons lors de la gestion des données avec Adobe Campaign.</p> 
<p>Le service d’unicité lance un nouveau workflow intégré appelé <b>ffdaUnicity</b> pour surveiller les contraintes d’unicité et alerter lorsque des doublons sont détectés.</p></td> </tr> 
</tbody> 
</table>

**Améliorations**

* Le connecteur du Snowflake a été amélioré en termes de performances.
* Dans le fichier de configuration du serveur (serverConf.xml), vous pouvez maintenant définir un temps d’attente, par schéma, entre les mises à jour et les réplications de validation à la volée.
* À des fins de surveillance et de test, les journaux d’audit de la variable **[!UICONTROL Réplication des données d’évaluation]** workflow inclut désormais le nombre d’enregistrements envoyés à la base de données FFDA (Full Federated Data Access).
* L&#39;activité Code SQL permet désormais de choisir dans quelle base de données sera stocké le script SQL : la source de données par défaut ou le compte externe FDA principal choisi.
* Un ensemble d’entrepôts prédéfinis est désormais disponible et peut être utilisé pour exécuter diverses requêtes en parallèle, telles que la segmentation, l’ETL ou les pics. [En savoir plus](../config/workflows.md)

**Autres changements**

* Le **[!UICONTROL Identifiant crypté]** a été ajouté au schéma du visiteur (`nms:visitor`). Ce champ est calculé et doit être utilisé pour les applications web.
* Correction d’un problème en raison duquel l’analyse de diffusion échouait lorsque certaines affinités IP existaient dans certains conteneurs de mid-sourcing mais pas dans tous. Désormais, les affinités IP sont toutes stockées dans la base de données, de sorte que n’importe quel conteneur puisse accéder aux affinités présentes dans tous les autres conteneurs. (NEO-37564)
* Vous pouvez désormais importer un package comportant plusieurs schémas et noeuds d’arborescence de navigation.

**Correctifs**

* Une fois qu’un utilisateur a supprimé, dans un schéma de données, la variable `<autoStg>` à partir d’un élément de définition de table ou a modifié sa valeur à partir de `true` to `false`, la table d’évaluation associée n’a pas été supprimée. Ce problème a été corrigé.
* Correction d’un problème qui provoquait une erreur lors de la création d’enregistrements avec un formulaire dédié en raison de la gestion des identifiants avec une source de données FFDA.
* Correction d’une erreur qui empêchait l’insertion des offres dans une diffusion si les offres étaient gérées par une activité d’enrichissement dans un workflow.
* Correction d’un problème qui pouvait ralentir l’importation des packages.
* Correction d’un problème qui empêchait l’envoi de diffusions email avec des adresses de contrôle.
* Correction d’un problème qui empêchait l’enregistrement des propositions dans le tableau des propositions d’offre.
* Correction d’un problème en raison duquel les problèmes de délai d’expiration du réseau étaient incorrectement consignés en tant que problèmes d’interruption du script plutôt que des erreurs réseau. Ce problème se produisait dans le cas de requêtes HTTP incluses dans les activités JavaScript.
* Correction d’un problème qui empêchait la réplication des offres dans l’environnement des offres en direct sur Snowflake.
* Correction d’un problème qui ignorait l’attribut &#39;autoStg&#39; pour les schémas intégrés non étendus.
* Correction d’un problème qui empêchait les utilisateurs de sélectionner la variable **[!UICONTROL Pays/région]** lors de la prévisualisation d&#39;un profil.
* Correction d’un problème en raison duquel le sélecteur de données dans les rapports personnalisés entraînait une erreur de script. (NEO-36345)
* Correction d’un problème en raison duquel le système se bloquait lors de la régénération de la configuration en cas de fichiers de configuration incorrects.
* Correction d’un problème qui empêchait la mise à niveau des instances marketing et de contrôle.
* Correction d’un problème en raison duquel le workflow de facturation se bloquait sur les instances marketing.
* Correction d’un problème qui entraînait la duplication de clés dans les tables d’usine du Snowflake FFDA. (NEO-38583)
* Correction d’un problème qui entraînait la perte des schémas temporaires de workflow lors de l’édition de deux activités de déduplication l’une après l’autre. (NEO-34063)
* Correction d’un problème qui renvoyait des résultats incorrects lors de l’exécution des fonctions Amazon Redshift HoursDiff et MinutesDiff lors de la tentative d’extraction du composant temporel.(NEO-31673)
* Correction d’un problème qui empêchait les utilisateurs de se connecter à la console en raison d’un problème de configuration de proxy. (NEO-38388)
* Correction d’un problème de régression qui empêchait la variable **Purge du dossier** de fonctionner correctement. (NEO-37459)
* Correction d’un problème qui pouvait vous empêcher de prévisualiser des diffusions mobiles qui étaient jointes à un workflow.
* Correction d’un problème qui empêchait le **Lecture de liste** l’activité de workflow ne fonctionne pas lorsque la liste a été identifiée dans la base de données avec un identifiant négatif. (NEO-39607)

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
* Une barrière de sécurité a été ajoutée pour permettre uniquement l’exécution du [workflow technique de facturation](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/monitoring-processes.html?lang=fr#billing-report) sur l’instance marketing.
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
