---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 12%
---
# sqlExecOnDataSource

Exécute un script SQL sur une source de données.

```text
sqlExecOnDataSource (query, dataSource [, value1, ... ])
```

## Paramètres

**requête** La requête SQL.

**dataSource** La source de données.

**value1, ...** variables de la requête SQL.

## Valeur renvoyée

Nombre d&#39;enregistrements mis à jour ou insérés dans une commande UPDATE ou INSERT SQL.

## Remarques

Les valeurs autorisées pour la source de données peuvent être :

* « » ou « default » pointe vers la base de données Adobe Campaign

* « nms:extAccount:InternalName » pointe vers une source de données définie dans les comptes externes Adobe Campaign (FDA)

* « name » (nom de la source de données) pointe vers une source de données définie dans le fichier de configuration de l’instance (config-instance.xml) sous la forme suivante :

  ```xml
                   <dataStore hosts="*" lang="">
        <dataSource name="datasourcename">
          <dbcnx encrypted="" login="" password=""
                 provider="" server=""/>
        </dataSource>
      </dataStore>
  ```

Exemple:

```javascript
sqlExecOnDataSource("UPDATE XtkOption SET sStringValue = $(sz) WHERE sName = $(sz)", oracleExternalDB, 'WdbcOptions_TableSpaceWork_nms:extAccount:' + sExtAccount)
```

Les variables facultatives définies en tant que paramètres de cette fonction sont définies dans [sqlGetString(query, value1, ...)](f-sqlgetstring.md)

## Fonctionnalités

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
