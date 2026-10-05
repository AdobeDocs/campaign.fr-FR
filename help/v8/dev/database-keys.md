---
title: Gestion des clés dans la base de données Campaign
description: Comprendre la gestion des clés dans les schémas Adobe Campaign
feature: Data Model, Configuration
role: Developer
level: Intermediate, Experienced
exl-id: cf1f5cfc-172f-44ec-ac97-804d15f9d628
TQID: 'https://experienceleague.adobe.com/vXtZ7fdqMhtrJt873qH3hfgTE7pO-SMBnqjCtcriFNQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: a1681cd8-6b2e-4955-9113-33b5f7a22b8c
    internal-label: Data model architecture
  - id: a14877cc-63b1-41d9-bf0b-5f97cadd0417
    internal-label: Configuration guidelines
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '271'
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
>Un enregistrement avec une clé primaire à 0 est automatiquement inséré lors de la création de la table. Cet enregistrement est utilisé pour éviter les jointures externes, qui ne sont pas efficaces sur les tables de volumes. Par défaut, toutes les clés étrangères sont initialisées avec la valeur 0, ce qui permet de toujours renvoyer un résultat sur la jointure lorsque la donnée n’est pas renseignée.
