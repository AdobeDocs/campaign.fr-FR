---
title: Notes de mise à jour de Campaign v8 (console) 2024
description: Liste des fonctionnalités et améliorations des versions 2024 de Campaign v8
feature: Release Notes
exl-id: 6a0a9486-19a9-4ec3-9030-48dbf419f45f
source-git-commit: b52308bcbe68a7c382918fe28f8166e3bfcb6cde
workflow-type: tm+mt
source-wordcount: '1568'
ht-degree: 97%

---

# Notes de mise à jour 2024 {#2024-rn}

Cette page répertorie les nouvelles fonctionnalités, les améliorations et les correctifs des **versions 2024 de Campaign v8**. Pour connaître la version la plus récente, consultez [cette page](release-notes.md).

Pour toute nouvelle implémentation ou mise à niveau vers un environnement existant, installez [la dernière version](release-notes.md).


>[!BEGINSHADEBOX]

**Dans cette page**

* Campaign v8.7 - [Version 8.7.1](#release-8-7-1) | [Version 8.7.2](#release-8-7-2)
* Campaign v8.6 - [Version 8.6.1](#release-8-6-1) | [Version 8.6.2](#release-8-6-2) | [Version 8.6.3](#release-8-6-3)
* Campaign v8.5 - [Version 8.5.3](#release-8-5-3)

>[!ENDSHADEBOX]

## Version 8.7.2 {#release-8-7-2}

_3 septembre 2024_

>[!AVAILABILITY]
>
>Cette version est en **disponibilité limitée** (LA). Elle est limitée aux personnes effectuant la migration **depuis Adobe Campaign Standard vers Adobe Campaign v8** et ne peut pas être déployée dans un autre environnement.
>
>Si vous êtes un utilisateur ou une utilisatrice de Campaign Standard et que vous passez à Campaign v8, apprenez-en plus sur cette transition dans la [documentation sur l’interface d’utilisation d’Adobe Campaign Web v8](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nouvelles fonctionnalités {#new-8-7-2}

* **Nouveau connecteur d’envoi de SMS** : le connecteur d’envoi de SMS a été modernisé et amélioré afin d’activer les connexions SMPP en mode émetteur-récepteur, d’activer les connexions SMPP persistantes et d’assurer une meilleure compatibilité pour les environnements en transition depuis Adobe Campaign Standard. Un nouveau compte externe SMS est désormais disponible pour toutes les nouvelles implémentations SMS. L’implémentation existante est toujours prise en charge, mais il est recommandé de passer au nouveau connecteur moderne et étendu. [En savoir plus](../send/sms/sms.md).

* **Modèles de notification push enrichis (disponibilité générale)** : vous pouvez désormais envoyer des notifications push enrichies via Android. La notification push enrichie est une forme améliorée de notification mobile qui va au-delà des messages texte simples en incorporant des éléments multimédias tels que des images, des boutons interactifs ou d’autres contenus multimédias enrichis. Avec cette version, un ensemble de modèles pour les notifications push enrichies est désormais disponible pour vos applications iOS et Android. [En savoir plus](../send/rich-push-android.md).

* **Branding** : les options de branding sont désormais disponibles pour tous les canaux, y compris les SMS et les courriers. [En savoir plus](https://experienceleague.adobe.com/docs/campaign-web/v8/conf/branding/branding-gs.html){target="_blank"}

### Correctifs {#fixes-8-7-2}

Les problèmes suivants ont été corrigés dans cette version :

NEO-48232, NEO-56832, NEO-72504, NEO-74855, NEO-75898, NEO-76097, NEO-76958, NEO-77014, NEO-77795, NEO-78843, NEO-79328.

## Version 8.7.1 {#release-8-7-1}

_2 mai 2024_

>[!AVAILABILITY]
>
>Cette version est en **disponibilité limitée** (LA). Elle est limitée aux personnes effectuant la migration **depuis Adobe Campaign Standard vers Adobe Campaign v8** et ne peut pas être déployée dans un autre environnement.
>
>Si vous êtes un utilisateur ou une utilisatrice de Campaign Standard et que vous passez à Campaign v8, apprenez-en plus sur cette transition dans la [documentation sur l’interface d’utilisation d’Adobe Campaign Web v8](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nouvelles fonctionnalités {#new-8-7-1}

* **Modèles de notification push enrichis** : vous pouvez désormais envoyer des notifications push enrichies via Android. La notification push enrichie est une forme améliorée de notification mobile qui va au-delà des messages texte simples en incorporant des éléments multimédias tels que des images, des boutons interactifs ou d’autres contenus multimédias enrichis. [En savoir plus](../send/rich-push-ios.md).

* **Branding** : en tant qu’utilisateur ou utilisatrice ayant effectué la migration depuis Campaign Standard, votre administration technique peut désormais définir une ou plusieurs marques afin de centraliser les paramètres qui affectent leur identité. Par exemple : le logo de la marque, le domaine d’URL d’accès aux pages de destination ainsi que les paramètres du tracking des messages. Vous pouvez créer ces marques et les associer à des messages ou à des pages de destination. Cette configuration est gérée dans des modèles. [En savoir plus](https://experienceleague.adobe.com/docs/campaign-web/v8/conf/branding/branding-gs.html){target="_blank"}

* **API REST** : en tant qu’utilisateur ou utilisatrice ayant effectué la migration depuis Campaign Standard, vous pouvez utiliser les API REST pour créer des intégrations pour Adobe Campaign et créer votre propre réseau en interfaçant Adobe Campaign avec le panneau de technologies que vous utilisez. [En savoir plus](../dev/api/get-started-apis.md)

* **Rapports dynamiques** : en tant qu’utilisateur ou utilisatrice ayant effectué la migration depuis Campaign Standard, vous pouvez accéder aux rapports dynamiques qui fournissent des rapports entièrement personnalisables en temps réel pour mesurer l’impact de vos activités marketing. Ils offrent la possibilité d’accéder aux données de profil, ce qui permet l’analyse démographique par dimensions de profil, telles que le genre, la ville et l’âge, en plus des données de campagne par e-mail fonctionnelles comme les ouvertures et les clics. [En savoir plus](https://experienceleague.adobe.com/docs/campaign-web/v8/reports/dynamic-reporting/get-started-reporting.html){target="_blank"}

### Mises à jour de compatibilité {#comp-8-7-1}

Les connecteurs FDA suivants ont été ajoutés. Consultez cette [page](compatibility-matrix.md#FederatedDataAccessFDA).

* Databricks est désormais pris en charge en tant que base de données externe avec Adobe Campaign Federated Data Access (FDA).

* Un nouveau connecteur ODBC FDA Amazon Redshift est désormais disponible. Il offre une connectivité améliorée, une maintenance plus facile et une meilleure compatibilité. Cette nouvelle version apporte les améliorations suivantes :

   * Le nouveau connecteur repose sur l’interface ODBC qui s’aligne sur nos connecteurs FDA les plus récents. Cela garantit une prise en charge à long terme.
   * Il introduit également un nouveau mécanisme de chargement de données à l’aide de compartiments s3, ce qui améliore considérablement les performances.

  Le connecteur hérité peut toujours être utilisé. Si vous souhaitez tester la nouvelle version, contactez votre représentant ou représentante Adobe.

### Migration vers les informations d’identification OAuth serveur à serveur {#change-8-7-1}

À compter de cette version, les informations d’identification du compte de service (JWT) étant abandonnées par Adobe, les intégrations sortantes de Campaign aux solutions et applications d’Adobe dépendent désormais des informations d’identification OAuth serveur à serveur. Adobe effectuera la migration JWT vers OAuth pour vos intégrations sortantes, telles que l’intégration Campaign-Analytics ou Triggers Experience Cloud.

Si vous avez implémenté des intégrations entrantes pour Campaign, vous devez migrer votre compte technique comme décrit dans [cette documentation](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. Les informations d’identification de compte de service (JWT) existantes continueront à fonctionner jusqu’au **30 juin 2025**.

### Améliorations générales {#improvements-8-7-1}

* Plusieurs schémas ont été modifiés de 32 à 64 bits. Cela s’applique uniquement aux clientes et clients effectuant la migration depuis Campaign Standard. [En savoir plus](https://experienceleague.adobe.com/docs/experience-cloud/campaign/technotes/64-bit-tables.html?lang=fr){target="_blank"}

* Dans les tableaux Campaign, les attributs suivants sont désormais renseignés par défaut par la date et l’heure du serveur : `lastModified` et `created`. La valeur d’attribut `createdBy-id` est désormais renseignée par défaut avec l’identifiant de connexion actuel. Les valeurs fournies par les utilisateurs et les utilisatrices dans les appels API sont ignorées. <!--This configuration can be changed in the Campaign server configuration file. As a Managed Cloud Services customer, you must reach out to Adobe to change this default configuration.-->

* Pour accroître la sécurité de toutes les communications entre les applications, mTLS est désormais pris en charge pour les appels API externes.

### Correctifs {#fixes-8-7-1}

Les problèmes suivants ont été corrigés dans cette version :

NEO-72648, NEO-71534, NEO-71473, NEO-70263, NEO-70195, NEO-69651, NEO-68704, NEO-68192, NEO-67814, NEO-67702, NEO-67620, NEO-66022, NEO-65774, NEO-65633, NEO-64199, NEO-63706, NEO-63705, NEO-63287, NEO-63197, NEO-62575, NEO-60250, NEO-60192, NEO-58596, NEO-58314, NEO-58004, NEO-40054



## Version 8.6.3 {#release-8-6-3}

_30 juillet 2024_

### Nouvelles fonctionnalités {#new-8-6-3}

* **Notification push enrichie** : vous pouvez désormais envoyer des notifications push enrichies. La notification push enrichie est une forme améliorée de notification mobile qui va au-delà des messages texte simples en incorporant des éléments multimédias tels que des images, des boutons interactifs ou d’autres contenus multimédias enrichis. Avec cette version, un ensemble de modèles pour les notifications push enrichies est désormais disponible pour vos applications iOS et Android. [En savoir plus](../send/rich-push-android.md).

* À compter de cette version, les informations d’identification du compte de service (JWT) étant abandonnées par Adobe, les intégrations sortantes de Campaign aux solutions et applications d’Adobe dépendent désormais des informations d’identification OAuth serveur à serveur. [En savoir plus](release-notes-2024.md#change-8-7-1)

### Améliorations générales {#improvements-8-6-3}

* Pour accroître la sécurité de toutes les communications entre les applications, mTLS est désormais pris en charge pour les appels API externes.

### Correctifs {#fixes-8-6-3}

Les problèmes suivants ont été corrigés dans cette version :

NEO-79328, NEO-78843, NEO-77795, NEO-77014, NEO-76958, NEO-76097, NEO-75898, NEO-72504, NEO-70263, NEO-67620, NEO-63197, NEO-58596, NEO-56832.

<!--
https://jira.corp.adobe.com/issues/?filter=585288&jql=fixVersion%20%3D%208.6.3%20AND%20type%20not%20in%20(epic%2C%20test%2C%20sub-task%2C%20Roadmap)%20AND%20resolution%20!%3D%20unresolved%20AND%20%22Fixed%20in%20Build%22%20is%20not%20EMPTY%20and%20type%20in%20(%22customer%20request%22)
-->


## Mises à jour de mai 2024 {#may-updates}

La modification suivante a été publiée en mai et est désormais disponible pour les utilisateurs et utilisatrices de Campaign v8 :

* **Nouveau module complémentaire de sécurité améliorée** : pour sécuriser votre connexion réseau et améliorer la sécurité de vos ressources, Adobe Campaign propose un nouveau module complémentaire de sécurité améliorée qui comprend deux fonctionnalités : l’intégration CMK sécurisée et la tunnellisation VPN sécurisée. [En savoir plus](../config/enhanced-security.md)

## Version 8.6.2 {#release-8-6-2}

_23 février 2024_

### Correctifs {#fixes-8-6-2}

Cette version corrige le problème suivant :

* Correction d’un problème de performances qui pouvait se produire sur l’instance de midsourcing (NEO-72595).

## Version 8.6.1 {#release-8-6-1}

_14 février 2024_

### Nouvelles fonctionnalités {#new-8-6-1}

* À compter de cette version, vous avez accès à la nouvelle **interface utilisateur web de Campaign**, disponible via l’environnement central Adobe Experience Cloud. Experience Cloud est la famille intégrée d’applications, de produits et de services de marketing numérique d’Adobe. Grâce à son interface intuitive, vous pouvez accéder rapidement à vos applications cloud, fonctionnalités de produit et services. Découvrez comment vous connecter à Adobe Experience Cloud et accéder à l’interface d’Adobe Campaign Web [dans cette page](campaign-ui.md#ac-web-ui).

  >[!AVAILABILITY]
  >
  >L’interface d’utilisation de Campaign Web n’est disponible que pour les utilisateurs et utilisatrices qui se connectent à Adobe Campaign avec leur Adobe ID. En savoir plus sur [Adobe Identity Management System (IMS)](https://helpx.adobe.com/fr/enterprise/using/identity.html){target="_blank"}.
  >

* Adobe Campaign v8 s’intègre désormais à **Adobe Experience Manager as a Cloud Service**, la création étant exclusivement possible via l’interface utilisateur web d’Adobe Campaign. [En savoir plus](../connect/ac-aem.md)

* Vous pouvez désormais utiliser votre **bibliothèque Adobe Experience Manager Assets** avec vos Experience Cloud Assets même si le package Intégration avec Adobe Experience Cloud est installé sur votre instance Adobe Campaign. [En savoir plus](../connect/ac-aem.md#assets-library)

### Améliorations générales {#improvements-8-6-1}

* Campaign v8.6 améliore le débit des **indicateurs de tracking des diffusions par e-mail**. Grâce à nos processus optimisés, le suivi de l’ingestion et le temps de calcul sont réduits, et vous pouvez vérifier beaucoup plus rapidement vos indicateurs clés de diffusion.


### Mises à jour de la délivrabilité {#deliverability-8-6-1}

* D’ici février 2024, toute société qui envoie plus de 5 000 e-mails via Google ou Yahoo! devra commencer à utiliser une technologie d’authentification appelée DMARC (Domain-based Message Authentication Reporting and Conformance). Assurez-vous que l’enregistrement DMARC est configuré pour tous les sous-domaines que vous utilisez avec Adobe Campaign. [En savoir plus](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=fr){target="_blank"}

* À compter du 1er juin 2024, Google et Yahoo! exigeront que les expéditeurs et expéditrices se conforment à List-Unsubscribe en un clic. Adobe Campaign prend désormais en charge cette option. [En savoir plus](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html?lang=fr#list-unsubscribe){target="_blank"}


### Correctifs {#fixes-8-6-1}

Les problèmes suivants ont été corrigés dans cette version :

NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973, NEO-63879, NEO-63815, NEO-63657, NEO-63539, NEO-63387, NEO-63294, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-62406, NEO-61580, NEO-61199, NEO-60786, NEO-59544, NEO-59198, NEO-59059, NEO-58637, NEO-55197, NEO-52542, NEO-50488, NEO-47789



## Version 8.5.3 {#release-8-5-3}

_28 mai 2024_

### Migration vers les informations d’identification OAuth serveur à serveur {#change-8-5-3}

À compter de cette version, les informations d’identification du compte de service (JWT) étant abandonnées par Adobe, les intégrations sortantes de Campaign aux solutions et applications d’Adobe dépendent désormais des informations d’identification OAuth serveur à serveur. [En savoir plus](#change-8-7-1)

### Correctifs {#fixes-8-5-3}

Les problèmes suivants ont été corrigés dans cette version :

NEO-70263, NEO-64984, NEO-63657, NEO-63387, NEO-62964, NEO-62750, NEO-62686, NEO-59544, NEO-52542