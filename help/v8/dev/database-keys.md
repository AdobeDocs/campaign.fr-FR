---
title: Gestion des clés dans la base de données Campaign
description: Comprendre la gestion des clés dans les schémas Adobe Campaign
feature: Data Model, Configuration
role: Developer
level: Intermediate, Experienced
exl-id: cf1f5cfc-172f-44ec-ac97-804d15f9d628
source-git-commit: 0f5efba364ef924447324bdd806e15e6db8d799d
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 100%

---

# Gestion des clés {#management-of-keys}

Chaque table associée à un schéma de données doit posséder au moins une clé pour identifier un enregistrement dans une table.

Une clé est déclarée à partir de l’élément principal du schéma de données.

```sql
<key name="name_of_key">
  <keyfield xpath="xpath_of_field1"/>
  <keyfield xpath="xpath_of_field2"/>
  ...
</key>
```

Une clé est dite primaire lorsqu’elle est renseignée en premier dans le schéma ou si elle contient l’attribut `internal` avec la valeur « true ».

Une clé peut référencer un ou plusieurs champs de la table.

**Exemple**:

* Ajout d&#39;une clé sur l&#39;email et la ville :

  ```sql
  <srcSchema name="recipient" namespace="cus">
    <element name="recipient">
      <key name="email">
        <keyfield xpath="@email"/> 
        <keyfield xpath="location/@city"/> 
      </key>
  
      <attribute name="email" type="string" length="80" label="Email" desc="E-mail address of recipient"/>
      <element name="location" label="Location">
        <attribute name="city" type="string" length="50" label="City" userEnum="city"/>
      </element>
    </element>
  </srcSchema>
  ```

  Le schéma généré :

  ```sql
  <schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
    <element name="recipient" sqltable="CusRecipient">    
     <key name="email">      
      <keyfield xpath="@email"/>      
      <keyfield xpath="location/@city"/>    
     </key>    
  
     <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>    
     <element label="Location" name="location">      
       <attribute label="City" length="50" name="city" sqlname="sCity" type="string" userEnum="city"/>    
     </element>  
    </element>
  </schema>
  ```

* Ajout d&#39;une clé primaire ou interne sur le champ de nom &quot;id&quot; :

  ```sql
  <srcSchema name="recipient" namespace="cus">
    <element name="recipient">
      <key name="id" internal="true">
        <keyfield xpath="@id"/> 
      </key>
  
      <key name="email">
        <keyfield xpath="@email"/> 
      </key>
  
      <attribute name="id" type="long" label="Identifier"/>
      <attribute name="email" type="string" length="80" label="Email" desc="E-mail address of recipient"/>
    </element>
  </srcSchema>
  ```

  Le schéma généré :

  ```sql
  <schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
    <element name="recipient" sqltable="CusRecipient">    
      <key name="email">      
        <keyfield xpath="@email"/>    
      </key>  
  
      <key internal="true" name="id">      
       <keyfield xpath="@id"/>    
      </key>    
  
      <attribute label="Identifier" name="id" sqlname="iRecipientId" type="long"/>    
      <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>  
    </element>
  </schema>
  ```

## Clé primaire - Identifiant{#primary-key}

Dans le contexte d’un [Déploiement Enterprise (FFDA)](../architecture/enterprise-deployment.md), la clé primaire des tables Adobe Campaign est un **Identifiant universel unique (UUID)** généré automatiquement par le moteur de base de données. La valeur de clé est unique pour l&#39;ensemble de la base de données. Le contenu de la clé est automatiquement généré à l&#39;insertion de l&#39;enregistrement.

**Exemple**

Dans l’exemple ci-dessous, nous déclarons une clé incrémentale dans le schéma source :

```sql
<srcSchema name="recipient" namespace="cus">
  <element name="recipient"  autopk="true" autouuid="true">
  ...
  </element>
</srcSchema>
```

Le schéma généré :

```sql
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">  
  <element name="recipient"  autopk="true" autouuid="true" sqltable="CusRecipient"> 

    <key internal="true" name="id">
      <keyfield xpath="@id"/>
    </key>

    <attribute desc="Internal primary key" label="Primary key" name="id" sqlname="iRecipientId" type="long"/>
  </element>
</schema>
```

Outre la définition de la clé, un champ numérique nommé &quot;id&quot; a été ajouté dans le schéma étendu afin de contenir la clé primaire générée automatiquement.

>[!CAUTION]
>
>Un enregistrement avec une clé primaire à 0 est automatiquement inséré à la création de la table. Cet enregistrement est utilisé pour éviter les jointures externes, non efficaces sur les tables à volumes. Par défaut, toutes les clés étrangères sont initialisées avec la valeur 0, ce qui permet de toujours retourner un résultat sur la jointure lorsque la donnée n&#39;est pas renseignée.
