---
title: Campaign Classic v7 - Matrice des fonctionnalités Campaign v8
description: Comprendre les différences entre Campaign Classic v7 et Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62,7105477f-d29e-4af8-8789-82b4459761b0
source-git-commit: 8668970b0270b990232b78d527d0713efd9d1a4d
workflow-type: ht
source-wordcount: '940'
ht-degree: 100%

---

# [!DNL Campaign Classic]Fonctionnalités v7 -[!DNL Campaign] v8{#gs-matrix}

En tant qu&#39;utilisateur existant de [!DNL Campaign Classic] v7, votre manière habituelle d&#39;interagir avec [!DNL Adobe Campaign] ne devrait pas subir de perturbations importantes. La plupart des modifications apportées à v8 ne sont pas visibles, à l&#39;exception des petites modifications qui apparaissent dans l&#39;interface utilisateur et dans les étapes de configuration.

Modifications clés :

* Création de segments jusqu&#39;à 200 fois plus rapide
* Augmentation de la vitesse de diffusion
* Reporting en temps réel       avec Cubes

En tant qu&#39;utilisateur [!DNL Campaign Classic], veuillez noter que la plupart des fonctionnalités de [!DNL Campaign Classic] v7 sont disponibles dans [!DNL Campaign] v8, à l&#39;exception d&#39;un petit ensemble de fonctionnalités répertoriées dans [cette section](#gs-removed). Les prochaines versions proposeront d&#39;autres fonctionnalités. [En savoir plus dans cette section](#gs-unavailable-features)

?? Pour en savoir plus sur l&#39;architecture de [!DNL Campaign] v8, consultez [cette page](../dev/architecture.md).

## Modifications de la configuration des produits

### [!DNL Campaign] et [!DNL Snowflake] {#ac-gs-snowflake}

[!DNL Adobe Campaign] v8 fonctionne avec deux bases de données : une base de données locale pour la messagerie en temps réel et les requêtes unitaires de l&#39;interface utilisateur à travers les API, et une base de données Cloud pour l&#39;exécution de campagnes, les requêtes par lots et l&#39;exécution de workflows.

Il s&#39;agit d&#39;une modification fondamentale de l&#39;architecture logicielle. Les données sont désormais distantes et Campaign fédère l&#39;intégralité d&#39;entre elles, y compris les profils. Les processus [!DNL Campaign] évoluent désormais de bout en bout, du ciblage à l&#39;exécution des messages : l&#39;ingestion des données, la segmentation, le ciblage, les requêtes et les diffusions s&#39;exécutent désormais en quelques minutes. Cette nouvelle version résout le défi de la mise à l&#39;échelle tout en conservant le même niveau de flexibilité et d&#39;extensibilité. Le nombre de profils est presque illimité et la rétention des données peut être étendue.

Le stockage dans le cloud est effectué dans **[!DNL Snowflake]** : un nouveau **compte externe** natif assure la connectivité avec la base de données dans le cloud. Il est configuré par Adobe et ne doit pas être modifié. [En savoir plus](../config/external-accounts.md)

Tout schéma prédéfini ou toute table intégrée devant être déplacé ou répliqué dans la base de données du cloud est fourni avec une extension de schéma intégrée sous l&#39;espace de noms **xxl**. Ces extensions contiennent toutes les modifications nécessaires au déplacement des schémas natifs depuis la base de données [!DNL Campaign] locale vers la base de données [!DNL Snowflake] dans le cloud et à l&#39;adaptation de leur structure en conséquence : nouvel UUID, liens mis à jour, etc.

>[!CAUTION]
>
> Les données client ne sont pas stockées dans la base de données [!DNL Campaign] locale. Par conséquent, toute table personnalisée doit être créée dans la base de données cloud.

Des API spécifiques sont disponibles pour gérer les données entre la base de données locale et la base de données cloud. Découvrez le fonctionnement de ces nouvelles API et comment les utiliser sur [cette page](../dev/new-apis.md).

### Réplication des données

Un workflow technique spécifique gère la réplication des tables qui doivent être présentes des deux côtés (base de données locale de Campaign et base de données dans le cloud). Ce workflow est déclenché toutes les heures et repose sur une nouvelle bibliothèque JavaScript intégrée.

>[!NOTE]
>
> Plusieurs stratégies de réplication ont été créées en fonction de la taille de la table (XS, XL, etc.).
> Certaines tables sont répliquées en temps réel tandis que d&#39;autres le sont toutes les heures. Certaines tables disposeront de mises à jour incrémentielles tandis que d&#39;autres bénéficieront d&#39;une mise à jour complète.

[En savoir plus sur la réplication des données](../config/replication.md)

