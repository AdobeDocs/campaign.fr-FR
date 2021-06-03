---
product: Adobe Campaign
title: Bonnes pratiques relatives au modèle de données
description: Découvrez les bonnes pratiques relatives à l’extension des modèles de données de Campaign
source-git-commit: 726e8d3ba00481237af2765e2f339d755f4e6a01
workflow-type: tm+mt
source-wordcount: '2686'
ht-degree: 94%

---

# Bonnes pratiques relatives au modèle de données{#data-model-best-practices}

Ce document présente les principales recommandations lors de la conception de votre modèle de données Adobe Campaign.

Le système Adobe Campaign est très flexible et peut être étendu au-delà de l’implémentation initiale. Toutefois, même si les possibilités sont infinies, il est essentiel de prendre des décisions judicieuses et de construire des bases solides pour commencer à concevoir votre modèle de données.

Afin de mieux comprendre le fonctionnement des tables intégrées de Campaign et leurs interactions les unes avec les autres, consultez [cette section](datamodel.md).

[!DNL :bulb:] Pour commencer à utiliser les schémas de Campaign, consultez [cette section](schemas.md).

[!DNL :bulb:] Découvrez comment configurer des schémas d’extension afin d’étendre le modèle de données conceptuel de la base de données Adobe Campaign sur [cette page](extend-schema.md).

## Architecture du modèle de données {#data-model-architecture}

Adobe Campaign est un puissant système de gestion de campagnes cross-canal. Il peut vous aider à aligner vos stratégies en ligne et hors ligne pour créer des expériences client personnalisées.

### Approche axée sur le client {#customer-centric-approach}

Bien que la plupart des fournisseurs de services de messagerie communiquent avec les clients par le biais d’une approche centrée sur des listes, Adobe Campaign s’appuie sur une base de données relationnelle afin d’obtenir une vision plus large des clients et de leurs attributs.

Pour obtenir la description de chaque table, accédez à **[!UICONTROL Administration > Paramétrage > Schémas de données]**, sélectionnez une ressource dans la liste et cliquez sur l’onglet **[!UICONTROL Documentation]**.


