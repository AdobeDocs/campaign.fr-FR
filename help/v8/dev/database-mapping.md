---
title: Mapping de la base de données de Campaign
description: Mapping de la base de données de Campaign
feature: Data Model, Configuration
role: Developer
level: Intermediate, Experienced
exl-id: a804d164-58bf-4b15-a48e-8cf75d793668
TQID: 'https://experienceleague.adobe.com/mkPCZigiyLWLYV7orT1B2jFQKBf0FOYSDE8IqCa1i1o'
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
source-wordcount: '372'
ht-degree: 86%
---
# Mapping de la base de données{#database-mapping}

Le mapping SQL de notre schéma d&#39;exemple donne le document XML suivant :

```sql
<schema mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:schema">
  <enumeration basetype="byte" name="gender">    
    <value label="Not specified" name="unknown" value="0"/>    
    <value label="Male" name="male" value="1"/>    
    <value label="Female" name="female" value="2"/> 
  </enumeration>  

  <element name="recipient" sqltable="CusRecipient">    
    <attribute desc="Recipient e-mail address" label="Email" length="80" name="email" sqlname="sEmail" type="string"/>    
    <attribute default="GetDate()" label="Date of creation" name="created" sqlname="tsCreated" type="datetime"/>    
    <attribute enum="gender" label="Gender" name="gender" sqlname="iGender" type="byte"/>    
    <element label="Location" name="location">      
      <attribute label="City" length="50" name="city" sqlname="sCity" type="string" userEnum="city"/>    
    </element>  
  </element>
</schema>
```

## Description {#description}

L&#39;élément racine du schéma n&#39;est plus **`<srcschema>`**, mais **`<schema>`**.

Nous sommes sur un autre type de document qui est généré automatiquement à partir du schéma source, on parle alors simplement de schéma. Ce schéma sera utilisé par l’application Adobe Campaign.

Les noms SQL sont déduits automatiquement en fonction du nom et du type de l&#39;élément.

Les règles de nommage des noms SQL sont les suivantes :

* table : concaténation de l&#39;espace de noms et du nom du schéma

  Dans notre exemple le nom de la table est renseigné à partir de l&#39;élément principal du schéma dans l&#39;attribut **sqltable** :

  ```sql
  <element name="recipient" sqltable="CusRecipient">
  ```

* champ : nom de l&#39;élément précédé d&#39;un préfixe défini en fonction de son type (&#39;i&#39; pour entier, &#39;d&#39; pour double, &#39;s&#39; pour chaîne, &#39;ts&#39; pour les dates, etc.)

  Le nom du champ est renseigné à partir de l&#39;attribut **sqlname** pour chaque **`<attribute>`** et **`<element>`** typé :

  ```sql
  <attribute desc="E-mail address of recipient" label="Email" length="80" name="email" sqlname="sEmail" type="string"/> 
  ```

>[!NOTE]
>
>Les noms SQL peuvent être surchargés depuis le schéma source. Pour ce faire, renseignez les attributs « sqltable » ou « sqlname » sur l’élément concerné.

Le script SQL de création de la table généré à partir du schéma étendu est le suivant :

```sql
CREATE TABLE CusRecipient(
  iGender NUMERIC(3) NOT NULL Default 0,   
  sCity VARCHAR(50),   
  sEmail VARCHAR(80),
  tsCreated TIMESTAMP Default NULL);
```

Les contraintes des champs SQL sont les suivantes :

* pas de valeurs nulles sur les champs numériques et de dates
* les champs numériques sont initialisés à 0

## Champs XML {#xml-fields}

Par défaut, tout élément **`<attribute>`** et **`<element>`** typé est mappé sur un champ SQL de la table du schéma de données. Vous pouvez toutefois référencer ce champ au format XML plutôt que SQL, ce qui signifie que les données sont stockées dans un champ mémo (&quot;mData&quot;) de la table contenant les valeurs de tous les champs XML. Le stockage de ces données est un document XML qui respecte la structure du schéma.

Pour renseigner un champ en XML, il faut ajouter l&#39;attribut **xml** avec la valeur &quot;true&quot; sur l&#39;élément concerné.

**Exemples**

* Champ commentaire multi-lignes :

  ```sql
  <element name="comment" xml="true" type="memo" label="Comment"/>
  ```

* Description de données au format HTML :

  ```sql
  <element name="description" xml="true" type="html" label="Description"/>
  ```

  Le type &quot;html&quot; permet de stocker le contenu HTML dans une balise CDATA et d&#39;afficher un contrôle spécifique d&#39;édition HTML dans l&#39;interface cliente Adobe Campaign.

L&#39;utilisation de champs XML permet d&#39;ajouter des champs sans avoir à modifier la structure physique de la base de données. Un autre avantage est d&#39;utiliser moins de ressources (taille allouée des champs SQL, limite du nombre de champs par table, etc.).
