---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '944'
ht-degree: 2%
---
# SchemaNode (classe)

Représente l’élément d’un schéma

## Méthodes

| Méthode | Description |
| --- | --- |
| [findNode](m-schemanode-findnode.md) | Renvoie une instance de [SchemaNode](c-schemanode.md) ou la valeur null si le nœud n&#39;existe pas et que le paramètre mustExist est défini sur false. |

## Propriétés

| Propriété | Description |
| --- | --- |
| [enfants](p-schemanode-children.md) | Renvoie un objet pour lequel chaque propriété est un nœud enfant indexé selon son nom. |
| [computeString](p-schemanode-computestring.md) | Renvoie la chaîne calculée par le nœud courant. |
| [dataPolicy](p-schemanode-datapolicy.md) | Renvoie une chaîne de caractères qui fournit la politique de données du nœud actif. |
| [description](p-schemanode-description.md) | Renvoie une chaîne de caractères décrivant le nœud actif. |
| [defaultValue](p-schemanode-defaultvalue.md) | Renvoie une chaîne de caractères qui fournit la valeur par défaut du nœud actif. |
| [editType](p-schemanode-edittype.md) | Renvoie une chaîne de caractères spécifiant le type de modification du nœud actif. |
| [énumération](p-schemanode-enumeration.md) | Renvoie un objet [Enumeration](c-enumeration.md) qui est l’énumération liée au nœud actif ou la valeur null s’il n’existe aucune énumération. |
| [enumerationImage](p-schemanode-enumerationimage.md) | Retourne le nom de l’image du nœud courant sous forme d’une chaîne de caractères. |
| [folderModel](p-schemanode-foldermodel.md) | Uniquement sur le nœud racine , renvoie une chaîne contenant le ou les modèles de dossier. Sur les autres nœuds, elle renvoie « undefined ». |
| [Image](p-schemanode-image.md) | Renvoie le nom de l’image sous la forme d’une chaîne de caractères. |
| [intégrité](p-schemanode-integrity.md) | Renvoie le type d’intégrité du lien. |
| [clés](p-schemanode-keys.md) | Renvoie une table avec les définitions des [clés SchemaKey](c-schemakey.md) du nœud actuel. |
| [hasEnumeration](p-schemanode-hasenumeration.md) | Renvoie une valeur booléenne qui indique si la valeur du nœud actif est liée à une énumération. |
| [childrenCount](p-schemanode-childrencount.md) | Renvoie un nombre qui spécifie le nombre de nœuds enfants. |
| [hasSQLTable](p-schemanode-hassqltable.md) | Renvoie une valeur de type boolean qui indique si le nœud actif est lié à une table SQL. |
| [hasUserEnumeration](p-schemanode-hasuserenumeration.md) | Renvoie une valeur de type boolean qui indique si la valeur du nœud actif est liée à une énumération utilisateur. |
| [aide](p-schemanode-help.md) | Renvoie la chaîne de caractères d&#39;aide. |
| [schéma](p-schemanode-schema.md) | Renvoie l’instance de l’objet [Schema](c-schema.md) parent de ce nœud. |
| [isAdvanced](p-schemanode-isadvanced.md) | Renvoie une valeur de type boolean qui indique si le nœud actif est avancé ou non. |
| [isAnyType](p-schemanode-isanytype.md) | Renvoie une valeur booléenne qui indique si le nœud actif est ordinaire. |
| [isAttribute](p-schemanode-isattribute.md) | Renvoie une valeur booléenne qui indique si le nœud actif est un attribut. |
| [isAutoIncrement](p-schemanode-isautoincrement.md) | Renvoie une valeur de type boolean qui indique si la valeur du nœud actif est incrémentée automatiquement. |
| [isAutoPK](p-schemanode-isautopk.md) | Renvoie une valeur de type boolean qui indique si le nœud actif est une clé primaire. |
| [isBlob](p-schemanode-isblob.md) | Renvoie une valeur booléenne qui indique si le nœud actif est un objet BLOB. |
| [isCalculated](p-schemanode-iscalculated.md) | Renvoie une valeur booléenne qui indique si la valeur du nœud actif est le résultat d’un calcul. |
| [isCDATA](p-schemanode-iscdata.md) | Renvoie une valeur booléenne qui indique si le nœud actif est mappé à partir d’un fichier XML de type CDATA. |
| [isCollection](p-schemanode-iscollection.md) | Renvoie une valeur de type boolean qui indique si le nœud actif est une collection de sous-éléments et/ou d&#39;attributs. |
| [isDefaultOnDuplicate](p-schemanode-isdefaultonduplicate.md) | Renvoie une valeur booléenne. Si la valeur ajoutée est vraie, lors de la déduplication des enregistrements, la valeur par défaut (définie dans defaultValue) est automatiquement réappliquée lors de l&#39;enregistrement. |
| [isElementOnly](p-schemanode-iselementonly.md) | Renvoie une valeur booléenne qui indique si le nœud actif est une sous-division logique du schéma. |
| [isExternalJoin](p-schemanode-isexternaljoin.md) | True si le nœud est un lien et si la jointure est externe. |
| [isFeature](p-schemanode-isfeature.md) | Renvoie une valeur booléenne qui indique si le nœud est une fonctionnalité. |
| [isLink](p-schemanode-islink.md) | Renvoie une valeur booléenne qui indique si le nœud est un lien. |
| [isMappedAsXML](p-schemanode-ismappedasxml.md) | Renvoie une valeur de type boolean qui indique si le nœud est un mappage XML. |
| [isMemo](p-schemanode-ismemo.md) | Renvoie une valeur booléenne qui indique si le nœud actif est mappé par un mémo. |
| [isMemoData](p-schemanode-ismemodata.md) | Renvoie une valeur de type boolean qui indique si le nœud actif est mappé par un objet MemoData. |
| [isNotNull](p-schemanode-isnotnull.md) | Renvoie une valeur de type boolean qui indique si le nœud actif peut prendre en compte la valeur null. |
| [isRequired](p-schemanode-isrequired.md) | Renvoie une valeur de type boolean qui indique si la valeur du nœud actif est obligatoire ou non. |
| [isRoot](p-schemanode-isroot.md) | Renvoie une valeur booléenne qui indique si le nœud est la racine du schéma. |
| [isSQL](p-schemanode-issql.md) | Renvoie une valeur de type boolean qui indique si le nœud actif est mappé dans SQL. |
| [isTemporaryTable](p-schemanode-istemporarytable.md) | Renvoie une valeur booléenne indiquant si le tableau est un tableau temporaire. La table ne sera pas créée lors de la création de la base de données. |
| [isUnbound](p-schemanode-isunbound.md) | Renvoie une valeur de type boolean qui indique si le nœud actif possède un nombre illimité d’enfants du même type. |
| [isUser](p-schemanode-isuser.md) | Renvoie une valeur booléenne qui indique si le nœud est de type utilisateur ou non. |
| [joinParts](p-schemanode-joinparts.md) | Renvoie une table d&#39;instances SchemaNode pour lesquelles chaque élément représente une condition de la jointure. |
| [libellé](p-schemanode-label.md) | Renvoie une chaîne de caractères qui est la description du nœud actif. |
| [nom](p-schemanode-name.md) | Renvoie une chaîne de caractères correspondant au nom du nœud actif. |
| [nodePath](p-schemanode-nodepath.md) | Renvoie une chaîne de caractères qui est le chemin d’accès absolu du nœud actif. |
| [parent](p-schemanode-parent.md) | Renvoie un objet [SchemaNode](c-schemanode.md) qui est l&#39;objet parent ou la valeur null s&#39;il n&#39;y en a pas. |
| [PKSequence](p-schemanode-pksequence.md) | Renvoie une chaîne de caractères qui fournit le nom de la séquence à utiliser pour la clé primaire. |
| [packageStatus](p-schemanode-packagestatus.md) | Renvoie un nombre qui donne le statut du package. |
| [lienInverse](p-schemanode-reverselink.md) | Si l&#39;élément est un lien, renvoie un objet [SchemaNode](c-schemanode.md) qui représente un lien inverse (via le schéma cible). Dans le cas contraire, la propriété n’est pas définie. |
| [SQLName](p-schemanode-sqlname.md) | Nom SQL du champ. La propriété est une chaîne vide si l&#39;objet n&#39;est pas de type SQL. |
| [SQLTable](p-schemanode-sqltable.md) | Nom SQL de la table. La propriété est une chaîne vide si l’objet n’est pas l’élément principal ou si le mappage de schéma n’est pas de type SQL. |
| [taille](p-schemanode-size.md) | Taille du type de chaîne de caractères. |
| [tableDefinition](p-schemanode-tabledefinition.md) | Une instance d&#39;un [SchemaNode](c-schemanode.md) qui est la description de la table contenant le nœud actuel, null s&#39;il n&#39;y en a pas. |
| [cible](p-schemanode-target.md) | Élément principal du schéma de la cible du lien. Si l’objet n’est pas un lien, la propriété n’est pas définie. |
| [type](p-schemanode-type.md) | Renvoie une chaîne de caractères qui fournit le type de valeur du nœud actif. |
| [userEnumeration](p-schemanode-userenumeration.md) | Renvoie une chaîne de caractères correspondant au nom de l’énumération utilisateur utilisée par le nœud actif. |

## Fonctionnalités

**Disponible en :**

* Gestion de contenu
* Propriétés de la diffusion
* Règle de typologie
* JSSP
* Méthode SOAP
* WebApp
* Workflow
