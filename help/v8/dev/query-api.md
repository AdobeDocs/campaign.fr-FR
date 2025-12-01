---
title: Interroger la base de données avec queryDef
description: Découvrez comment utiliser les méthodes queryDef et NLWS pour interroger la base de données Campaign
feature: API
role: Developer
level: Intermediate, Experienced
hide: true
hidefromtoc: true
exl-id: 0fd39d6c-9e87-4b0f-a960-2aef76c9c8eb
source-git-commit: 26fededf0ee83299477e45e891df30a46c6d40fe
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 2%

---

# Interroger la base de données avec queryDef {#query-database-api}

[!DNL Adobe Campaign] fournit des méthodes JavaScript puissantes pour interagir avec la base de données à l’aide de `queryDef` et de `NLWS`. Ces méthodes vous permettent de charger, créer, mettre à jour et interroger des données à l’aide de JSON, XML ou SQL.

>[!NOTE]
>
>Cette documentation couvre les API orientées données pour interroger la base de données par programmation. Pour les API REST, voir [Prise en main des API REST](api/get-started-apis.md). Pour créer des requêtes visuelles, reportez-vous à la section [Utilisation de l’éditeur de requêtes](../start/query-editor.md).

## Conditions préalables {#prerequisites}

Avant d’utiliser les méthodes queryDef et NLWS, vous devez connaître les éléments suivants :

* JavaScript
* Modèle de données et schémas [!DNL Adobe Campaign]
* Expressions XPath pour la navigation dans les éléments de schéma

En savoir plus sur le modèle de données de Campaign dans [cette page](datamodel.md).

## Méthodes statiques du schéma d’entité {#entity-schema-methods}

Chaque schéma dans [!DNL Adobe Campaign] (par exemple, `nms:recipient`, `nms:delivery`) est fourni avec des méthodes statiques accessibles par le biais de l’objet `NLWS`. Ces méthodes offrent un moyen pratique d’interagir avec les entités de base de données.

### Chargement, enregistrement et création d’entités {#load-save-create}

**Charger une entité par identifiant et la mettre à jour :**

```javascript
// Load a delivery by @id and save
var delivery = NLWS.nmsDelivery.load("12435");
delivery.label = "New label";
delivery.save();
```

**Créer un destinataire à l’aide de JSON:**

```javascript
// Create via JSON, edit via JS and save
var recipient = NLWS.nmsRecipient.create({
  x: { // the key 'x' doesn't matter
    email: 'john.doe@example.com',
  }
});
recipient.folder_id = 1183;
recipient.firstName = 'John';
recipient.lastName = 'Doe';
recipient.save();
```

**Créer un destinataire à l’aide de XML:**

```javascript
// Create via XML and save
var recipient = NLWS.nmsRecipient.create(
  <recipient
    email="support@adobe.com"
    lastName="Adobe"
    firstName="Support"
  />
);
recipient.save();
```

## Présentation de QueryDef {#querydef-overview}

Le schéma `xtk:queryDef` fournit des méthodes pour créer et exécuter des requêtes de base de données. Vous pouvez utiliser `NLWS.xtkQueryDef.create()` pour créer des requêtes avec la syntaxe JSON ou XML.

**Opérations disponibles :**

* `select` - Récupération de plusieurs enregistrements
* `get` - Récupérer un seul enregistrement (SQL `LIMIT 1`)
* `getIfExists` - Récupérez un seul enregistrement, renvoyez la valeur null s’il est introuvable.
* `count` - Compter les enregistrements répondant aux critères

Pour en savoir plus sur les méthodes queryDef, consultez la [documentation JSAPI Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/s-xtk-queryDef.html?lang=fr){target="_blank"}.

## Requête avec JSON {#query-json}

Utilisez `NLWS.xtkQueryDef.create()` pour créer des requêtes avec la syntaxe JSON. L’opération `get` récupère un seul enregistrement (`LIMIT 1` SQL), tandis que l’`select` récupère plusieurs enregistrements.

