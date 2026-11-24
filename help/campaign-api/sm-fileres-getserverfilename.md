---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 51%
---
# GetServerFileName

Renvoie le nom du fichier sur le serveur l&#39;ayant préalablement copié dans le répertoire de chargement si nécessaire.

```text
String serverFileName = fileRes.GetServerFileName ()
```

## Paramètres

Aucune.

## Valeur(s) renvoyée(s)

**serverFileName** Nom complet du fichier sur le serveur (vide si le fichier est introuvable).

## Exemple

```javascript
var query = xtk.queryDef.create(
  {queryDef: {schema: "xtk:fileRes", operation: "get", 
    select: {
      node: [
      {expr: "@label"}, 
      {expr: "@originalName"}, 
      {expr: "@storageType"}, 
      {expr: "@fileName"}, 
      {expr: "@md5"}]
    }, 
    where: {
      condition: {expr: "@id = 4216"}
    }
  }})

var fileRes = xtk.fileRes.create(query.ExecuteQuery())
var sFileName = fileRes.GetServerFileName();
        
```

## Fonctionnalités

**Schéma :** [xtk:fileRes](s-xtk-fileres.md)

**Statique :**

Non

**Const :**

Non

**Clé uniquement :**

Non