>[!NOTE]
>
>Adobe Campaign permet de créer une [table de destinataires personnalisée](custom-recipient.md). Cependant, dans la plupart des cas, il est recommandé d’utiliser la [table de destinataires](datamodel.md#ootb-profiles) native, qui contient des tables et des fonctionnalités supplémentaires préconfigurées.

### Données pour Adobe Campaign {#data-for-campaign}

Quelles données doivent être envoyées à Adobe Campaign ? Il est essentiel de déterminer les données requises pour vos activités marketing.

>[!NOTE]
>
> Adobe Campaign n’est ni un entrepôt de données, ni un outil de reporting. Vous devez donc éviter d’importer dans Adobe Campaign tous les clients possibles et les informations qui s’y rapportent, ou d’importer des données uniquement pour créer des rapports.

Pour décider si un attribut est nécessaire ou non dans Adobe Campaign, demandez-vous s’il appartient à l’une des catégories suivantes :

* Attribut utilisé pour la **segmentation**
* Attribut utilisé pour les **processus de gestion des données** (calcul agrégé, par exemple)
* Attribut utilisé pour la **personnalisation**

S’il n’appartient à aucune de ces catégories, il est probable que vous n’ayez pas besoin de cet attribut dans Adobe Campaign.

### Choix des types de données {#data-types}

Pour optimiser l’architecture et les performances de votre système, appliquez les bonnes pratiques suivantes pour configurer les données dans Adobe Campaign.

* Dans un grand tableau, vous pouvez insérer des champs de chaîne ou numériques et ajouter des liens vers des tables de référence (lorsque vous utilisez des listes de valeurs).
* L’attribut **expr** permet de définir un attribut de schéma sous la forme d’un champ calculé plutôt que d’une valeur physique définie dans une table. Vous pouvez ainsi accéder aux informations dans un format différent (par exemple, l’âge et la date de naissance) sans avoir à stocker les deux valeurs. Il s’agit d’un bon moyen d’éviter la duplication des champs. Par exemple, la table des destinataires utilise une expression relative au domaine qui est déjà présente dans le champ de l’email.
* Toutefois, lorsque le calcul de l’expression est complexe, il n’est pas recommandé d’utiliser l’attribut **expr**, car le calcul à la volée peut avoir une incidence sur les performances de vos requêtes.
* Le type **XML** est un bon moyen d’éviter de créer des champs superflus. Cependant, il occupe aussi un certain volume d’espace disque, car il utilise une colonne CLOB dans la base de données. Il peut aussi contribuer à la complexité des requêtes SQL et avoir un impact sur les performances.
* La longueur d’un champ de **chaîne** doit toujours être définie avec la colonne. Par défaut, la longueur maximale dans Adobe Campaign est de 16 Ko, mais Adobe recommande de raccourcir le champ si vous savez déjà que la taille ne dépassera pas une longueur inférieure.
* Dans Adobe Campaign, il est acceptable de disposer d’un champ plus court que dans le système source si vous êtes sûr que la taille du système source a été surestimée et ne sera pas atteinte. Cela peut signifier une chaîne plus courte ou un entier plus petit dans Adobe Campaign.

### Choix des champs {#choice-of-fields}

Un champ doit être stocké dans une table s’il est destiné à un ciblage ou une personnalisation. En d’autres termes, si un champ n’est pas utilisé pour envoyer un e-mail personnalisé ou comme critère dans une requête, il occupe de l’espace disque inutilement.

### Choix des clés {#choice-of-keys}

Outre les **autouuid** et **autopk** définis par défaut dans la plupart des tables, vous devez envisager d’ajouter des clés logiques ou métier (numéro de compte, numéro de client, etc.). Vous pourrez l’utiliser ultérieurement pour les imports et les réconciliations ou les packages de données. Pour plus d’informations, voir la section [Identificateurs](#identifiers).

L’efficacité des clés est essentielle pour les performances. Snowflake vous permet d’insérer des types de données numériques ou string comme clés pour les tableaux.

<!-- ### Dedicated tablespaces {#dedicated-tablespaces}

The tablespace attribute in the schema allows you to specify a dedicated tablespace for a table.

The installation wizard allows you to store objects by type (data, temporary).

Dedicated tablespaces are better for partitioning, security rules, and allow fluid and flexible administration, better optimization, and performance. -->

## Identificateurs {#identifiers}

Les ressources Adobe Campaign ont trois identifiants et il est possible d’en ajouter un supplémentaire.

Le tableau ci-après décrit ces identifiants et leur finalité.

| Identifiant | Description | Bonnes pratiques |
|--- |--- |--- |
| Id | <ul><li>L’id est la clé primaire physique d’une table Adobe Campaign. Pour les tables intégrées, il s’agit d’un identifiant universel unique (UUID).</li><li>Cet identifiant doit être unique. </li><li>Un UUID est visible dans une définition de schéma.</li></ul> | <ul><li>Les identifiants générés automatiquement ne peuvent pas être utilisés comme référence dans un workflow ou une définition de package.</li><li>L’identifiant d’une table est un UUID dont le type ne doit pas être modifié.</li></ul> |
| Nom (ou nom interne) | <ul><li>Cette information est l’identifiant unique d’un enregistrement dans une table. Cette valeur peut être mise à jour manuellement, généralement avec un nom généré.</li><li>Cet identifiant conserve sa valeur lorsqu’il est déployé dans une autre instance d’Adobe Campaign et ne doit pas être vide.</li></ul> | <ul><li>Changez le nom d’enregistrement généré par Adobe Campaign si l’objet est destiné à être déployé d’un environnement à un autre.</li><li>Si un objet possède un attribut d’espace de noms (par exemple, *schema*), cet espace de noms commun sera appliqué à tous les objets personnalisés créés. Certains espaces de noms réservés ne doivent pas être utilisés : *nms*, *xtk*, etc.  Notez que certains espaces de noms sont internes uniquement. [En savoir plus](schemas.md#reserved-namespaces).</li><li>Lorsqu’un objet n’a pas d’espace de noms (*workflow* ou *delivery*, par exemple), cette notion d’espace de noms est ajoutée sous la forme d’un préfixe d’un objet de nom interne : *namespaceMyObjectName*.</li><li>N’utilisez pas de caractères spéciaux tels que l’espace « », le point-virgule « ; » ou le tiret « - ». Tous ces caractères seront remplacés par un trait de soulignement « _ » (caractère autorisé). Par exemple, « abc-def » et « abc:def » seront stockés sous la forme de « abc_def » et s’écraseront mutuellement.</li></ul> |
| Libellé | <ul><li>Le libellé est l’identifiant d’entreprise d’un objet ou d’un enregistrement dans Adobe Campaign.</li><li>Cet objet autorise les espaces et les caractères spéciaux.</li><li>Il ne garantit pas le caractère unique d&#39;un enregistrement.</li></ul> | <ul><li>Il est recommandé de déterminer une structure pour les libellés de vos objets.</li><li>Il s’agit de la solution la plus conviviale pour identifier un enregistrement ou un objet pour un utilisateur d’Adobe Campaign.</li></ul> |

La clé primaire d’Adobe Campaign est un UUID généré automatiquement pour toutes les tables intégrées. Un UUID peut également être utilisé pour les tables personnalisées.

Même si le nombre d’identifiants est illimité, vous devez prendre en charge la taille de votre base de données pour garantir des performances optimales. Pour éviter tout problème, veillez à ajuster les paramètres de purge de votre instance. Pour plus d’informations à ce sujet, consultez [cette section](#data-retention).


## Clés internes personnalisées {#custom-internal-keys}

Pour chaque table créée dans Adobe Campaign, des clés primaires sont nécessaires.

La plupart des organisations importent des enregistrements à partir de systèmes externes. Bien que la clé physique de la table des destinataires soit l’attribut « id », il est possible de déterminer aussi une clé personnalisée.

Cette clé personnalisée est la clé primaire d’enregistrement réelle dans le système externe chargé d’alimenter Adobe Campaign.

Pour la création d’une table personnalisée, vous avez deux possibilités :
* Combinaison d’une clé générée automatiquement (id) et d’une clé interne (personnalisée). Cette option est intéressante si votre clé système est une clé composite ou n’est pas un entier. Avec Snowflake, les entiers ou les clés basées sur des chaînes offrent des performances supérieures dans les grandes tables et dans la jointure avec d’autres tables.
* Utilisation de la clé primaire comme clé primaire du système externe. Cette solution est généralement préférable, car elle simplifie l’approche d’import et d’export des données, avec une clé cohérente entre les différents systèmes. **Autouuid doit être désactivé si la clé est nommée « id » et qu’elle doit être remplie avec des valeurs externes (et non par génération automatique).**

>[!CAUTION]
>
>Un autouuid ne doit pas être utilisé comme référence dans les workflows.


## Liens et cardinalité {#links-and-cardinality}

### Liens {#links}

Attention à l’intégrité « propre » des grandes tables. La suppression d’enregistrements possédant des tables volumineuses avec une intégrité qui leur est propre peut éventuellement arrêter l’instance. La table est verrouillée et les suppressions sont faites une par une. Il est donc préférable d’appliquer une intégrité « neutre » sur les tables enfants très volumineuses.

La déclaration d’un lien en tant que jointure externe est néfaste pour les performances. L’enregistrement Zero ID émule la fonctionnalité de jointure externe. Il n’est pas nécessaire de déclarer des jointures externes si le lien utilise la balise **autouuid**.

Bien qu’il soit possible de joindre n’importe quelle table dans un workflow, Adobe recommande de définir des liens communs entre les ressources directement dans la définition de la structure de données.

Le lien doit être défini en fonction des données réelles contenues dans vos tables. Une mauvaise définition peut avoir un impact sur les données récupérées via les liens, par exemple la duplication inattendue d’enregistrements.

Attribuez au lien un nom cohérent avec celui de la table : le nom du lien doit permettre de comprendre à quoi correspond la table distante.

N’utilisez pas un nom de lien comportant le suffixe « id ». Par exemple, appelez-le « transaction » plutôt que « transactionId ».

Par défaut, Adobe Campaign crée un lien à l’aide de la clé primaire de la table externe. Pour plus de clarté, il est préférable de définir explicitement la jointure dans la définition du lien.

### Cardinalité {#cardinality}

Pour créer un lien, veillez à ce que l’enregistrement cible soit unique lorsqu’une relation 1-1 a été déclarée. Dans le cas contraire, la jointure risque de renvoyer plusieurs enregistrements alors qu’un seul est attendu. Cette situation entraîne des erreurs lors de la préparation de la diffusion lorsque « la requête renvoie plus de lignes qu’attendu ». Définissez un nom de lien identique à celui du schéma cible.

Définissez un lien possédant une cardinalité (1-N) dans le schéma du côté (1). Par exemple, la relation Destinataire (1) – (N) Transaction doit être définie dans le schéma de transaction.

Notez que la cardinalité inverse d’un lien est (N) par défaut. Il est possible de définir un lien (1-1) en ajoutant l’attribut revCardinality=&#39;single&#39; à la définition du lien.

Si le lien inverse ne doit pas être visible pour l’utilisateur, vous pouvez le masquer avec la définition de lien revLink=&#39;_NONE_&#39;. Un bon exemple d’utilisation consiste à définir un lien entre le destinataire et la dernière transaction effectuée, par exemple. Il vous suffit de voir le lien entre le destinataire et la dernière transaction. Aucun lien inverse ne doit être visible dans la table de transaction.

Les liens d’une jointure externe (1-0..1) doivent être utilisés avec soin, car ils ont une incidence sur les performances du système.

## Conservation des données {#data-retention}

 Adobe Campaign n’est ni un entrepôt de données, ni un outil de reporting. Pour garantir de bonnes performances, la croissance des bases de données doit rester sous contrôle. Pour cela, il peut être utile de suivre certaines des bonnes pratiques ci-dessous.

En ce qui concerne la conservation des données, les tables de logs d&#39;usine de Campaign possèdent des périodes de conservation prédéfinies, limitant généralement le stockage des données à 6 mois ou moins.

Vous trouverez ci-dessous les valeurs de conservation par défaut pour les tables d’usine. Notez que la configuration de conservation est définie par les administrateurs techniques Adobe lors de la mise en œuvre et que les valeurs peuvent varier pour chaque mise en œuvre, selon les exigences du client.

* **Tracking consolidé** : 1 an
* **Logs de diffusion** : 6 mois
* **Logs de tracking** : 1 an
* **Diffusions supprimées** : 1 semaine
* **Rejets d&#39;imports** : 6 mois
* **Profils des visiteurs** : 1 mois
* **Propositions d&#39;offres** : 1 an
* **Evénements** : 1 mois
* **Statistiques du traitement des événements** : 1 an
* **Evénements archivés** : 1 an
* **Evénements Pipeline ignorés** : 1 mois

>[!CAUTION]
>
>Les tables personnalisées ne sont pas purgées par le processus de nettoyage standard. Bien que cela ne soit pas nécessaire dès le début, n’oubliez pas de créer un processus de purge de vos tables personnalisées, faute de quoi des problèmes de performances peuvent se produire.

Il existe un certain nombre de solutions pour minimiser le besoin d’enregistrements dans Adobe Campaign :
* Exportez les données dans un entrepôt de données extérieur à Adobe Campaign.
* Générez des valeurs agrégées qui utilisent moins d’espace, mais suffisantes pour vos pratiques marketing. Par exemple, vous n’avez pas besoin de l’historique complet des transactions client d’Adobe Campaign pour le tracking des derniers achats.

Vous pouvez déclarer l’attribut « deleteStatus » dans un schéma. Il est plus efficace de marquer l’enregistrement comme supprimé, puis de différer la suppression au cours de la tâche de nettoyage.

[!DNL :speech_balloon:] En tant qu’utilisateur Managed Cloud Services, contactez les consultants ou administrateurs techniques Adobe pour en savoir plus sur la conservation des données ou si vous devez définir la conservation des tables personnalisées.

## Performances {#performance}

Afin d’optimiser les performances à tout moment, suivez les bonnes pratiques ci-dessous.

### Recommandations générales {#general-recommendations}

* Évitez d’utiliser des opérations telles que « CONTAINS » dans les requêtes. Si vous savez ce qui est attendu et souhaitez appliquer un filtre, appliquez la même condition avec un opérateur « ÉGAL À » ou d’autres opérateurs de filtre spécifiques.
* Veillez à ce que les processus tels que l’import et l’export se produisent en dehors des heures de bureau.
* Vérifiez qu’il existe un planning pour toutes les activités quotidiennes et respectez-le.
* Si un ou plusieurs processus quotidiens échouent et s’ils doivent être exécutés le même jour, vérifiez que des processus en conflit ne sont pas en cours d’exécution lorsque le processus manuel est lancé, car cela peut avoir un impact sur les performances du système.
* Vérifiez qu’aucune campagne quotidienne n’est exécutée pendant le processus d’import ou lorsqu’un processus manuel est exécuté.
* Utilisez une ou plusieurs tables de référence plutôt que de dupliquer un champ dans chaque ligne. Lors de l’utilisation de paires clé/valeur, il est préférable de choisir une clé numérique.
* Une chaîne courte reste acceptable. Si des tables de références sont déjà en place dans un système externe, les réutiliser facilitera l’intégration des données avec Adobe Campaign.

### Relations de type « un à plusieurs » {#one-to-many-relationships}

* La conception des données a un impact sur la convivialité et les fonctionnalités. Si vous concevez votre modèle de données avec de nombreuses relations de type « un à plusieurs », il devient plus difficile pour les utilisateurs de construire une logique significative dans l’application. Il peut s’avérer difficile pour les marketeurs n’ayant pas de compétences techniques de construire et de comprendre correctement la logique.
* Qu’une table comporte tous les champs essentiels est une bonne chose car cela facilite la création de requêtes par les utilisateurs. Il est aussi parfois judicieux de dupliquer certains champs d’une table à l’autre si cela permet d’éviter une jointure.
* Certaines fonctionnalités intégrées ne pourront pas faire référence à des relations de type « un à plusieurs », par exemple la formule Pondération d’offre et Diffusions.

## Tables volumineuses {#large-tables}

 Adobe Campaign fait appel à des moteurs de bases de données tiers. Selon le fournisseur, l’optimisation des performances des tables les plus volumineuses peut nécessiter une conception spécifique.

Vous trouverez ci-dessous quelques bonnes pratiques courantes à appliquer lors de la conception de votre modèle de données utilisant des tables volumineuses et des jointures complexes.

* Lorsque vous utilisez des tables de destinataires par défaut supplémentaires, veillez à disposer d’une table de logs dédiée pour chaque mapping de diffusion.
* Diminuez le nombre de colonnes, notamment en identifiant celles qui ne sont pas utilisées.
* Optimisez les relations du modèle de données en évitant les jointures complexes, notamment celles qui concernent plusieurs conditions et/ou colonnes.
* Pour les clés de jointure, vous pouvez utiliser des valeurs numériques ou string.
* Réduisez autant que possible la profondeur de conservation des logs. Si vous avez besoin d’un historique plus détaillé, vous pouvez agréger le calcul et/ou gérer des tables de logs personnalisées pour stocker un historique plus volumineux.

### Taille des tables {#size-of-tables}

La taille de la table est le résultat d’une combinaison du nombre d’enregistrements et du nombre de colonnes par enregistrement. L’un et l’autre peuvent avoir une incidence sur les performances des requêtes.

* Une table de **petite taille** est similaire à la table de diffusion.
* Une table de **taille moyenne** possède une taille identique à celle de la table des destinataires. Elle contient un enregistrement par client.
* Une table de **grande taille** est similaire à la table des broadlogs. Elle contient de nombreux enregistrements par client.
Par exemple, si votre base de données contient 10 millions de destinataires, la table des broadlogs possède entre 100 et 200 millions de messages, et la table de diffusion quelques milliers d’enregistrements.

Le nombre de lignes a également une incidence sur les performances. La base de données d’Adobe Campaign n’est pas conçue pour stocker des historiques qui ne sont pas activement utilisés à des fins de ciblage ou de personnalisation. Il s’agit d’une base de données opérationnelle.

Pour éviter tout problème de performances lié au nombre élevé de lignes, conservez uniquement les enregistrements nécessaires dans la base de données. Les autres enregistrements doivent être exportés vers un entrepôt de données tiers et supprimés de la base de données opérationnelle d’Adobe Campaign.

Voici quelques bonnes pratiques concernant la taille des tables :

* Créez de grandes tables contenant moins de champs et plus de données numériques.
* N’utilisez pas les types correspondant aux grands nombres pour les colonnes si vous souhaitez stocker de petits nombres comme les valeurs booléennes.
* Supprimez les colonnes inutilisées de la définition de la table.
* Ne conservez pas les données historiques ou inactives dans votre base de données Adobe Campaign (export et nettoyage).