**Obtenir un seul destinataire :**

```javascript
var email = "contact@example.com";
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient", 
    operation: "get", // "get" does a SQL "LIMIT 1"
    select: { 
      node: [{expr: "@id"}, {expr: "@email"}, {expr: "@firstName"}] 
    },
    where: { 
      condition: [
        {expr: "@email = '" + email + "'"}, // filter by email
      ],
    }
  }
});

var res = query.ExecuteQuery(); 
// res is an XML object such as <recipient id="1234" email="contact@example.com" firstName="John"/>
var recipient = NLWS.nmsRecipient.load(res.$id); // conversion to a JavaScript object
recipient.email = "newemail@example.com";
recipient.save();
```

**Utilisez `getIfExists` pour éviter les exceptions :**

Si l’enregistrement n’existe peut-être pas, utilisez `operation: "getIfExists"` au lieu de `get` pour éviter les exceptions :

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient", 
    operation: "getIfExists",
    select: { node: [{expr: "@id"}] },
    where: { 
      condition: [{expr: "@email = 'nonexistent@example.com'"}]
    }
  }
});

var res = query.ExecuteQuery();
if (res) {
  logInfo("Recipient found: " + res.$id);
} else {
  logInfo("Recipient not found");
}
```

## Sélectionner plusieurs enregistrements {#select-multiple}

Utilisez l’opération `select` pour récupérer plusieurs enregistrements. Vous pouvez ajouter des conditions, un ordre et des limites.

**Workflows de requête avec filtres et ordre :**

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "xtk:workflow", 
    operation: "select", 
    select: {
      node: [
        {expr: "@id"},
        {expr: "@label"},
        {expr: "@internalName"}
      ] 
    }, 
    where: {
      condition: [
        {expr: "[folder/@name]='nmsTechnicalWorkflow'"},
        {expr: "@production = 1"}
      ]
    }, 
    orderBy: {
      node: {expr: "@internalName", sortDesc: "false"}
    }
  }
});

var res = query.ExecuteQuery();

var workflows = res.getElementsByTagName("workflow");
for each (var w in workflows) {
  logInfo(w.getAttribute("internalName"));
}
```

**Requête sur les diffusions avec syntaxe XML :**

```javascript
var q = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="select" lineCount="3">
    <select>
      <node expr="@id"/>
      <node expr="@label"/>
      <node expr="@created"/>
    </select>
    <where>
      <condition expr="@label NOT LIKE '%Proof%'" bool-operator="AND"/>
      <condition expr="@created &lt;= '2024-12-01'" bool-operator="AND"/>
    </where>
    <orderBy>
      <node expr="@lastModified" sortDesc="true"/>
    </orderBy>    
  </queryDef>
);

var deliveries = q.ExecuteQuery();
for each(var delivery in deliveries.delivery) {
  logInfo(delivery.@id + ": " + delivery.@label);
}
```

>[!NOTE]
>
>Le paramètre `lineCount` limite le nombre de résultats. Sans cela, la limite par défaut est de 10 000 enregistrements.

En savoir plus sur [ExecuteQuery](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-ExecuteQuery.html?lang=fr){target="_blank"}.

## Données de transition du workflow de requête {#workflow-transition-data}

Lorsque vous travaillez avec des activités JavaScript dans des workflows, vous pouvez interroger les données des transitions entrantes à l’aide de `vars.targetSchema` et de `vars.tableName`.

**Requête sur les données des destinataires à partir d&#39;une transition de workflow :**

```javascript
// Query data from the incoming transition
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: vars.targetSchema, // The schema from the previous activity
    operation: 'select', 
    lineCount: 999999999, // Override default 10,000 limit
    select: { 
      node: [
        {expr: '@id'},
        {expr: '@email'},
        {expr: '@firstName'},
        {expr: '@lastName'}
      ]
    },
  }
});

var records = query.ExecuteQuery(); // Returns a DOMElement

for each(var record in records.getElements()) {
  logInfo("Processing: " + record.$id + " - " + record.$email);
  
  // Clean email address
  var cleanedEmail = record.$email.replace(/\s+/g, '').toLowerCase();
  
  // Update using parameterized query to prevent SQL injection
  sqlExec(
    "UPDATE " + vars.tableName + " SET sEmail=$(sz) WHERE iId=$(l)", 
    cleanedEmail, 
    record.$id
  );
}
```

