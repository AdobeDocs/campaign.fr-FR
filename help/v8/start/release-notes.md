---
title: Notes de mise à jour de Campaign v8
description: Dernière version de Campaign v8
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: f215d10c2b8deffc73407bfc39628e2f7958650c
workflow-type: tm+mt
source-wordcount: '3381'
ht-degree: 100%

---

# Dernière version{#latest-release}

Cette page répertorie les nouvelles fonctionnalités, les améliorations et les correctifs de la **dernière version de Campaign Classic v8**.

## Version 8.4.1 {#release-8-4-1}

_30 septembre 2022_

**Nouveautés**

<table> 
<thead>
<tr> 
<th> <strong>Intégration d’Adobe Campaign à Adobe Experience Platform</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td><p>De nouveaux connecteurs source et de destination sont désormais disponibles afin de permettre une intégration transparente entre Adobe Campaign et Adobe Experience Platform :</p>
<ul><li>Utilisez le connecteur de destination Adobe Campaign Managed Cloud Services pour envoyer des segments Experience Platform à Adobe Campaign en vue de leur activation,</li>
<li>Utilisez le connecteur source Adobe Campaign Managed Cloud Service pour envoyer les logs de diffusion et de tracking Adobe Campaign à Adobe Experience Platform.</li>
</ul>
<p>Pour plus d’informations, consultez la <a href="../connect/ac-aep.md">documentation détaillée</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong>Disponibilité du canal twitter</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Le <a href="../send/twitter.md">canal social Twitter</a> est désormais disponible avec Campaign v8. Vous pouvez ainsi :</p>
<ul> 
<li><p>Envoyer des messages sur Twitter : Adobe Campaign vous permet de publier des messages directement sur votre compte Twitter. Vous pouvez également envoyer des messages directs à tous les abonnés de vos comptes.
</p></li>
<li><p>Collecter de nouveaux contacts : Adobe Campaign peut récupérer automatiquement les données de profil, ce qui vous permet ainsi d’exécuter des campagnes de ciblage et, lorsque cela est possible, d’implémenter des stratégies cross-canal.
</p></li>
</ul>
<p>Découvrez comment connecter Campaign et Twitter dans la <a href="../connect/ac-tw.md">documentation détaillée</a>.</p>
<p>Découvrez comment publier des tweets et envoyer des messages directs avec Campaign dans <a href="../connect/ac-tw.md">cette page</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Amélioration de la sécurité**

Pour optimiser la sécurité, les jetons de sécurité ont été supprimés des URL générées par Campaign :

* Cette modification s’applique uniquement aux URL GET. D’autres types, y compris les URL POST, ne sont pas affectés.
* Si vous utilisez du code personnalisé, les jetons de sécurité ne sont plus récupérés à partir du paramètre de jeton de sécurité de l’URL GET. Vous devez générer un nouveau jeton de sécurité à l’aide du code JSSP suivant :

   ```getNewSecurityToken(jsspContext.getSessionToken(), jsspContext.getSecurityToken(), true);```

   Vous pouvez également utiliser l’API de connexion pour récupérer les jetons de sécurité.
* La gestion des jetons de session ne change pas.

**Améliorations**

* Compte tenu de la fin de vie d’Internet Explorer 11, le moteur de rendu HTML dans la console utilise désormais **Microsoft Edge Chromium**. En outre, l’installation du runtime **Microsoft Edge WebView 2** est désormais requise pour toute installation de la console cliente.
* Amélioration de l’exécution des workflows avec une haute disponibilité des workflows. Cela permet d’exécuter simultanément plusieurs workflows dans différents conteneurs, afin de prévenir la perte du service de workflow et d’éviter les erreurs d’exécution associées. **Remarque** : cette nouvelle fonctionnalité est en disponibilité limitée et est réservée à un ensemble de clients uniquement.
* Les demandes d’accès à des informations personnelles sont désormais exécutées par lots pour un espace de nommage de confidentialité donné. Cette amélioration augmente le temps d’exécution des demandes de suppression en vertu du RGPD/de la confidentialité.

**Mises à jour de compatibilité**

* Le SDK Campaign v8 prend maintenant en charge iOS 16 pour les notifications push.

Reportez-vous à la [matrice de compatibilité de Campaign](compatibility-matrix.md).

**Correctifs**

