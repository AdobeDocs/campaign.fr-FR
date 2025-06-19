---
title: Notes de mise à jour de Campaign v8 2022
description: Liste des fonctionnalités et améliorations des versions 2022 de Campaign v8.
feature: Release Notes
exl-id: 76473fa5-48ba-42cf-8664-0dd197833a86
source-git-commit: b3ca222fb28c1a5d35190e41cfbbe463c5d1bcad
workflow-type: ht
source-wordcount: '1949'
ht-degree: 100%

---

# Notes de mise à jour 2022{#2022-rn}

Cette page répertorie les nouvelles fonctionnalités, les améliorations et les correctifs des **versions 2022 de Campaign v8**.

>[!BEGINSHADEBOX]

**Dans cette page**

* Campaign v8.4 - [Version 8.4.1](#release-8-4-1) | [Version 8.4.2](#release-8-4-2)
* Campaign v8.3 - [version 8.3.8](#release-8-3-8) | [Version 8.3.9](#release-8-3-9)
* Campaign v8.2 - [version 8.2.10](#release-8-2-10)

>[!ENDSHADEBOX]



## Version 8.4.2 {#release-8-4-2}

_28 octobre 2022_

**Correctifs**

* Correction d’un problème qui empêchait la mise à jour correcte de l’indicateur de diffusion de succès lors de l’utilisation du MTA amélioré d’Adobe Campaign. (NEO-50462)

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
<th> <strong>Disponibilité du canal X (anciennement Twitter)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Le <a href="../send/twitter.md">canal social X</a> est désormais disponible avec Campaign v8. Vous pouvez ainsi effectuer les actions suivantes :</p>
<ul> 
<li><p>Envoyer des messages sur X (anciennement Twitter) : Adobe Campaign vous permet de publier des messages directement sur votre compte X. Vous pouvez également envoyer des messages directs à tous les abonnées et abonnés de vos comptes.
</p></li>
<li><p>Collecter de nouveaux contacts : Adobe Campaign peut récupérer automatiquement les données de profil, ce qui vous permet ainsi d’exécuter des campagnes de ciblage et, lorsque cela est possible, d’implémenter des stratégies cross-canal.
</p></li>
</ul>
<p>Découvrez comment connecter Campaign et X dans la <a href="../connect/ac-tw.md">documentation détaillée</a>.</p>
<p>Découvrez comment créer des publications et envoyer des messages directs avec Campaign sur <a href="../connect/ac-tw.md">cette page</a>.</p>
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
* Correction d’un problème en raison duquel les logs de tracking ne pouvaient pas renvoyer de données liées au navigateur du ou de la destinataire. (NEO-46612)
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

**Correctifs**

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
* Correction d’un problème en raison duquel les logs de tracking ne pouvaient pas renvoyer de données liées au navigateur du ou de la destinataire. (NEO-46612)
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
<td> <p>Le marketing distribué de Campaign vous permet d’implémenter des campagnes collaboratives entre entités centrales (sièges sociaux, services marketing, etc.) et entités locales (magasins, agences régionales, etc.). Depuis un espace de travail partagé (kits d'opération), vous pouvez créer des modèles d’opération et les proposer à vos entités locales.</p>
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
* Campaign est fourni avec un ensemble de nouveaux mécanismes de sécurisation pour empêcher l’insertion de clés dupliquées dans la base de données Snowflake. [En savoir plus](../architecture/keys.md)

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
