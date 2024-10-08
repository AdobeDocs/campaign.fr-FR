---
title: Notes de mise à jour de Campaign v8 (console) 2023
description: Liste des fonctionnalités et améliorations des versions 2023 de Campaign v8.
feature: Release Notes
exl-id: 6a0a9486-19a9-4ec3-9030-48dbf419f45f
source-git-commit: fb7abba9009591a2757c07f584c0a7c59c6eb01a
workflow-type: ht
source-wordcount: '1016'
ht-degree: 100%

---

# Notes de mise à jour 2024 {#2024-rn}

Cette page répertorie les nouvelles fonctionnalités, les améliorations et les correctifs des **versions 2024 de Campaign v8**.



## Version 8.5.3 {#release-8-5-3}

_28 mai 2024_

### Migration vers les informations d’identification OAuth serveur à serveur {#change-8-5-3}

À compter de cette version, les informations d’identification du compte de service (JWT) étant abandonnées par Adobe, les intégrations sortantes de Campaign aux solutions et applications d’Adobe dépendent désormais des informations d’identification OAuth serveur à serveur. [En savoir plus](#change-8-7-1)

### Correctifs {#fixes-8-5-3}

Les problèmes suivants ont été corrigés dans cette version :

NEO-70263, NEO-64984, NEO-63657, NEO-63387, NEO-62964, NEO-62750, NEO-62686, NEO-59544, NEO-52542


## Mises à jour de mai {#may-updates}

La modification suivante a été publiée en mai et est désormais disponible pour les utilisateurs et utilisatrices de Campaign v8 :

* **Nouveau module complémentaire de sécurité améliorée** : pour sécuriser votre connexion réseau et améliorer la sécurité de vos ressources, Adobe Campaign propose un nouveau module complémentaire de sécurité améliorée qui comprend deux fonctionnalités : l’intégration CMK sécurisée et la tunnellisation VPN sécurisée. [En savoir plus](../config/enhanced-security.md)


## Version 8.7.1 {#release-8-7-1}

_2 mai 2024_

>[!AVAILABILITY]
>
>Cette version est en **disponibilité limitée** (LA). Elle est limitée aux personnes effectuant la migration **depuis Adobe Campaign Standard vers Adobe Campaign v8** et ne peut pas être déployée dans un autre environnement.
>
>Si vous êtes un utilisateur ou une utilisatrice de Campaign Standard et que vous passez à Campaign v8, apprenez-en plus sur cette transition dans la [documentation sur l’interface d’utilisation d’Adobe Campaign Web v8](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/start/acs-migration){target="_blank"}.

### Nouvelles fonctionnalités {#new-8-7-1}

* **Modèles de notification push enrichis** : vous pouvez désormais envoyer des notifications push enrichies via Android. La notification push enrichie est une forme améliorée de notification mobile qui va au-delà des messages texte simples en incorporant des éléments multimédias tels que des images, des boutons interactifs ou d’autres contenus multimédias enrichis. [En savoir plus](../send/rich-push-ios.md).

* **Branding** : en tant qu’utilisateur ou utilisatrice ayant effectué la migration depuis Campaign Standard, votre administration technique peut désormais définir une ou plusieurs marques afin de centraliser les paramètres qui affectent leur identité. Par exemple : le logo de la marque, le domaine d’URL d’accès aux pages de destination ainsi que les paramètres du tracking des messages. Vous pouvez créer ces marques et les associer à des messages ou à des pages de destination. Cette configuration est gérée dans des modèles. [En savoir plus](https://experienceleague.adobe.com/docs/experience-cloud/campaign/branding/branding-gs.html?lang=fr){target="_blank"}

* **API REST** : en tant qu’utilisateur ou utilisatrice ayant effectué la migration depuis Campaign Standard, vous pouvez utiliser les API REST pour créer des intégrations pour Adobe Campaign et créer votre propre réseau en interfaçant Adobe Campaign avec le panneau de technologies que vous utilisez. [En savoir plus](https://experienceleague.adobe.com/docs/experience-cloud/campaign/apis/get-started-apis.html?lang=fr){target="_blank"}

* **Rapports dynamiques** : en tant qu’utilisateur ou utilisatrice ayant effectué la migration depuis Campaign Standard, vous pouvez accéder aux rapports dynamiques qui fournissent des rapports entièrement personnalisables en temps réel pour mesurer l’impact de vos activités marketing. Ils offrent la possibilité d’accéder aux données de profil, ce qui permet l’analyse démographique par dimensions de profil, telles que le genre, la ville et l’âge, en plus des données de campagne par e-mail fonctionnelles comme les ouvertures et les clics. [En savoir plus](https://experienceleague.adobe.com/docs/experience-cloud/campaign/reporting/get-started-reporting.html?lang=fr){target="_blank"}

### Mises à jour de compatibilité {#comp-8-7-1}

* Databricks est désormais pris en charge en tant que base de données externe avec Adobe Campaign Federated Data Access (FDA). En savoir plus [sur cette page](compatibility-matrix.md#FederatedDataAccessFDA).

### Migration vers les informations d’identification OAuth serveur à serveur {#change-8-7-1}

À compter de cette version, les informations d’identification du compte de service (JWT) étant abandonnées par Adobe, les intégrations sortantes de Campaign aux solutions et applications d’Adobe dépendent désormais des informations d’identification OAuth serveur à serveur. Adobe effectuera la migration JWT vers OAuth pour vos intégrations sortantes, telles que l’intégration Campaign-Analytics ou Triggers Experience Cloud.

Si vous avez implémenté des intégrations entrantes avec Campaign, vous devez migrer votre compte technique comme décrit dans [cette documentation](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. Les informations d’identification de compte de service (JWT) existantes continueront à fonctionner jusqu’au **27 janvier 2025**.

### Améliorations générales {#improvements-8-7-1}

* Plusieurs schémas ont été modifiés de 32 à 64 bits. Cela s’applique uniquement aux clientes et clients effectuant la migration depuis Campaign Standard. [En savoir plus](https://experienceleague.adobe.com/docs/experience-cloud/campaign/technotes/64-bit-tables.html?lang=fr){target="_blank"}

* Dans les tableaux Campaign, les attributs suivants sont désormais renseignés par défaut par la date et l’heure du serveur : `lastModified` et `created`. La valeur d’attribut `createdBy-id` est désormais renseignée par défaut avec l’identifiant de connexion actuel. Les valeurs fournies par les utilisateurs et les utilisatrices dans les appels API sont ignorées. <!--This configuration can be changed in the Campaign server configuration file. As a Managed Cloud Services customer, you must reach out to Adobe to change this default configuration.-->

* Pour accroître la sécurité de toutes les communications entre les applications, mTLS est désormais pris en charge pour les appels API externes.

### Correctifs {#fixes-8-7-1}

Les problèmes suivants ont été corrigés dans cette version :

NEO-72648, NEO-71534, NEO-71473, NEO-70263, NEO-70195, NEO-69651, NEO-68704, NEO-68192, NEO-67814, NEO-67702, NEO-67620, NEO-66022, NEO-65774, NEO-65633, NEO-64199, NEO-63706, NEO-63705, NEO-63287, NEO-63197, NEO-62575, NEO-60250, NEO-60192, NEO-58596, NEO-58314, NEO-58004, NEO-40054


## Version 8.6.2 {#release-8-6-2}

_23 février 2024_

### Correctifs {#fixes-8-6-2}

Cette version corrige le problème suivant :

* Correction d’un problème de performances qui pouvait se produire sur l’instance de midsourcing (NEO-72595).

## Version 8.6.1 {#release-8-6-1}

_14 février 2024_

### Nouveautés {#new-8-6-1}

* À compter de cette version, vous avez accès à la nouvelle **interface utilisateur web de Campaign**, disponible via l’environnement central Adobe Experience Cloud. Experience Cloud est la famille intégrée d’applications, de produits et de services de marketing numérique d’Adobe. Grâce à son interface intuitive, vous pouvez accéder rapidement à vos applications cloud, fonctionnalités de produit et services. Découvrez comment vous connecter à Adobe Experience Cloud et accéder à l’interface d’Adobe Campaign Web [dans cette page](campaign-ui.md#ac-web-ui).


* Adobe Campaign v8 s’intègre désormais à **Adobe Experience Manager as a Cloud Service**, la création étant exclusivement possible via l’interface utilisateur web d’Adobe Campaign. [En savoir plus](../connect/ac-aem.md)

* Vous pouvez désormais utiliser votre **bibliothèque Adobe Experience Manager Assets** avec vos Experience Cloud Assets même si le package Intégration avec Adobe Experience Cloud est installé sur votre instance Adobe Campaign. [En savoir plus](../connect/ac-aem.md#assets-library)

### Améliorations générales {#improvements-8-6-1}

* Campaign v8.6 améliore le débit des **indicateurs de tracking des diffusions par e-mail**. Grâce à nos processus optimisés, le suivi de l’ingestion et le temps de calcul sont réduits, et vous pouvez vérifier beaucoup plus rapidement vos indicateurs clés de diffusion.


### Mises à jour de la délivrabilité {#deliverability-8-6-1}

* D’ici février 2024, toute société qui envoie plus de 5 000 e-mails via Google ou Yahoo! devra commencer à utiliser une technologie d’authentification appelée DMARC (Domain-based Message Authentication Reporting and Conformance). Assurez-vous que l’enregistrement DMARC est configuré pour tous les sous-domaines que vous utilisez avec Adobe Campaign. [En savoir plus](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=fr){target="_blank"}

* À compter du 1er juin 2024, Google et Yahoo! exigeront que les expéditeurs et expéditrices se conforment à List-Unsubscribe en un clic. Adobe Campaign prend désormais en charge cette option. [En savoir plus](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html?lang=fr#one-click-list-unsubscribe){target="_blank"}


### Correctifs {#fixes-8-6-1}

Les problèmes suivants ont été corrigés dans cette version :

NEO-67892, NEO-67235, NEO-66797, NEO-66462, NEO-65091, NEO-65036, NEO-64984, NEO-64680, NEO-63973, NEO-63879, NEO-63815, NEO-63657, NEO-63539, NEO-63387, NEO-63294, NEO-63174, NEO-62964, NEO-62750, NEO-62686, NEO-62455, NEO-62406, NEO-61580, NEO-61199, NEO-60786, NEO-59544, NEO-59198, NEO-59059, NEO-58637, NEO-55197, NEO-52542, NEO-50488, NEO-47789