>[!CAUTION]
>
>Utilisez toujours des requêtes paramétrées avec des `$(sz)` pour les chaînes et des `$(l)` pour les entiers afin d&#39;éviter les vulnérabilités d&#39;injection SQL. Pour en savoir plus, consultez la [documentation JSAPI Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/f-sqlExec.html?lang=fr){target="_blank"}.

## Comptage des enregistrements {#count-records}

Utilisez `Count(@id)` avec un alias pour comptabiliser les enregistrements.

**Compter les hypothèses en cours d’exécution :**

```javascript
var jobCount = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:remaHypothesis" operation="get">
    <select>
      <node expr="Count(@id)" alias="@count"/>
    </select>
    <where>
      <condition expr={"@status=" + HYPOTHESIS_STATUS_RUNNING}/>
    </where>
  </queryDef>
);

var iJobCount = parseInt(jobCount.ExecuteQuery().@count);
logInfo("Running jobs: " + iJobCount);
```

**Nombre avec plusieurs conditions :**

```javascript
var xmlQuery = <queryDef schema="nms:trackingLogRcp" operation="select">
  <select>
    <node expr="DateOnly(@logDate)" groupBy="1"/>
    <node expr="count(@id)" alias="@count"/>
    <node expr="countDistinct([@broadLog-id])" alias="@distinctCount"/>
  </select>
  <where>
    <condition expr={"@logDate IS NOT NULL AND @logDate &lt; #" + today + "# AND [@url-id] &lt;&gt; 1"}/>
  </where>
</queryDef>;

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

## Répartition des valeurs {#distribution-values}

Obtenez la distribution des valeurs pour un champ spécifique, ce qui est utile pour analyser les modèles de données.

**Répartition des codes pays :**

```javascript
/**
 * @class DistributionOfValues
 * @param {string} schema - The schema name (e.g., 'nms:recipient')
 * @param {string} field - The field to analyze (e.g., '@country')
 */
function DistributionOfValues(schema, field) {
  this.queryDef = {
    operation: 'select', 
    lineCount: 200, 
    schema: schema,
    select: {
      node: [
        {alias: '@expr', expr: field, groupBy: 'true', noSqlBind: 'true'},
        {alias: '@count', expr: 'COUNT()', label: 'Count'},
      ]
    },
    orderBy: {
      node: [{expr: 'COUNT()', sortDesc: 'true'}]
    },
  };
  
  /**
   * Execute the query and return results
   * @return {Array} XML list of results
   */
  this.get = function() {
    this.results = NLWS.xtkQueryDef.create({queryDef: this.queryDef}).ExecuteQuery();
    return this.results.getElements();
  };
}

// Usage example
var d = new DistributionOfValues('nms:recipient', '@country');

// Optional: Add additional filters
d.queryDef.where = {
  condition: [{expr: 'DateOnly(@created) = #2024-12-01#'}]
};

// Execute and display results
for each(var result in d.get()) {
  logInfo(result.$expr + ': ' + result.$count);
}
```

## Création de requête dynamique {#dynamic-queries}

Créer des requêtes de manière dynamique en ajoutant des conditions par programmation.

**Ajouter des conditions à une requête existante :**

```javascript
var xmlQuery = <queryDef schema="nms:delivery" operation="select">
  <select>
    <node expr="@id"/>
    <node expr="@label"/>
  </select>
  <where/>
</queryDef>;

// Dynamically add conditions
if (includeProofs) {
  xmlQuery.where.appendChild(
    <condition expr="@label LIKE '%Proof%'"/>
  );
}