### Gestion des identifiants

Les objets Campaign v8 utilisent désormais un **Identifiant universel unique (UUID)**, ce qui permet d&#39;identifier des données à l&#39;aide de valeurs uniques illimitées.

Veuillez noter que cet identifiant est basé sur des chaînes et n&#39;est pas séquentiel. La clé primaire n&#39;est pas une valeur numérique dans Campaign v8 et vous devez utiliser les attributs **autouuid** et **autopk** dans vos schémas.

Dans Campaign Classic v7 et les versions antérieures, l&#39;unicité d&#39;une clé dans un schéma (c&#39;est-à-dire une table) est gérée au niveau du moteur de la base de données. Plus généralement, les moteurs de base de données classiques tels que PostgreSQL, Oracle ou SQL Server incluent un mécanisme natif pour empêcher l&#39;insertion de lignes dupliquées à partir d&#39;une colonne ou d&#39;un ensemble de colonnes via des clés primaires et/ou des index uniques. Les ID en double n&#39;existent pas dans ces versions lorsque l&#39;index correct et les clés primaires sont définis au niveau de la base de données.

Adobe Campaign v8 est fourni avec Snowflake comme base de données principale. Comme cela augmente considérablement l&#39;échelle des requêtes, l&#39;architecture répartie de la base de données Snowflake ne fournit pas de tels mécanismes de gestion et d&#39;application de l&#39;unicité d&#39;une clé dans une table. Par conséquent, avec Adobe Campaign v8, rien n&#39;empêche l&#39;ingestion de clés dupliquées dans une table. Les utilisateurs finaux sont désormais chargés d&#39;assurer la cohérence des clés au sein de la base de données Adobe Campaign. [En savoir plus](../dev/keys.md)

### Maintenance simplifiée

Les utilisateurs de Campaign n&#39;ont pas besoin d&#39;être experts en bases de données. Il n&#39;est en effet plus nécessaire d&#39;effectuer des opérations complexes de maintenance des bases de données ou des indexations complexes de tables.

## Connexion à Campaign

Les utilisateurs de Campaign se connectent via leur Adobe ID. Le même Adobe ID est utilisé pour conserver tous vos plans d’Adobe et produits associés à un seul compte.

?? Découvrez comment vous connectez à [!DNL Campaign]sur [cette page](connect.md).

## Reporting

Notez que les rapports Adobe Campaign sont optimisés et offrent de meilleures fonctionnalités d&#39;échelle que Campaign Classic v7. Les limites sur les cubes ne s&#39;appliquent pas.

## Workflow {#workflow}

Campaign v8 propose une activité de workflow de ciblage supplémentaire : **[!UICONTROL Modifier la source de données]**.

L&#39;activité **[!UICONTROL Modifier la source de données]** permet de modifier la source de données d&#39;un workflow **[!UICONTROL Table de travail]** pour gérer les données de différentes sources de données telles que FDA, FFDA et base de données locale.

?? En savoir plus sur l’activité **[!UICONTROL Modifier la source de données]** dans [cette page](../config/workflows.md#change-data-source-activity).

## Fonctionnalités non disponibles{#gs-unavailable-features}

Veuillez noter que certaines fonctionnalités ne sont pas disponibles dans cette version de Campaign, telles que :

* Marketing Resource Management (Gestion des ressources marketing)
* Marketing distribué
* Gestion des offres entrantes (module Interaction)
* Optimisation des campagnes
* Gestion de la réaction
* Modèles de déploiement hybrides/On-premise
* Canal Twitter

>[!CAUTION]
>
>* À l&#39;heure actuelle, Campaign v8 est **uniquement** disponible en tant que Managed Cloud Service et ne peut pas être déployé dans des environnements on-premise ou hybrides.
>
>* La migration depuis un environnement Campaign Classic v7 existant n&#39;est pas encore disponible.
>
>* Si vous n&#39;êtes pas sûr de votre modèle de déploiement ou si vous avez des questions, contactez votre équipe de compte.


## Fonctionnalités non prises en charge{#gs-removed}

Pour s&#39;aligner sur la nouvelle architecture et le nouveau modèle de déploiement de Campaign v8, certaines fonctionnalités historiques de Campaign Classic v7 ne sont plus prises en charge dans Campaign v8, telles que :

* Coupons
* Tracking web
* Questionnaires
* Marketing pour réseaux sociaux  avec Facebook
* Connecteur ACS (offre principale)
* Intégration avec LDAP
* Connexion utilisateur/mot de passe

>[!NOTE]
>
>Certaines fonctionnalités non disponibles ou non prises en charge sont toujours visibles dans l&#39;interface utilisateur.