* Correction d’un problème qui affectait les mises à jour du statut du journal de diffusion sur l’instance MID, lorsque l’option FeatureFlag_GZIP_Compression était activée. (NEO-49183)
* Correction d’un problème en raison duquel les diffusions pouvaient garder le statut **En attente** même si la date de contact avait été atteinte. (NEO-48079)
* Correction d’un problème dans les workflows en raison duquel des fichiers sur le serveur ne pouvaient pas être mis à jour lors de l’utilisation de l’activité **Chargement de données (fichier)**. Le processus s’est arrêté à 100 % mais n’a jamais pris fin. (NEO-47269)
* Correction d’un problème lors du postupgrade sur les environnements japonais. (NEO-46640)
* Correction d’une erreur qui pouvait se produire si une diffusion atteignait une taille précise pendant le processus MTA. (NEO-46097)
* Correction d’un problème en raison duquel les logs de tracking ne pouvaient pas renvoyer de données liées au navigateur du destinataire. (NEO-46612)
* Correction d’un problème qui entraînait des problèmes de personnalisation lors de l’envoi de SMS à l’aide d’un mode de diffusion externe. (NEO-46415)
* Correction d’un problème qui entraînait la génération de doublons dans les logs de tracking. (NEO-46409)
* Correction d’un problème en raison duquel le workflow technique (ffdaReplicateStagingData) **[!UICONTROL Répliquer les données d’évaluation]** ne pouvait pas s’arrêter même si une erreur s’était produite lors de son exécution. (NEO-46280)
* Afin de prévenir tout problème de lenteur lors de l’envoi de BAT aux adresses de contrôle, toutes les réplications consécutives des membres des adresses de contrôle sont désormais regroupées dans une seule demande de réplication. (NEO-44844)
* Correction d’un problème qui affichait un message d’erreur lors d’une tentative de prévisualisation d’une diffusion dans un événement archivé de Message Center. (NEO-43620)
* Correction d’un problème en raison duquel, lors de l’injection de données dans la base de données cloud Snowflake avec une activité de **requête** de Campaign ainsi qu’une activité **Modifier la source de données**, le processus échouait si une barre oblique inverse était présente dans les données. La chaîne source n’a pas été placée dans une séquence d’échappement et les données n’ont pas été traitées correctement sur Snowflake. (NEO-45549)
* Correction d’un problème qui se produisait lors de l’utilisation de l’activité **Requête** et du filtrage d’un tableau. Lorsqu’un nom de colonne contenait les mots « Mise à jour », une erreur de compilation se produisait avec un identifiant non valide et le message suivant : « nombre de lignes mises à jour ». (NEO-46485)
* Le workflow technique **Nettoyage de la base de données** gère désormais également les schémas d’évaluation personnalisés. (NEO-48974)
* Correction d’une erreur qui ralentissait l’analyse de la diffusion, lors de l’étape d&#39;exclusion des destinataires placés sur la liste bloquée, lors du ciblage d’un grand nombre de destinataires. (NEO-48019)
* Stabilité améliorée lors de la gestion des chaînes XML non valides lors des appels SOAP. (NEO-48027)
* Correction d’un problème qui entraînait la création de DeliveryParts superflus lorsque la diffusion utilisait les modes Calendrier et Partage. (NEO-48634)
* Correction d’un problème de performances lors de l’utilisation de vagues basées sur le calendrier. (NEO-48451)
* Correction d’un problème qui entraînait l’affichage d’un message d’erreur dans l’écran de la liste de diffusion après la création d’un nouveau mapping de ciblage sur un schéma personnalisé. (NEO-49237)
* Correction d’un problème qui entraînait une perte de données si le workflow d’évaluation était en erreur et que la période de conservation était complètement dépassée. (NEO-48975)

## Version 8.3.9 {#release-8-3-9}

