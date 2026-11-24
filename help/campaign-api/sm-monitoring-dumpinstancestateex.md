---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '42'
ht-degree: 21%
---
# DumpInstanceStateEx

Retourne l&#39;état des processus serveur

```text
XML monitoring = DumpInstanceStateEx ( String mask, Boolean includeDead, Boolean noDatabaseCheck, Number criticalLevel )
```

## Paramètres

**mask** Masque des instances à prendre en compte

**includeDead** Ajouter la liste des processus inactifs

**noDatabaseCheck** ne vérifie pas les alertes provenant des objets de la base de données

**criticalLevel** filtre la gravité des alertes renvoyées

## Valeur(s) renvoyée(s)

**monitoring**

## Fonctionnalités

**Schéma :** [nl:monitoring](s-nl-monitoring.md)

**Statique :**

Oui
