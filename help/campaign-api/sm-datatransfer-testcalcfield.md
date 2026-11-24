---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 27%
---
# TestCalcField

Teste le champ calculé sur les lignes d&#39;exemples

```text
XML calcFieldValues = TestCalcField ( XML dataTransferStep, String calcFieldName )
```

## Paramètres

**dataTransferStep** Étape de transfert de données où le champ calculé est défini

**calcFieldName** Champ calculé à tester

## Valeur(s) renvoyée(s)

**calcFieldValues** Renvoie la liste des valeurs pour chaque ligne d&#39;exemple (calcFieldValues/line) et le nom du champ (calcFieldValues/@name)

## Fonctionnalités

**Schéma :** [xtk:dataTransfer](s-xtk-datatransfer.md)

**Statique :**

Oui