if (startDate) {
  xmlQuery.where.appendChild(
    <condition expr={"@created >= #" + Format.toISO8601(startDate) + "#"}/>
  );
}

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

**Créer des clauses select et where dans les boucles :**

```javascript
// Build select dynamically
var select = <select/>;
var fields = ["@id", "@label", "@created"];
for each(var field in fields) {
  select.appendChild(<node expr={field}/>);
}

// Build where dynamically
var where = <where/>;
var conditions = [
  "@status = 1",
  "@type = 'email'"
];
for each(var condition in conditions) {
  where.appendChild(<condition expr={condition}/>);
}

// Create complete query
var xmlQuery = <queryDef operation="select" schema="nms:delivery"/>;
xmlQuery.appendChild(select);
xmlQuery.appendChild(where);

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

## Méthodes queryDef avancées {#advanced-methods}

Au-delà de `ExecuteQuery()`, queryDef fournit plusieurs méthodes spécialisées pour des cas d’utilisation avancés.

### BuildQuery - Génère le code SQL sans l’exécuter {#build-query}

Utilisez `BuildQuery()` pour générer l’instruction SQL sans l’exécuter. Cela s’avère utile pour le débogage, la journalisation ou la transmission de requêtes à des systèmes externes.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@email"/>
    </select>
    <where>
      <condition expr="@email IS NOT NULL"/>
    </where>
  </queryDef>
);

// Get the generated SQL
var sql = query.BuildQuery();
logInfo("Generated SQL: " + sql);
// Output: "SELECT iRecipientId, sEmail FROM NmsRecipient WHERE sEmail IS NOT NULL"
```

En savoir plus sur [BuildQuery](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-BuildQuery.html?lang=fr){target="_blank"}.

### BuildQueryEx - Obtenir le code SQL avec la chaîne de format {#build-query-ex}

`BuildQueryEx()` renvoie à la fois la requête SQL et une chaîne de format compatible avec la fonction `sqlSelect()`.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@email"/>
      <node expr="@firstName"/>
    </select>
  </queryDef>
);

var [sql, format] = query.BuildQueryEx();
logInfo("SQL: " + sql);
logInfo("Format: " + format);

// Use with sqlSelect
var results = sqlSelect(format, sql);
```

En savoir plus sur [BuildQueryEx](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-BuildQueryEx.html?lang=fr){target="_blank"}.

### SelectAll - Ajoute tous les champs à sélectionner {#select-all}

La méthode `SelectAll()` ajoute automatiquement tous les champs du schéma à la clause select, ce qui vous évite de répertorier manuellement chaque champ.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select/>
    <where>
      <condition expr="@id = 12345"/>
    </where>
  </queryDef>
);

// Add all fields to the select
query.SelectAll(false);

var result = query.ExecuteQuery();
// Result contains all recipient fields
```

En savoir plus sur [SelectAll](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-SelectAll.html?lang=fr){target="_blank"}.

### Mise à jour - Enregistrements de mise à jour en masse {#mass-update}

La méthode `Update()` vous permet d’effectuer des mises à jour en masse sur les enregistrements correspondant à vos critères de requête sans charger chaque enregistrement individuellement.

```javascript
// Mass update example: set a field value for all matching records
var updateQuery = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "update",
    where: {
      condition: [{expr: "@country = 'US'"}]
    },
    set: {
      node: [{expr: "@blackList", value: "0"}]
    }
  }
});

// Execute mass update
updateQuery.Update();
logInfo("Mass update completed");
```

>[!CAUTION]
>
>Les mises à jour en masse affectent tous les enregistrements correspondant à la clause where. Testez toujours vos conditions WHERE avec une requête Select en premier pour vérifier quels enregistrements seront affectés.

En savoir plus sur [Mise à jour](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-Update.html?lang=fr){target="_blank"}.

### GetInstanceFromModel - Instances de modèle de requête {#get-instance-from-model}

Utilisez `GetInstanceFromModel()` pour récupérer des données à partir d’instances créées à partir de modèles.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@label"/>
    </select>
    <where>
      <condition expr="@isModel = 1"/>
    </where>
  </queryDef>
);

