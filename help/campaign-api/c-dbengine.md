---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 6%
---
# DBEngine (classe)

Représente une connexion à la base de données.

Cet objet vous permet d’interroger la base de données et d’effectuer les opérations associées.

La plupart des méthodes de cette classe nécessitent des droits &#39;sql&#39;. Si l’opérateur appelle une méthode et ne dispose pas des droits appropriés, une exception est générée. En règle générale, toutes les méthodes qui modifient la base de données requièrent des droits &#39;sql&#39;, contrairement aux méthodes qui affichent simplement des informations. Reportez-vous à la documentation de chaque méthode pour savoir si les droits sont requis ou non.

## Méthodes

| Méthode | Description |
| --- | --- |
| [batchDelete](m-dbengine-batchdelete.md) | Efface par paquets les enregistrements d&#39;une table. |
| [disposer](m-dbengine-dispose.md) | Libère la connexion de toutes les ressources qui lui sont liées. |
| [exécuter](m-dbengine-execute.md) | Exécute une commande SQL. |
| [exec](m-dbengine-exec.md) | Alias de la commande d’exécution. Cette fonction est obsolète. Utilisez [execute()](m-dbengine-execute.md). |
| [requête](m-dbengine-query.md) | Exécute une requête SQL de type SELECT. |
| [queryWithTypes](m-dbengine-querywithtypes.md) | Exécute une requête SQL de type SELECT avec spécification du type de colonne. |
| [commencer](m-dbengine-begin.md) | Démarre une nouvelle transaction sur la connexion. |
| [validation](m-dbengine-commit.md) | Valide la transaction en cours sur la connexion. |
| [restauration](m-dbengine-rollback.md) | Annule la transaction en cours sur la connexion. |

## Propriétés

| Propriété | Description |
| --- | --- |
| [isOracle](p-dbengine-isoracle.md) | Renvoie true si la base de données est Oracle. |
| [isDB2](p-dbengine-isdb2.md) | Renvoie true si la base de données est de type DB2. |
| [isMySQL](p-dbengine-ismysql.md) | Renvoie vrai si la base de données est de type MySQL. |
| [isMSSQL](p-dbengine-ismssql.md) | Renvoie true si la base de données est SQL Server. |
| [isPostgreSQL](p-dbengine-ispostgresql.md) | Renvoie true si la base de données est PostgreSQL. |
| [isSybase](p-dbengine-issybase.md) | Renvoie true si la base de données est Sybase. |
| [isSybaseIQ](p-dbengine-issybaseiq.md) | Renvoie true si la base de données est Sybase IQ. |
| [isFDA](p-dbengine-isfda.md) | Renvoie true si l’accès à la base de données est réalisé via FDA. |
| [isBroken](p-dbengine-isbroken.md) | Renvoie true si la connexion n’est plus utilisable. |
| [useUnicodeData](p-dbengine-useunicodedata.md) | Renvoie vrai si la base de données contient des données Unicode. |
| [useNChar](p-dbengine-usenchar.md) | Renvoie true si Adobe Campaign utilise des champs de type NCHAR, NVARCHAR, NCLOB, NTEXT. |

## Fonctionnalités

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
