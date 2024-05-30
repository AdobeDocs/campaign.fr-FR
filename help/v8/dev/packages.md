---
title: Utiliser les packages de données
description: Utiliser les packages de données
feature: Data Management, Package Export/Import
role: Developer
level: Intermediate, Experienced
source-git-commit: 202a0553f0c736086eca993b9647737732f57d07
workflow-type: tm+mt
source-wordcount: '2020'
ht-degree: 50%

---

# Utiliser les packages de données{#data-packages}

## Prise en main des packages {#gs-data-packages}

Vous pouvez utiliser des packages de données pour exporter et importer vos données et paramètres personnalisés de plateforme. Un package peut contenir différents types de configurations et de composants, filtrés ou non.

Dans les packages de données Campaign, les entités de la base de données Adobe Campaign doivent être affichées dans des fichiers XML. Dans un package, chaque entité est représentée avec toutes ses données.

Le principe de **packages de données** consiste à exporter une configuration de données et à l’intégrer dans un autre environnement Adobe Campaign. Découvrez comment conserver un ensemble cohérent de packages de données dans cette [section](#data-package-best-practices).

### Types de packages {#types-of-packages}

Vous pouvez travailler avec trois types de packages dans Adobe Campaign : les packages utilisateur, les packages plate-forme et les packages administrateur.

* A **package utilisateur** permet de sélectionner la liste des entités à exporter. Ce type de package gère les dépendances et vérifie les erreurs.
* A **package de plateforme** comprend toutes les ressources techniques ajoutées (non livrées d&#39;usine) : schémas, code JavaScript, etc.
* Un **package admin** inclut tous les modèles et objets métiers ajoutés (non livrés d&#39;usine) : modèles, librairies, etc.

>[!CAUTION]
>
>La variable **platform** et **admin** Les packages contiennent une liste prédéfinie d&#39;entités à exporter. A chaque entité exportable sont associées des conditions de filtrage permettant d&#39;écarter les ressources livrées d&#39;usine du package créé.

## Structure des données {#data-structure}

La description d’un package de données est un document XML structuré respectant la grammaire de la variable **xrk:navtree** schéma de données, comme dans l’exemple ci-dessous :

```xml
<package>
  <entities schema="nms:recipient">
    <recipient email="john.smith@adobe.com" lastName="Smith" firstName="John">      
      <folder _operation="none" name="nmsRootFolder"/>      
      <company _operation="none" name="Adobe"/>
    </recipient>
  </entities>
  <entities schema="sfa:company">
    <company name="Adobe">
      <location city="London" zipCode="W11 2BQ"/>
    </company>
  </entities>
</package>
```

Le document XML doit commencer et se terminer par l&#39;élément `<package>`. Quelconque `<entities>` les éléments suivants répartissent les données par type de document. Un `<entities>` contient les données du package au format du schéma de données renseigné dans la variable **schema** attribut. Les données d&#39;un package ne doivent pas contenir de clés internes non compatibles entre les bases, comme les clés auto-générées (option **autopk**).

Dans notre exemple, les jointures sur la variable `folder` et `company` Les liens ont été remplacés par des clés dites de &quot;haut niveau&quot; sur les tables de destination :

```xml
<recipient>
  <folder _operation="none" name="nmsRootFolder"/>
  <company _operation="none" name="Adobe"/>
</recipient>
```

La variable `operation` avec la valeur `none` définit un lien de réconciliation.

Un package de données peut être créé manuellement à partir de n’importe quel éditeur de texte. Vous devez vous assurer que la structure du document XML est conforme au `xtk:navtree` schéma de données. La console cliente dispose d’un module d’export et d’import de package de données.

## Export de packages {#export-packages}

Les packages peuvent être exportés de trois manières différentes :

* Utilisez la variable **[!UICONTROL Exportation de package]** pour exporter un ensemble d’objets dans un même package. [En savoir plus](#export-a-set-of-objects-in-a-package)
* Pour exporter un **objet unique**, cliquez dessus avec le bouton droit et sélectionnez **[!UICONTROL Actions > Exporter dans un package]**.
* Utilisez la variable **Définitions de package** pour créer une structure de package dans laquelle vous ajoutez des objets à exporter ultérieurement dans un package. [En savoir plus](#manage-package-definitions)

Une fois un package exporté, vous pouvez l&#39;importer ainsi que toutes les entités ajoutées dans une autre instance Campaign.

### Exporter un ensemble d&#39;objets dans un package {#export-a-set-of-objects-in-a-package}

Pour exporter un ensemble d’objets dans un package de données, procédez comme suit :

1. Accédez à l’assistant d’export de package via le **[!UICONTROL Outils > Avancé > Export de package...]** de l’explorateur.
1. Sélectionnez la variable [types de packages](#types-of-packages).

   ![](assets/package_type.png)

1. Cliquez sur le bouton **Ajouter** pour sélectionner les entités à exporter en tant que package.

   >[!CAUTION]
   >
   >Si vous exportez un dossier de type **[!UICONTROL Catégorie d&#39;offres]**, **[!UICONTROL Environnement d&#39;offres]**, **[!UICONTROL Programme]** ou **[!UICONTROL Plan]**, ne sélectionnez en aucun cas l&#39;entité **xtk:folder** au risque de perdre une partie des données. Sélectionnez l&#39;entité correspondant au dossier : **nms:offerCategory** pour les catégories d&#39;offres, **nms:offerEnv** pour les environnements d&#39;offres, **nms:program** pour les programmes et **nms:plan** pour les plans.

   Le mécanisme de dépendance contrôle la séquence d&#39;exportation des entités. Pour plus d&#39;informations, consultez la section [Gestion des dépendances](#manage-dependencies).

1. Cliquez sur **[!UICONTROL Suivant]** et définir la requête de filtrage sur le type de document à extraire. Vous devez paramétrer la clause de filtrage pour l&#39;extraction des données.

   >[!NOTE]
   >
   >Le requêteur est présenté dans [cette section](../../automation/workflow/query.md).

1. Cliquez sur **[!UICONTROL Suivant]** et sélectionnez l’ordre de tri des données exportées.

1. Prévisualisez les données à extraire pour vérifier votre configuration.

1. La dernière page de l&#39;assistant d&#39;export de package permet de lancer l&#39;export. Les données seront stockées dans le fichier indiqué dans le champ **[!UICONTROL Fichier]**.

### Gérer les dépendances {#manage-dependencies}

Le processus d&#39;export effectue le suivi des liens entre les différents éléments exportés. Deux règles définissent le mécanisme :

* liés à un lien avec un objet `own` ou `owncopy` l’intégrité du type est exportée dans le même package que l’objet exporté.
* objets liés à un lien `neutral` ou `define` l&#39;intégrité du type (lien défini) doit être exportée séparément.

>[!NOTE]
>
>Les types d’intégrité liés aux éléments de schéma sont définis dans [cette page](database-links.md).

#### Exporter une campagne {#export-a-campaign}

Vous trouverez ci-dessous un exemple d&#39;export d&#39;une campagne. La campagne marketing à exporter contient :
* a `MyTask`tâche
* a `campaignWorkflow` workflow dans le dossier suivant : **[!UICONTROL Administration > Exploitation > Workflows techniques > Processus de campagne > MyWorkflow]**.

La tâche et le workflow sont exportés dans le même package que l&#39;opération, car les schémas correspondants sont reliés par des liens avec un `own` intégrité du type .

Le contenu du module est le suivant :

```xml
<?xml version='1.0'?>
<package author="Administrator (admin)" buildNumber="7974" buildVersion="7.1" img=""
label="" name="" namespace="" vendor="">
 <desc></desc>
 <version buildDate="2013-01-09 10:30:18.954Z"/>
 <entities schema="nms:operation">
  <operation duration="432000" end="2013-01-14" internalName="OP1" label="MyCampaign"
  modelName="opEmpty" start="2013-01-09">
   <controlGroup>
    <where filteringSchema=""/>
   </controlGroup>
   <seedList>
    <where filteringSchema="nms:seedMember"></where>
    <seedMember internalName="SDM1"></seedMember>
   </seedList>
   <parameter useAsset="1" useBudget="1" useControlGroup="1" useDeliveryOutline="1"
   useDocument="1" useFCPValidation="0" useSeedMember="1" useTask="1"
   useValidation="1" useWorkflow="1"></parameter>
   <fcpSeed>
    <where filteringSchema="nms:seedMember"></where>
   </fcpSeed>
   <owner _operation="none" name="admin" type="0"/>
   <program _operation="none" name="nmsOperations"/>
   <task end="2013-01-17 10:07:51.000Z" label="MyTask" name="TSK2" start="2013-01-16 10:07:51.000Z"
   status="1">
    <owner _operation="none" name="admin" type="0"/>
    <operation _operation="none" internalName="OP1"/>
    <folder _operation="none" name="nmsTask"/>
   </task>
   <workflow internalName="WKF12" label="CampaignWorkflow" modelName="newOpEmpty"
   order="8982" scenario-cs="Notification of the workflow supervisor (notifySupervisor)"
   schema="nms:recipient">
    <scenario internalName="notifySupervisor"/>
    <desc></desc>
    <folder _operation="none" name="Folder4"/>
    <operation _operation="none" internalName="OP1"/>
   </workflow>
  </operation>
 </entities>
</package>   
```

L’appartenance à un type de package est défini dans un schéma avec la variable `@pkgAdmin and @pkgPlatform` attribut. Ces deux attributs reçoivent une expression XTK définissant les conditions d&#39;appartenance au package.

```xml
<element name="offerEnv" img="nms:offerEnv.png" 
template="xtk:folder" pkgAdmin="@id != 0">
```

Enfin, la `@pkgStatus` vous permet de définir les règles d’exportation de ces éléments ou attributs. Selon la valeur de l&#39;attribut, l&#39;élément ou l&#39;attribut sera présent dans le package exporté. Les trois valeurs possibles pour cet attribut sont :

* `never`: n’exporte pas le champ/lien
* `always`: force l’exportation de ce champ
* `preCreate`: autorise la création de l’entité liée

>[!NOTE]
>
>La variable `preCreate` n’est admise que pour les événements de type lien. Il vous permet de créer ou de pointer vers une entité qui n’est pas encore chargée dans le package exporté.

## Gérer les définitions de packages {#manage-package-definitions}

Les définitions de packages vous permettent de créer une structure de package dans laquelle vous ajoutez les entités qui seront exportées ultérieurement dans un même package. Vous pourrez ensuite importer ce package et toutes les entités ajoutées dans une autre instance Campaign.

### Créer une définition de package {#create-a-package-definition}

Les définitions de packages sont accessibles à partir du menu **[!UICONTROL Administration > Paramétrage > Gestion des packages > Définitions de packages]**.

Pour créer une définition de package, cliquez sur le bouton **[!UICONTROL Nouveau]**, puis remplissez les informations générales de la définition de package.

![](assets/packagedefinition_create.png)

Vous pouvez ensuite ajouter des entités à la définition de package et l&#39;exporter dans un package de fichier XML.

**Rubriques connexes :**

* [Ajouter des entités à une définition de package](#add-entities-to-a-package-definition)
* [Paramétrer la génération des définitions de packages](#configure-package-definitions-generation)
* [Exporter des packages à partir d&#39;une définition de package](#export-packages-from-a-package-definition)

### Ajouter des entités à une définition de package {#add-entities-to-a-package-definition}

Dans l&#39;onglet **[!UICONTROL Contenu]**, cliquez sur le bouton **[!UICONTROL Ajouter]** pour sélectionner les entités à exporter avec le package. Les bonnes pratiques relatives à la sélection d’entités sont présentées dans la section [cette section](#export-a-set-of-objects-in-a-package).

![](assets/packagedefinition_addentities.png)

Les entités peuvent être ajoutées directement à une définition de package à partir de leur emplacement dans l&#39;instance. Pour ce faire, suivez les étapes ci-dessous :

1. Cliquez avec le bouton droit de la souris sur l&#39;entité désirée, puis sélectionnez **[!UICONTROL Actions > Exporter dans un package]**.

1. Sélectionnez **[!UICONTROL Ajout dans une définition de package]**, puis sélectionnez la définition de package dans laquelle vous voulez ajouter l&#39;entité.

1. L&#39;entité est ajoutée dans la définition de package, elle sera exportée avec le package (voir [cette section](#export-packages-from-a-package-definition)).

### Paramétrer la génération des définitions de packages {#configure-package-definitions-generation}

La génération de packages peut être paramétrée à partir de l&#39;onglet **[!UICONTROL Contenu]** de définition de package. Pour ce faire, cliquez sur le lien **[!UICONTROL Paramètres de génération]**.

![](assets/packagedefinition_generationparameters.png)

* Utilisez la variable **[!UICONTROL Inclure la définition]** pour inclure la définition actuellement utilisée dans la définition de package.
* Utilisez la variable **[!UICONTROL Inclure un script d’installation]** pour ajouter un script javascript à exécuter lors de l’importation du package. S&#39;il est sélectionné, un onglet **[!UICONTROL Script]** est ajouté à l&#39;écran de définition de package.
* Utilisez la variable **[!UICONTROL Inclure les valeurs par défaut]** pour ajouter les valeurs de tous les attributs des entités au package.

  Cette option n&#39;est pas sélectionnée par défaut, afin d&#39;éviter les exports longs. Cela signifie que, par défaut, les attributs des entités avec des valeurs par défaut (&#39;chaîne vide&#39;, &#39;0&#39; et &#39;false&#39; si elles ne sont pas définies autrement dans le schéma) ne sont pas ajoutés au package et ne sont donc pas exportés.

  >[!CAUTION]
  >
  >Si l&#39;instance où le package est importé contient des entités identiques à celles du package (par exemple, avec le même ID externe), leurs attributs ne seront pas mis à jour. Cela peut se produire si les attributs de l’instance précédente ont des valeurs par défaut, car ils ne sont pas inclus dans le package. Dans ce cas, la sélection de l&#39;option **[!UICONTROL Inclure les valeurs par défaut]** empêcherait la fusion des versions, car tous les attributs de l&#39;instance précédente seraient exportés avec le package.

### Exporter des packages à partir d&#39;une définition de package {#export-packages-from-a-package-definition}

Pour exporter un package à partir d&#39;une définition de package, suivez les étapes ci-dessous :

1. Sélectionnez la définition de package à exporter, puis cliquez sur le bouton **[!UICONTROL Actions]** et sélectionnez **[!UICONTROL Exporter le package]**.
1. Vérifiez le nom et l’emplacement du fichier exporté.
1. Cliquez sur le bouton **[!UICONTROL Début]** pour lancer l&#39;export.

## Importer des packages {#import-packages}

L&#39;assistant d&#39;import de package est accessible à partir du menu principal **[!UICONTROL Outils > Avancé > Importer un package]** de la console cliente.

### Installer un package depuis un fichier {#install-a-package-from-a-file}

Pour importer un package de données existant, procédez comme suit :

1. Accéder à l&#39;assistant d&#39;import via le menu principal **[!UICONTROL Outils > Avancé > Importer un package]** de la console cliente.
1. Sélectionnez le fichier XML et cliquez sur **[!UICONTROL Ouvrir]**.

Le contenu du package à importer est alors affiché dans la section centrale de l&#39;éditeur.

Cliquez sur **[!UICONTROL Suivant]** puis sur **[!UICONTROL Démarrer]** pour lancer l&#39;import.

### Installer un package natif {#install-a-standard-package}

Packages intégrés (alias . les packages standard) sont installés lors de la configuration d’Adobe Campaign. Selon vos autorisations, votre modèle de déploiement et votre offre de produit, vous pouvez importer de nouveaux packages standard.

Reportez-vous à votre contrat de licence pour savoir quels packages peuvent être installés.

## Bonnes pratiques relatives aux packages de données {#data-package-best-practices}

Cette section décrit comment organiser les packages de données de façon cohérente tout au long de la vie du projet.


### Versions

Vous devez toujours importer dans la même version de la plateforme. Vous devez vérifier que vous déployez vos packages entre deux instances associées au même build. Ne forcez jamais l&#39;import et mettez toujours la plateforme à jour en premier (si le build est différent).

>[!IMPORTANT]
>
>L&#39;import entre différentes versions n&#39;est pas pris en charge par Adobe.

Accordez de l&#39;attention à la structure du schéma et de la base de données. L&#39;import d&#39;un package avec schéma doit être suivi de la génération de schémas.

### Types de packages {#package-types}

Commencez par définir différents types de packages. Seuls quatre types sont utilisés :

**Entités**

* Tous les éléments spécifiques &quot;xtk&quot; et &quot;nms&quot; dans Adobe Campaign tels que les schémas, les formulaires, dossiers, modèles de diffusion, etc.
* Vous pouvez considérer une entité comme un élément &quot;admin&quot; et &quot;platform&quot;.
* Vous ne devez pas inclure plus d&#39;une entité dans un package lorsque vous le chargez sur une instance Campaign.

Si vous devez déployer votre configuration sur une nouvelle instance, vous pouvez importer tous vos packages d&#39;entités.

**Fonctionnalités**

Ce type de package a les avantages suivants :
* Répond à une exigence/spécification du client.
* Contient une ou plusieurs fonctionnalités.
* Doit contenir toutes les dépendances pour pouvoir exécuter la fonctionnalité sans aucun autre package.

**Campagnes**

Ce package n&#39;est pas obligatoire. Il est parfois utile de créer un type spécifique pour toutes les campagnes, même si une campagne peut être considérée comme une fonctionnalité.

**Mises à jour**

Une fois configurée, une fonctionnalité peut être exportée dans un autre environnement. Par exemple, le package peut être exporté d&#39;un environnement de développement vers un environnement de test. Dans ce test, un défaut est mis en évidence. Il doit être tout d&#39;abord corrigé dans l&#39;environnement de développement. Ensuite, le correctif doit être appliqué à la plateforme de test.

La première solution consisterait à réexporter l&#39;ensemble de la fonctionnalité. Cependant, pour éviter tout risque (comme la mise à jour d&#39;éléments indésirables), il est plus sûr d&#39;avoir un package ne contenant que la correction.

C’est pourquoi nous vous recommandons de créer un package &quot;update&quot; contenant un seul type d’entité de la fonctionnalité.

Une mise à jour peut non seulement être constituée d&#39;un correctif, mais aussi d&#39;un nouvel élément de votre package d&#39;entité/de fonctionnalité/de campagne. Pour éviter de déployer l&#39;ensemble du package, vous pouvez exporter un package de mise à jour.

### Conventions de dénomination {#data-package-naming}

Les types étant définis, nous devons spécifier une convention de dénomination. Adobe Campaign ne permettant pas de créer des sous-dossiers pour les spécifications de package, les nombres constituent la meilleure solution pour assurer l’organisation. Les nombres préfixent les noms des packages.

Par exemple, vous pouvez utiliser la convention suivante :

* Entité : de 1 à 99
* Fonctionnalité : de 100 à 199
* Campagne : de 200 à 299
* Mise à jour : de 5000 à 5999

#### Ordre des packages d&#39;entité {#entity-packages-order}

Pour faciliter l’import, les packages d’entités doivent être triés au fur et à mesure de leur importation.

Par exemple :

* 001 – Schéma
* 002 – Formulaire
* 003 – Images
* etc.

>[!NOTE]
>
>Forms ne doit être importé que **after** mises à jour des schémas.


#### Documentation du package {#package-documentation}

Lorsque vous mettez à jour un package, vous devez toujours insérer un commentaire dans le champ de description pour donner des informations détaillées sur les modifications et les motifs (par exemple, « ajouter un nouveau schéma » ou « corriger un défaut »).

Il est également recommandé d’indiquer la date de la mise à jour.

>[!IMPORTANT]
>
>Le champ de description peut contenir 2 000 caractères au maximum.