// Get instance data from template
var instance = query.GetInstanceFromModel("nms:delivery");
```

En savoir plus sur [GetInstanceFromModel](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-GetInstanceFromModel.html?lang=fr){target="_blank"}.

## Opérations par lots {#batch-operations}

Traitez plusieurs enregistrements par lots pour améliorer les performances.

**Étiquettes de diffusion de mise à jour par lots :**

```javascript
// Query all deliveries to update
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: vars.targetSchema,
    operation: 'select', 
    lineCount: 999999999,
    select: { 
      node: [{expr: '@id'}]
    },
    where: {
      condition: [{expr: "@label LIKE '%OLD%'"}]
    }
  }
});

var records = query.ExecuteQuery();

// Process each record
for each(var record in records.getElements()) {
  var delivery = NLWS.nmsDelivery.load(record.$id);
  var oldLabel = delivery.label.toString();
  var newLabel = oldLabel.replace(/OLD/g, 'NEW');
  
  logInfo("Updating: " + oldLabel + " => " + newLabel);
  
  delivery.label = newLabel;
  delivery.save();
}

logInfo("Updated " + records.getElements().length + " deliveries");
```

## Exécution SQL brute {#raw-sql}

Pour les opérations complexes, vous pouvez exécuter directement du SQL brut.

**Exécuter SQL paramétré:**

```javascript
var dbEngine = instance.engine;

// Using parameterized query (recommended)
dbEngine.exec(
  "UPDATE NmsUserAgentStats SET iVisitorsOfTheDay=$(l) WHERE tsDate=$(dt)", 
  visitorCount,
  Format.parseDateTimeInter(dateString)
);
```

**Requête avec sqlSelect:**

```javascript
// Execute SELECT query and parse results
var xml = sqlSelect(
  "collection,@id,@email", 
  "SELECT iId as id, sEmail as email FROM " + vars.tableName + " WHERE iStatus = 1"
);

logInfo(xml.toXMLString()); // "<select><collection id="1" email="..."/></select>"

for each(var record in xml.collection) {
  logInfo('ID: ' + record.@id + ', Email: ' + record.@email);
  
  // Load full object if needed
  if (vars.targetSchema == "nms:recipient") {
    var recipient = NLWS.nmsRecipient.load(record.@id);
    recipient.lastName = recipient.lastName.toUpperCase();
    recipient.save();
  }
}
```

>[!CAUTION]
>
>Lors de l’utilisation de SQL brut :
>
>* Toujours valider et nettoyer les entrées utilisateur
>* Utilisez des requêtes paramétrées avec `$(sz)`, `$(l)`, `$(dt)`, etc.
>* Tenez compte des différences entre les bases de données locales et cloud dans les déploiements [FFDA](../architecture/enterprise-deployment.md)

## Bonnes pratiques {#best-practices}

Lorsque vous utilisez les méthodes queryDef et NLWS :

* **Utiliser des requêtes paramétrées** - Utilisez toujours des paramètres liés (`$(sz)`, `$(l)`) avec `sqlExec` pour empêcher l’injection SQL
* **Set lineCount** - Remplacez la limite par défaut de 10 000 enregistrements si nécessaire avec `lineCount: 999999999`
* **Utiliser getIfExists** - Utilisez `operation: "getIfExists"` lorsque des enregistrements peuvent ne pas exister pour éviter des exceptions
* **Optimisation des requêtes** - Ajoutez des conditions de `where` appropriées pour limiter les jeux de résultats.
* **Traitement par lots** - Traitez les jeux de données volumineux par lots pour éviter les dépassements de délai
* **Sécurité des transactions** - Envisagez d’utiliser des transactions pour plusieurs mises à jour associées
* **Prise de conscience de FFDA** - Dans les déploiements [&#x200B; Entreprise (FFDA)](../architecture/enterprise-deployment.md), sachez que [!DNL Campaign] fonctionne avec deux bases de données



## Cas d’utilisation pratiques {#use-cases}

### Déboguer et consigner les requêtes {#debug-queries}

Utilisez `BuildQuery()` pour inspecter le code SQL généré avant l’exécution :

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "select",
    select: { node: [{expr: "@id"}, {expr: "@email"}] },
    where: { condition: [{expr: "@blackList = 0"}] }
  }
});

// Log the SQL for debugging
var sql = query.BuildQuery();
logInfo("About to execute: " + sql);

// Now execute
var results = query.ExecuteQuery();
```

