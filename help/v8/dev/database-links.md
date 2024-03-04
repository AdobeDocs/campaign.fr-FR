---
title: Gestion des liens dans les schémas Campaign
description: Présentation de la gestion des liens dans les schémas Adobe Campaign
feature: Data Model, Configuration
role: Developer
level: Intermediate, Experienced
source-git-commit: 6db351c8b5d30f722ddc4b0261af93cd8e3b72cd
workflow-type: tm+mt
source-wordcount: '919'
ht-degree: 64%

---


# Gestion des liens {#links--relation-between-tables}

Un lien décrit l&#39;association d&#39;une table vers une autre table.

Les types d’associations, également appelés cardinalités, sont répertoriés ci-dessous.

* cardinalité 1-1 : à une occurrence de la table source peut correspondre au plus une occurrence de la table cible,
* cardinalité 1-N : à une occurrence de la table source peuvent correspondre plusieurs occurrences de la table cible, mais à une occurrence de la table cible peut correspondre au plus une occurrence de la table source,
* cardinalité N-N : à une occurrence de la table source peuvent correspondre plusieurs occurrences de la table cible et vice versa.

Dans l’interface utilisateur, les cardinalités sont représentées par une icône spécifique.

Pour les relations de jointure avec une table/base de données de campagne :

* ![](assets/do-not-localize/join_with_campaign11.png) : Cardinalité 1-1. Par exemple, entre un destinataire et une commande en cours. Un destinataire ne peut être associé qu&#39;à une seule occurrence à la fois de la table des commandes actuelle.
* ![](assets/do-not-localize/externaljoin11.png) : Cardinalité 1-1, jointure externe. Par exemple, entre un destinataire et son pays. Un destinataire ne peut être associé qu&#39;à une seule occurrence dans la table des pays. Le contenu de la table des pays ne sera pas enregistré.
* ![](assets/do-not-localize/join_with_campaign1n.png) : Cardinalité 1-N. Par exemple, entre un destinataire et la table des abonnements. Un destinataire peut être associé à plusieurs occurrences dans la table des abonnements.

Pour les relations de jointure à l’aide de Federated Database Access (FDA) :

* ![](assets/do-not-localize/join_fda_11.png) : Cardinalité 1-1
* ![](assets/do-not-localize/join_fda_1m.png) : Cardinalité 1-N

Pour plus d’informations sur les tables FDA, voir la section [Accès à une base de données externe](../connect/fda.md).

Un lien doit être déclaré dans le schéma possédant la clé étrangère de la table liée à partir de l&#39;élément principal :

```sql
<element name="name_of_link" type="link" target="key_of_destination_schema">
  <join xpath-dst="xpath_of_field1_destination_table" xpath-src="xpath_of_field1_source_table"/>
  <join xpath-dst="xpath_of_field2_destination_table" xpath-src="xpath_of_field2_source_table"/>
  ...
</element>
```

Les liens suivent les règles suivantes :

* La définition d&#39;un lien est renseignée sur un **`<element>`** de type **link** avec les attributs suivants :

   * **name**: nom du lien de la table source
   * **cible**: nom du schéma cible
   * **label**: libellé du lien
   * **revLink** (facultatif) : nom du lien inverse du schéma cible (déduit automatiquement par défaut)
   * **integrity** (facultatif) : intégrité référentielle de l’occurrence de la table source par rapport à celle de la table cible.
Les valeurs possibles sont les suivantes :

      * **définir**: il est possible de supprimer l’occurrence source si elle n’est plus référencée par une occurrence cible.
      * **normal**: la suppression de l’occurrence source initialise les clés du lien sur l’occurrence cible (mode par défaut), ce type d’intégrité initialise toutes les clés étrangères
      * **own**: la suppression de l’occurrence source entraîne la suppression de l’occurrence cible
      * **owncopy**: identique à **own** (en cas de suppression) ou duplique les occurrences (en cas de duplication)
      * **neutral**: aucun comportement spécifique

   * **revIntegrity** (facultatif) : intégrité sur le schéma cible (facultatif, &quot;normal&quot; par défaut)
   * **revCardinality** (facultatif) : avec la valeur &quot;single&quot; renseigne la cardinalité de type 1-1 (par défaut 1-N)
   * **externalJoin** (optionnel) : force la jointure externe
   * **revExternalJoin** (optionnel) : force la jointure externe sur le lien reverse

* Un lien fait référence à un ou plusieurs champs de la table source vers la table de destination. Il n’est pas nécessaire de renseigner les champs constituant l’élément `<join>`, car ils sont automatiquement déduits par défaut à l’aide de la clé interne du schéma cible.
* Un index sur la clé étrangère du lien est automatiquement ajouté dans le schéma étendu.
* Un lien est composé de deux demi-liens, le premier est déclaré à partir du schéma source et le second est créé automatiquement dans le schéma étendu du schéma cible.
* La jointure d’un lien peut être externe (&quot;external join&quot;) en ajoutant l’attribut **externalJoin** avec la valeur &quot;true&quot; (supporté sous PostgreSQL).

>[!NOTE]
>
>Par convention, les liens sont les éléments déclarés en fin de schéma.

## Exemple : lien inverse {#example-1}

Dans l&#39;exemple ci-dessous, nous déclarons une relation 1-N à la table de schéma &quot;cus:company&quot; :

```sql
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    ...
    <element label="Company" name="company" revIntegrity="define" revLabel="Contact" target="cus:company" type="link"/>
  </element>
</srcSchema>
```

Le schéma généré :

