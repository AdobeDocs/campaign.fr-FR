---
title: Notes de mise à jour de Campaign v8
description: Dernière version de Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 4e52e596d4eb2a8e1a1799fcd7104dcd894b6c2d
workflow-type: ht
source-wordcount: '931'
ht-degree: 100%

---

# Dernières versions {#latest-release}

Adobe Campaign fait l&#39;objet de mises à jour régulières. Cette fréquence régulière de mise à jour a pour but de vous fournir les dernières fonctionnalités et améliorations. Vous bénéficiez ainsi d&#39;un environnement sécurisé et d&#39;une expérience optimale avec notre produit. Adobe recommande vivement à toute sa clientèle d’effectuer la mise à niveau vers la dernière version. Cette page répertorie les nouvelles fonctionnalités, les améliorations et les correctifs des dernières versions de Campaign v8 (console). Pour en savoir plus sur les versions et les mises à jour de Campaign, consultez [cette page](upgrades.md).

En tant qu’utilisateur ou utilisatrice de Managed Cloud Services, votre instance est mise à niveau par Adobe avec chaque nouvelle version. Adobe vous contactera et mettra à niveau vos environnements. La console cliente Campaign **doit être mise à niveau vers la même version** que les serveurs Campaign. Découvrez comment mettre à niveau votre console cliente sur [cette page](../start/connect.md#upgrade-ac-console).

En outre, en tant que client ou cliente, assurez-vous d’utiliser les dernières versions prises en charge des systèmes répertoriés dans la [matrice de compatibilité](compatibility-matrix.md).

## Version 8.6.3 {#release-8-6-3}

_30 juillet 2024_

### Nouvelles fonctionnalités {#new-8-6-3}

* **Notification push enrichie** : vous pouvez désormais envoyer des notifications push enrichies. La notification push enrichie est une forme améliorée de notification mobile qui va au-delà des messages texte simples en incorporant des éléments multimédias tels que des images, des boutons interactifs ou d’autres contenus multimédias enrichis. Avec cette version, un ensemble de modèles pour les notifications push enrichies est désormais disponible pour vos applications iOS et Android. [En savoir plus](../send/rich-push-android.md).

* À compter de cette version, les informations d’identification du compte de service (JWT) étant abandonnées par Adobe, les intégrations sortantes de Campaign aux solutions et applications d’Adobe dépendent désormais des informations d’identification OAuth serveur à serveur. [En savoir plus](release-notes.md#change-8-7-1)

### Améliorations générales {#improvements-8-6-3}

* Pour accroître la sécurité de toutes les communications entre les applications, mTLS est désormais pris en charge pour les appels API externes.

### Correctifs {#fixes-8-6-3}

Les problèmes suivants ont été corrigés dans cette version :

NEO-79328, NEO-78843, NEO-77795, NEO-77014, NEO-76958, NEO-76097, NEO-75898, NEO-72504, NEO-70263, NEO-67620, NEO-63197, NEO-58596, NEO-56832.

<!--
https://jira.corp.adobe.com/issues/?filter=585288&jql=fixVersion%20%3D%208.6.3%20AND%20type%20not%20in%20(epic%2C%20test%2C%20sub-task%2C%20Roadmap)%20AND%20resolution%20!%3D%20unresolved%20AND%20%22Fixed%20in%20Build%22%20is%20not%20EMPTY%20and%20type%20in%20(%22customer%20request%22)
-->


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
>Si vous êtes un utilisateur ou une utilisatrice de Campaign Standard et que vous passez à Campaign v8, apprenez-en plus sur cette transition dans la [documentation sur l’interface d’utilisation d’Adobe Campaign Web v8](https://experienceleague.adobe.com/fr/docs/campaign-web/v8/release-notes/acs-migration){target="_blank"}.

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