>[!CAUTION]
>
> La mise à niveau de la console client est obligatoire. Découvrez comment mettre à niveau votre console client sur cette [page](../start/connect.md#download-ac-console).

_7 octobre 2022_

**Améliorations**

* Correction d’un problème qui affectait les mises à jour du statut du journal de diffusion sur l’instance MID, lorsque l’option FeatureFlag_GZIP_Compression était activée. (NEO-49183)
* Le workflow technique **Nettoyage de la base de données** gère désormais également les schémas d’évaluation personnalisés. (NEO-48974)
* Correction d’un problème en raison duquel les diffusions pouvaient garder le statut **En attente** même si la date de contact avait été atteinte. (NEO-48079, NEO-48251)
* Stabilité améliorée lors de la gestion des chaînes XML non valides lors des appels SOAP. (NEO-48027)
* Correction d’une erreur qui ralentissait l’analyse de la diffusion, lors de l’étape d&#39;exclusion des destinataires placés sur la liste bloquée, lors du ciblage d’un grand nombre de destinataires. (NEO-48019)
* Afin de prévenir tout problème de lenteur lors de l’envoi de BAT aux adresses de contrôle, toutes les réplications consécutives des membres des adresses de contrôle sont désormais regroupées dans une seule demande de réplication. (NEO-44844)
* Correction d’un problème qui entraînait des problèmes de personnalisation lors de l’envoi de SMS à l’aide d’un mode de diffusion externe. (NEO-46415)
* Correction d’un problème qui affichait un message d’erreur lors d’une tentative de prévisualisation d’une diffusion dans un événement archivé de Message Center. (NEO-43620)
* Correction d’un problème dans les workflows en raison duquel des fichiers sur le serveur ne pouvaient pas être mis à jour lors de l’utilisation de l’activité **Chargement de données (fichier)**. Le processus s’est arrêté à 100 % mais n’a jamais pris fin. (NEO-47269)
* Correction d’un problème qui entraînait la création de DeliveryParts superflus lorsque la diffusion utilisait les modes Calendrier et Partage. (NEO-48634)
* Correction d’un problème de performances lors de l’utilisation de vagues basées sur le calendrier. (NEO-48451)
* Correction d’un problème qui entraînait l’affichage d’un message d’erreur dans l’écran de la liste de diffusion après la création d’un nouveau mapping de ciblage sur un schéma personnalisé. (NEO-49237)
* Correction d’une erreur qui pouvait se produire si une diffusion atteignait une taille précise pendant le processus MTA. (NEO-46097)
* Correction d’un problème en raison duquel les logs de tracking ne pouvaient pas renvoyer de données liées au navigateur du destinataire. (NEO-46612)
* Correction d’un problème lors du postupgrade sur les environnements japonais. (NEO-46640)
* Correction d’un problème qui se produisait lors de l’utilisation de l’activité **Requête** et du filtrage d’un tableau. Lorsqu’un nom de colonne contenait les mots « Mise à jour », une erreur de compilation se produisait avec un identifiant non valide et le message suivant : « nombre de lignes mises à jour ». (NEO-46485)
* Correction d’un problème en raison duquel le workflow technique (ffdaReplicateStagingData) **[!UICONTROL Répliquer les données d’évaluation]** ne pouvait pas s’arrêter même si une erreur s’était produite lors de son exécution. (NEO-46280)
* Correction d’un problème qui entraînait une perte de données si le workflow d’évaluation était en erreur et que la période de conservation était complètement dépassée. (NEO-48975)
* Correction d’un problème en raison duquel, lors de l’injection de données dans la base de données cloud Snowflake avec une activité de **requête** de Campaign ainsi qu’une activité **Modifier la source de données**, le processus échouait si une barre oblique inverse était présente dans les données. La chaîne source n’a pas été placée dans une séquence d’échappement et les données n’ont pas été traitées correctement sur Snowflake. (NEO-45549)

## Version 8.3.8 {#release-8-3-8}

_18 mai 2022_

**Nouveautés**

<table> 
<thead>
<tr> 
<th> <strong>Notifications sensibles à l’heure</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Avec iOS 15, Apple a ajouté une notion de notification urgente qui permet au développeur de l’application de contourner le mode Focus lorsqu’une notification est considérée comme urgente et doit atteindre l’utilisateur en temps réel.</p>
<p>Pour plus d’informations, consultez la <a href="../send/push.md#send-notifications-on-ios">documentation détaillée</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead>
<tr> 
<th> <strong>Intégration de Privacy Core Service</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Campaign v8 s’intègre désormais à Adobe Privacy Core Service. Les demandes d'accès à des informations personnelles transmises par Privacy Core Service à toutes les solutions Experience Cloud sont automatiquement traitées par Campaign via un workflow dédié.</p>
<p>Pour plus d’informations, consultez la <a href="privacy.md">documentation détaillée</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table>
<thead>
<tr>
<th><strong>Gestion de la réaction</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>La gestion de la réaction des campagnes permet de mesurer le succès et le ROI de vos campagnes marketing ou de vos propositions d’offres sur tous les canaux : e-mail, mobile, courrier, etc.</p>
<p>Pour plus d’informations, consultez la <a href="../start/campaigns.md#response-manager-add-on">documentation détaillée</a>.</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>Distributed Marketing (Marketing distribué)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Le marketing distribué de Campaign permet de mettre en place des opérations collaboratives entre les entités centrales (siège social, services marketing, etc.) et les entités locales (points de vente, agences régionales, etc.). Depuis un espace de travail partagé (kits d'opération), vous pouvez créer des modèles d’opération et les proposer à vos entités locales.</p>
<p>Pour plus d’informations, consultez la <a href="../start/campaigns.md#distributed-marketing-add-on">documentation détaillée</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Mises à jour de compatibilité**

* Le SDK Campaign v8 prend maintenant en charge Android 12 et iOS 15 pour les notifications push.
* Campaign v8 est désormais compatible avec Windows 11.

Reportez-vous à la [matrice de compatibilité de Campaign](compatibility-matrix.md).

**Améliorations**

* L’authentification OAuth 2.0 de Microsoft Exchange Online pour POP3 est désormais prise en charge dans Campaign. [En savoir plus](../config/external-accounts.md#bounce-mails-external-account)
* Des correctifs importants ont été appliqués concernant l’API web du connecteur Microsoft Dynamics.
* Le nouveau droit nommé Opérateur et Écriture des schémas de groupe (operatorWrite) a été ajouté pour permettre aux utilisateurs d’insérer, de mettre à jour et de supprimer des schémas Opérateurs (xtk:operator) et Groupes d’opérateurs (xtk:group).

<!--* You can now enable the Email BCC (blind carbon copy) capability to store emails sent by Campaign at the delivery level, through the dedicated option in the delivery properties. [Read more](../config/email-settings.md#email-bcc)-->
<!--* To ensure better performances, a new "Split" option is now activated by default in the Routing external account. This option allows messages to be automatically split across your mid-sourcing instances in order to be delivered faster to the recipients.-->
* Plusieurs comptes actifs LINE peuvent désormais être paramétrés sur un seul mid-sourcing.
* Le nombre de connexions par défaut pour le processus web a été augmenté de 50 à 150.
* Campaign est fourni avec un ensemble de nouvelles barrières de sécurité pour empêcher l’insertion de clés dupliquées dans la base de données Snowflake. [En savoir plus](../architecture/keys.md)

**Correctifs**

* Correction d’un problème qui se produisait lors de l’utilisation d’adresses de contrôle et de populations témoins dans la même diffusion récurrente. (NEO-41197)
* Correction d’un problème sur FFDA en raison duquel l’envoi d’e-mails était bloqué pour tous les destinataires appartenant au même deliveryPart pendant le processus d’envoi (jusqu’à 256) lorsque les blocs de personnalisation contenaient l’un des caractères suivants : `' & < > "`. Ces caractères sont désormais pris en charge dans les blocs de personnalisation (par exemple : prénom=&quot;Brian O&#39;Neil&quot;). (NEO-43184)
* Correction d&#39;un problème qui pouvait mener à l’échec du workflow de facturation lors de l&#39;utilisation d&#39;un schéma personnalisé comme mapping de ciblage. Nous nous assurons désormais que le type du lien étranger vers un schéma de ciblage personnalisé est correct lors de la génération du schéma broadLog via l’assistant de mapping de ciblage. (NEO-43506)
* Correction d’un problème qui entraînait l’échec des workflows de déploiement FFDA pour des langues autres que l’anglais. (NEO-44561)

## Version 8.2.10 {#release-8-2-10}

_2 février 2022_

**Correctifs**

* Correction d’un problème qui entraînait lʼéchec de la préparation de la diffusion si le nombre maximal de messages, défini dans la règle de typologie, était atteint.
* Correction d’un problème lors de la configuration du connecteur Adobe Analytics lorsque l’adresse e-mail contenait un caractère « s ».
* Correction d’un problème lors du postupgrade qui entraînait une perte de données dans le tableau deliveryMapping à partir d’un mapping de diffusion personnalisé.
* Correction d’un problème en raison duquel les destinataires recevaient le même message plusieurs fois pour une même diffusion lorsque l’adresse e-mail contenait un guillemet simple (&#39;). Ce caractère est désormais placé dans une séquence d’échappement. (NEO-41198)
* Correction d’un problème de génération d’ID lors de l’envoi de BAT avec des adresses de contrôle ou de substitution. (NEO-42637)
* Correction d’un problème qui empêchait l’envoi de BAT à l’aide de la méthode de substitution d’adresse. (NEO-40417)
* Correction dʼune erreur qui vous empêchait dʼinstaller le package LINE. (NEO-42503)

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
<p>Comme Cloud Database n’applique pas les contraintes d’unicité, Unicity Service introduit au niveau de l’application, <b>un ensemble de nouvelles barrières de sécurité</b> qui réduisent le risque d’insertion de doublons lors de la gestion des données avec Adobe Campaign.</p> 
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