### Dupliquer un enregistrement avec SelectAll {#duplicate-record}

Utilisez `SelectAll()` pour copier tous les champs lors de la duplication des enregistrements :

```javascript
// Query the original record
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="get">
    <select/>
    <where>
      <condition expr="@id = 12345"/>
    </where>
  </queryDef>
);

// Select all fields for duplication
query.SelectAll(true); // true indicates duplication mode

var original = query.ExecuteQuery();

// Create a new delivery from the original
var newDelivery = NLWS.nmsDelivery.create(original);
newDelivery.label = original.@label + " (Copy)";
newDelivery.save();
```

### Valider avant la mise à jour en masse {#validate-mass-update}

Prévisualisez toujours les enregistrements concernés avant d’effectuer des mises à jour en masse :

```javascript
// Step 1: Preview what will be updated
var previewQuery = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "select",
    select: { node: [{expr: "@id"}, {expr: "@email"}] },
    where: { condition: [{expr: "@country = 'US' AND @blackList = 1"}] }
  }
});

var preview = previewQuery.ExecuteQuery();
var count = preview.getElementsByTagName("recipient").length;
logInfo("About to update " + count + " recipients");

// Step 2: If count looks correct, proceed with mass update
if (count > 0 && count < 10000) {
  sqlExec("UPDATE NmsRecipient SET iBlackList = 0 WHERE sCountryCode = 'US' AND iBlackList = 1");
  logInfo("Mass update completed for " + count + " recipients");
} else {
  logWarning("Update cancelled: count is " + count);
}
```

## Référence de syntaxe de définition de requête {#querydef-reference}

Structure complète de l’objet `queryDef` :

```javascript
{
  queryDef: {
    schema: 'nms:recipient',           // Required: target schema
    operation: 'select',                // select|get|getIfExists|count
    lineCount: 100,                    // Maximum records to return
    startLine: 0,                      // Offset for pagination
    select: {
      node: [
        {
          expr: '@id',                 // XPath expression
          alias: '@myAlias',           // Optional alias
          label: 'ID',                 // Optional label
          groupBy: 'true',             // Group by this field
          noSqlBind: 'true'            // No SQL binding on constants
        }
      ]
    },
    where: {
      condition: [
        {
          expr: '@email IS NOT NULL',  // Condition expression
          boolOperator: 'AND',         // AND|OR
          setOperator: 'EXISTS',       // EXISTS|NOT EXISTS|IN|NOT IN
          enabledIf: '',               // Enabling condition
          ignore: false,               // Ignore this condition
          sql: '',                     // Native SQL expression
          'filter-name': ''            // Predefined filter name
        }
      ]
    },
    orderBy: {
      node: [
        {
          expr: '@lastModified',       // Field to sort by
          sortDesc: 'true'             // true for DESC, false for ASC
        }
      ]
    },
    groupBy: {
      node: [
        {expr: '@country'}             // Group by field
      ]
    }
  }
}
```

## Rubriques connexes {#related-topics}

* [Prise en main des API de Campaign](api.md)
* [Référence de l’API queryDef](https://experienceleague.adobe.com/developer/campaign-api/api/s-xtk-queryDef.html?lang=fr){target="_blank"}
* [Documentation JSAPI Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html?lang=fr){target="_blank"}
* [Modèle de données](datamodel.md)
* [Utiliser les schémas](schemas.md)
* [Utiliser le requêteur](../start/query-editor.md)