```sql
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
  <element name="recipient" sqltable="CusRecipient"> 
    <dbindex name="companyId">      
      <keyfield xpath="@company-id"/>    
    </dbindex>
    ...
    <element label="Company" name="company" revLink="recipient" target="cus:company" type="link">      
      <join xpath-dst="@id" xpath-src="@company-id"/>    
    </element>    
    <attribute advanced="true" label="Foreign key of 'Company' link (field 'id')" name="company-id" sqlname="iCompanyId" type="long"/>
  </element>
</schema>
```

La définition du lien est complétée avec les champs composant la jointure, c’est-à-dire la clé primaire avec son XPath (« @id ») dans le schéma destination et la clé étrangère avec son XPath (« @company-id ») dans le schéma.

La clé étrangère est ajoutée automatiquement dans un élément reprenant les même caractéristiques que le champ associé dans la table destination avec comme convention de nommage le nom du schéma cible suivi du nom du champ associé (&quot;company-id&quot; dans notre exemple).

Le schéma étendu de la cible (&quot;cus:company&quot;) :

```sql
<schema mappingType="sql" name="company" namespace="cus" xtkschema="xtk:schema">  
  <element name="company" sqltable="CusCompany" autopk="true"> 
    <dbindex name="id" unique="true">     
      <keyfield xpath="@id"/>    
    </dbindex>   
    <key internal="true" name="id">      
      <keyfield xpath="@id"/>    
    </key>
    ...
    <attribute desc="Internal primary key" label="Primary key" name="id" sqlname="iCompanyId" type="long"/>
    ...
    <element belongsTo="cus:recipient" integrity="define" label="Contact" name="recipient" revLink="company" target="nms:recipient" type="link" unbound="true">      
      <join xpath-dst="@company-id" xpath-src="@id"/>    
    </element>
  </element>
</schema>
```

Un lien réverse vers la table &quot;cus:recipient&quot; a été ajouté avec les paramètres suivant :

* **name** : déduit automatiquement avec le nom du schéma source (peut être forcé avec l&#39;attribut &quot;revLink&quot; dans la définition du lien sur le schéma source)
* **revLink** : nom du lien réverse
* **target** : clé du schéma lié (schéma &quot;cus:recipient&quot;)
* **unbound** : le lien est déclaré comme élément de collection pour une cardinalité 1-N (par défaut)
* **integrity** : par défaut &quot;define&quot; (peut être forcée avec l&#39;attribut &quot;revIntegrity&quot; dans la définition du lien sur le schéma source)

## Exemple : lien simple {#example-2}

Dans cet exemple, nous déclarons un lien vers la table de schéma &quot;nms:address&quot;. La jointure est externe et est renseignée explicitement avec l&#39;adresse email du destinataire et le champ &quot;@address&quot; de la table liée (&quot;nms:address&quot;).

```sql
<srcSchema name="recipient" namespace="cus">
  <element name="recipient"> 
    ...
    <element integrity="neutral" label="Info about email" name="emailInfo" revIntegrity="neutral" revLink="recipient" target="nms:address" type="link" externalJoin="true">      
      <join xpath-dst="@address" xpath-src="@email"/>
    </element>
  </element>
</srcSchema>
```

## Exemple : cardinalité unique {#example-3}

Dans cet exemple, nous créons une relation 1-1 avec la table de schéma &quot;cus:extension&quot; :

```sql
<element integrity="own" label="Extension" name="extension" revCardinality="single" revLink="recipient" target="cus:extension" type="link"/>
```

## Exemple : lien vers un dossier {#example-4}

Dans cet exemple, nous déclarons un lien vers un dossier (schéma &quot;xtk:folder&quot;) :

```sql
<element default="DefaultFolder('nmsFolder')" label="Folder" name="folder" revDesc="Recipients in the folder" revIntegrity="own" revLabel="Recipients" target="xtk:folder" type="link"/>
```

La valeur par défaut retourne l&#39;identifiant du premier dossier éligible de type du paramètre renseigné dans la fonction &quot;DefaultFolder(&#39;nmsFolder&#39;)&quot;.

## Exemple : créer une clé sur un lien {#example-5}

Dans cet exemple, nous créons une clé sur un lien (&quot;company&quot; vers le schéma &quot;cus:company&quot;) avec le **xlink** et un champ de la table (&quot;email&quot;) :

```sql
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">
    <key name="companyEmail"> 
      <keyfield xpath="@email"/>
      <keyfield xlink="company"/>
    </key>
    
    <attribute name="email" type="string" length="80" label="Email" desc="Recipient email"/>
    <element label="Company" name="company" revIntegrity="define" revLabel="Contact" target="cus:company" type="link"/>
  </element>
</srcSchema>
```

Le schéma généré :

```sql
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
  <element name="recipient" sqltable="CusRecipient"> 
    <dbindex name="companyId">      
      <keyfield xpath="@company-id"/>    
    </dbindex>

    <dbindex name="companyEmail" unique="true">
      <keyfield xpath="@email"/>      
      <keyfield xpath="@company-id"/>    
    </dbindex>    

    <key name="companyEmail">      
      <keyfield xpath="@email"/>      
      <keyfield xpath="@company-id"/>    
    </key>

    <attribute desc="Email address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>
    <element label="Company" name="company" revLink="recipient" target="sfa:company" type="link">      
      <join xpath-dst="@id" xpath-src="@company-id"/>    
    </element>    
    <attribute advanced="true" label="Foreign key of link 'Company' (field 'id')" name="company-id" sqlname="iCompanyId" type="long"/>
  </element>
</schema>
```

La définition de la clé de nom &quot;companyEmail&quot; a été entendue avec la clé étrangère du lien &quot;company&quot;, cette clé engendre un index unique sur les deux champs.