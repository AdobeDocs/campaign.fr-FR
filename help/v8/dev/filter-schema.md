---
title: Filtrage des schémas Campaign
description: Découvrez comment filtrer les schémas Campaign
feature: Schema Extension
role: Developer
level: Intermediate, Experienced
exl-id: e8ad021c-ce2e-4a74-b9bf-a989d8879fd1
TQID: 'https://experienceleague.adobe.com/2T0OxjyVTM9-lzsOfcaqv81YVtVvrNpprpyC0VLoWgU'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b82389f8-9b5e-4083-8e3b-3cef299fb8b9
    internal-label: Schemas
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: e3988c18-3cfa-4f16-b812-ac2d2b1056fa
    internal-label: Permissions
  - id: a72a22e0-8c8d-4019-ba42-3f2644aa91a3
    internal-label: Schema extension
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 100%
---
# Filtrage des schémas{#filter-schemas}

## Filtres système {#system-filters}

Vous pouvez filtrer l’accès aux schémas pour des utilisateurs et utilisatrices spécifiques, selon leurs autorisations. Les filtres système vous permettent de gérer les autorisations de lecture et d’écriture des entités figurant dans les schémas, au moyen des paramètres **readAccess** et **writeAccess**.

>[!NOTE]
>
>Cette restriction s’applique uniquement aux utilisateurs n’ayant pas de connaissances techniques : un utilisateur technique, avec les autorisations associées ou utilisant un workflow, sera en mesure de récupérer les données et de les mettre à jour.

* **readAccess** : permet d&#39;accéder aux données d&#39;un schéma en lecture seule.

  **Attention** : toutes les tables liées doivent être définies avec la même restriction. Cette configuration peut avoir une incidence sur les performances.

* **writeAccess** : permet d&#39;accéder aux données d&#39;un schéma en écriture.

Ces filtres sont renseignés au niveau de l’**élément** principal des schémas et peuvent être formés comme dans les exemples suivants afin de restreindre l’accès :

* Restreindre les autorisations d’ÉCRITURE

  Ici, le filtre sert à interdire les autorisations d’ÉCRITURE sur le schéma aux opérateurs et opératrices ne disposant pas de l’autorisation d’ADMINISTRATION. Cela signifie que seuls les administrateurs et administratrices disposeront d’autorisations d’écriture sur les entités décrites par ce schéma.

  ```
  <sysFilter name="writeAccess">      
   <condition enabledIf="hasNamedRight('admin')=false" expr="FALSE"/>    
  </sysFilter>
  ```

* Restreindre les autorisations de LECTURE et d’ÉCRITURE :

  Ici, le filtre sert à interdire à la fois les autorisations de LECTURE et d’ÉCRITURE du schéma à tous les opérateurs. Seul le compte **interne**, représenté par l’expression &quot;$(loginId)!=0&quot;, possède ces autorisations.

  ```
  <sysFilter name="readAccess"> 
   <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
  </sysFilter>
  
  <sysFilter name="writeAccess">  
   <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
  </sysFilter>
  ```

  Les valeurs possibles de l’attribut **expr** utilisé pour définir la condition sont TRUE ou FALSE.

>[!NOTE]
>
>Si aucun filtre n&#39;est défini, tous les opérateurs peuvent accéder librement en lecture et en écriture au schéma.

## Protection des schémas intégrés

Par défaut, les schémas intégrés ne sont accessibles avec les autorisations d’ÉCRITURE que par les opérateurs possédant le droit d’ADMINISTRATION :

* ncm:publishing
* nl:monitoring
* nms:calendar
* xtk:builder
* xtk:connections
* xtk:dbInit
* xtk:entityBackupNew
* xtk:entityBackupOriginal
* xtk:entityOriginal
* xtk:form
* xtk:funcList
* xtk:fusion
* xtk:image
* xtk:javascript
* xtk:jssp
* xtk:jst
* xtk:navtree
* xtk:operatorGroup
* xtk:package
* xtk:queryDef
* xtk:resourceMenu
* xtk:rights
* xtk:schema
* xtk:scriptContext
* xtk:specFile
* xtk:sql
* xtk:sqlSchema
* xtk:srcSchema
* xtk:strings
* xtk:xslt

>[!CAUTION]
>
>Le schéma **xtk:sessionInfo** n’est accessible en lecture et en écriture que par le compte interne d’une instance Adobe Campaign.

## Modification des filtres système des schémas intégrés

Les schémas intégrés sont protégés afin d’éviter des problèmes de compatibilité avec les versions antérieures. Adobe recommande toutefois de ne pas modifier les paramètres de schémas par défaut afin de garantir une sécurité optimale.

Cependant, dans certains contextes, vous devrez peut-être modifier les filtres système des schémas intégrés. Pour ce faire, suivez les étapes ci-après :

1. Créez une extension du schéma intégré concerné ou ouvrez une extension existante.
1. Dans l’élément principal, ajoutez un élément enfant **`<sysfilter name="<filter name>" _operation="delete"/>`** afin d’ignorer le filtre du même nom dans le schéma intégré.
1. Vous pouvez ajouter un nouveau filtre, comme décrit dans la section [Filtres système](#system-filters).
