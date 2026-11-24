---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 29%
---
# generateRegisterHookScript

Génère le script d&#39;extension qui va être appelé lors de l&#39;évènement &quot;register&quot; de &quot;appSubscriptionRcp&quot;.

```text
String JSScriptStr = generateRegisterHookScript ( XML additionalXmlNodes )
```

## Paramètres

**additionalXmlNodes** nœuds XML contenant le lien entre les paramètres supplémentaires et le champ de mapping de ciblage.

## Valeur(s) renvoyée(s)

Script JS **JSScriptStr** permettant de lier des paramètres supplémentaires aux champs du mapping de ciblage.

## Fonctionnalités

**Schéma :** [nms:mobileApp](s-nms-mobileapp.md)

**Statique :**

Oui
