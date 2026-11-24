---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 33%
---
# BuildPreviewFromId

Construit l&#39;aperçu d&#39;un contenu à diffuser ou d&#39;une ligne du fichier de sortie (en mode externe).

```text
[ XML preview, XML queryResult ] = BuildPreviewFromId ( Number deliveryId, XML params ) const
```

## Paramètres

**deliveryId** ID de diffusion.

**params** Condition de filtrage des destinataires (@filter = &#39;@id = 5673&#39;), identifiant de contenu (@content = &#39;html&#39;, &#39;text&#39;, &#39;sms&#39;, &#39;webContent1&#39;, &#39;outputFile&#39;...), @targetPart = 1345686...

## Valeur(s) renvoyée(s)

**preview** Renvoie tous les paramètres de l’aperçu généré.

**queryResult** renvoie les données chargées pour calculer l’aperçu.

## Exemple

```javascript
var res = nms.delivery.BuildPreviewFromId(
                           deliveryId,
                           {params: {content: "html", filter: "@id=1234"}})
var preview     = res[0]
var queryResult = res[1]
```

## Fonctionnalités

**Schéma :** [nms:delivery](s-nms-delivery.md)

**Statique :**

Oui
